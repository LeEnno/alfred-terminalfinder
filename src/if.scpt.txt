on alfred_script(q)
  tell application "iTerm"
    tell the current session of current window
      write text "open -a Finder ./"
    end tell
  end tell
end alfred_script
