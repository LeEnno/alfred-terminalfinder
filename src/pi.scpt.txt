on alfred_script(q)
  tell application "Path Finder"
    set pathList to POSIX path of the target of the front finder window
    set pathList to quoted form of pathList
    set command to "clear; cd " & pathList
  end tell
  
  tell application "System Events"
    -- some versions might identify as "iTerm2" instead of "iTerm"
    set isRunning to (exists (processes where name is "iTerm")) or (exists (processes where name is "iTerm2"))
  end tell
  
  tell application "iTerm"
    activate
    set hasNoWindows to ((count of windows) is 0)
    if isRunning and hasNoWindows then
      create window with default profile
    end if
    select first window
    
    tell the first window
      if isRunning and hasNoWindows is false then
        create tab with default profile
      end if
      tell current session to write text command
    end tell
  end tell

end alfred_script
