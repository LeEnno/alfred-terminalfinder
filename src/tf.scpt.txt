on alfred_script(q)
  tell application "Terminal"
    do script "open -a Finder ./" in first window
  end tell
end alfred_script
