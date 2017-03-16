# Magpie — an Alfred workflow

Collect shiny UX things with pictures and notes using [Alfred](https://www.alfredapp.com/).

## Features

* Take a [screenshot using a keyboard shortcut](https://support.apple.com/en-au/HT201361) or [record a GIF](http://www.cockos.com/licecap/) for `magpie` to collect.
* Use `m1` Alfred keyword, a Screenshot title, and a URL (or just `#`) to save the most recent screenshot to your magpie collection.
* Use `m2` Alfred keyword and a text description to save text below your screenshot in your magpie collection.
* Use `magpie` Alfred keyword to open your magpie collection.

## Setup

* Install [Alfred](https://www.alfredapp.com/).
* Optional: install [Marked 2](http://marked2app.com/), a markdown preview tool. Or use a text editor of your choosing.

1. Clone this repo. See also: [Cloning a repository](https://help.github.com/articles/cloning-a-repository/).
2. Import the Alfred workflow (by double-clicking on it). You might need to set the hotkey trigger keywords (`m1`, `m2`, `magpie`) after import.
3. Open the `magpie` script in a text editor and update these paths:
    * `SCREENSHOT_FOLDER = Pathname('~/dropbox-personal/utilities/screenshots/').expand_path` — set this to [wherever your screenshots are saved](https://discussions.apple.com/thread/5393832?tstart=0)
    * `MAGPIE_FOLDER = Pathname('~/dropbox-personal/utilities/magpie/collection/').expand_path` — set this to where you'd like your magpie image collection to live
    * `MAGPIE_NOTES = Pathname('~/dropbox-personal/utilities/magpie/ux-magpie-collection.md').expand_path` — set this to where you'd like your magpie collection Markdown or text file to live
4. In the Alfred workflow, update the same paths in each of the scripts run. Note `open -a Marked\ 2 ~/dropbox-personal/utilities/magpie/ux-magpie-collection.md` is set to use the Marked 2 application, but any text editor will do.

## Extras

* If you want to be notified when the `magpie` script has collected an item, uncomment all the lines containing `notify`. For `notify`, you can use this osacript saved to `/usr/local/bin/notify` and made executable using `chmod 755 /usr/local/bin/notify`:
```
#! /bin/bash
/usr/bin/osascript -e "display notification \"$*\""
```

* If you want to archive screenshots after collecting them, make an `archive` folder in the screenshots folder and uncomment this line:

```
# FileUtils.mv(newest_file, SCREENSHOT_FOLDER+"archive")
```

* Explore the `magpie` script to see how you might auto-commit content …

