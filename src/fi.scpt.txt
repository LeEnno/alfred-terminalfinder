tell application "Finder"
	set pathList to (quoted form of POSIX path of (folder of the front window as alias))
end tell

do shell script "open -a iTerm.app " & pathList