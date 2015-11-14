on alfred_script(q)
  tell application "Terminal"
    do script "open -a 'Path Finder' ./" in first window
  end tell
end alfred_script
