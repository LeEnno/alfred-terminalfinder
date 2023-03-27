-- Properties
property open_in_new_window : false -- Open in a new window if true
property open_in_new_tab : true -- Open in a new tab if true
property our_delay : 0.5 -- Delay between keystrokes, increase if needed

-- Keystrokes
property new_window_keystroke : "n" -- Keystroke for opening a new window
property new_tab_keystroke : "t" -- Keystroke for opening a new tab
property return_key_code : 36 -- Key code for the return key

-- Handlers
-- Open a new Warp window
on open_new_window()
    perform_keystroke(new_window_keystroke, command down)
end open_new_window

-- Open a new Warp tab
on open_new_tab()
    perform_keystroke(new_tab_keystroke, command down)
end open_new_tab

-- Activate the Warp application
on activate_warp()
    tell application "Warp" to activate
end activate_warp

-- Send a command to the Warp terminal
on send_command(command_text)
    tell application "System Events"
        tell process "Warp"
            keystroke command_text
            delay(our_delay)
            key code return_key_code
        end tell
    end tell
end send_command

-- Perform a keystroke with optional modifiers
on perform_keystroke(key_label, key_modifiers)
    tell application "System Events"
        tell process "Warp"
            keystroke key_label using key_modifiers
        end tell
    end tell
end perform_keystroke

-- Main
-- This handler is called by Alfred with the query (not used in this script)
on alfred_script(query)
    -- Get the current folder path from Finder
    tell application "Finder"
        set currentFolder to (folder of the front window as alias)
    end tell
    set currentPath to POSIX path of currentFolder

    -- Activate Warp
    activate_warp()

    -- Choose whether to open a new window, new tab, or reuse the current tab
    if open_in_new_window then
        open_new_window()
    else if open_in_new_tab then
        open_new_tab()
    end if

    -- Send the change directory command to Warp
    send_command("cd " & quoted form of currentPath)
end alfred_script