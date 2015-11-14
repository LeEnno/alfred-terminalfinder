on alfred_script(q)
  tell application "Path Finder"
    set pathList to POSIX path of the target of the front finder window
  end tell

  tell application "System Events"
    if not (exists (processes where name is "Terminal")) then
      do shell script "open -a Terminal " & quoted form of pathList
    else
      tell application "Terminal"
        activate
        delay 0.25
        tell application "System Events" to tell process "Terminal" to keystroke "t" using command down
        do script ("cd " & quoted form of pathList & "; clear") in first window
      end tell
    end if
  end tell
end alfred_script
