on alfred_script(q)
  tell application "Finder"
    set pathList to (quoted form of POSIX path of (folder of the front window as alias))
  end tell

  tell application "System Events"
    if not (exists (processes where name is "Terminal")) then
      do shell script "open -a Terminal " & pathList
    else
      tell application "Terminal"
        activate
        if (count of windows) is 0 then
          do script ("cd " & pathList)
        else
          tell application "System Events" to tell process "Terminal.app" to keystroke "t" using command down
          delay 1
          do script ("cd " & pathList) in first window
        end if
      end tell
    end if
  end tell
end alfred_script