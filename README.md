# alfred-terminalfinder

Alfred workflow to open current Finder window in Terminal/iTerm and vice versa.

## Usage

Install workflow and enter following keywords depending on what you want to achieve:

- `ft`: open current **Finder** directory in **Terminal**
- `tf`: open current **Terminal** directory in **Finder**
- `fi`: open current **Finder** directory in **iTerm**
- `if`: open current **iTerm** directory in **Finder**

Thanks to @olibob we also have [Path Finder](http://www.cocoatech.com/ "Path Finder 6 by Cocoatech") support:

- `pt`: open current **Path Finder** directory in **Terminal**
- `tp`: open current **Terminal** directory in **Path Finder**
- `pi`: open current **Path Finder** directory in **iTerm**
- `ip`: open current **iTerm** directory in **Path Finder**

In addition the search result in Alfred will show you what the action will do in its subtitle, i.e. `ft`:

![Finder → Terminal](https://raw.github.com/LeEnno/alfred-terminalfinder/master/screenshot_ft.png)

## iTerm Compatibility

This workflow works with iTerm 3.x and 2.9.x. If you need support for 2.1.x, [see the `2.1.x` branch](https://github.com/LeEnno/alfred-terminalfinder/tree/2.1.x "LeEnno/alfred-terminalfinder at 2.1.x").

## Known Issues

Unfortunately there seems to be a weird bug with iTerm 3.x which causes the `fi` keyword not to work. This bug appears to vanish after some time. So if you encounter it, you may try [@hunit's suggestion](https://github.com/LeEnno/alfred-terminalfinder/issues/21#issuecomment-244546871 "fi in iterm2 doesn't work · Issue #21 · LeEnno/alfred-terminalfinder").

If you even find a way to reproduce it, I'd be happy to receive your report in the [corresponding issue](https://github.com/LeEnno/alfred-terminalfinder/issues/21 "fi in iterm2 doesn't work · Issue #21 · LeEnno/alfred-terminalfinder")... and may also flood you with all the ❤️ I have, like, forever.

## Hat tip

This workflow was heavily inspired by [ssgreg's *Terminal in Finder's folder*](https://github.com/ssgreg/AlfredWorkflows/ "ssgreg/AlfredWorkflows · GitHub").