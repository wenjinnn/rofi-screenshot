## rofi-screenshot wayland fork, work with wayland only

![](https://imgur.com/7io5BKJ.gif)

I got sick of not having a simple solution to take screenshots and screencasts.

Plus, there's so many different things I might want to do I struggle to find key bindings for all of them. So, I created a script to show and execute various screen capture related commands in Rofi.

### Features
* Capture a region to the clipboard or a directory
* Capture a window to the clipboard or a directory
* Capture the whole screen to the clipboard or a directory
* Record a specific region and save as a gif or MP4, optionally with audio
* Record the whole screen and save as a gif or MP4, optionally with audio

> [!NOTE]
> Window operations only support in Hyprland or Sway

### Installation
Make sure you have the required [dependencies](#dependencies) installed.

Download the rofi-screenshot source code, save as rofi-screenshot and make it executable
```bash
$ git clone https://github.com/wenjinnn/rofi-screenshot-wayland.git && cd rofi-screenshot-wayland && chmod u+x rofi-screenshot
```
Then move rofi-screenshot to somewhere in your $PATH for example:
```bash
$ sudo mv rofi-screenshot /usr/local/bin/
```

### Usage
Show the rofi menu
```bash
$ rofi-screenshot
```

Stop recording
```bash
$ rofi-screenshot -s
```

Immediately take a screenshot without displaying rofi menu, useful when the timing is important
```bash
$ rofi-screenshot -i
```
**Tip**: Add a keybinding for both of the above commands

### Configuration
| environment variable           | default value                   |                                                                                                                     |
| ------------------------------ | ------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| `$ROFI_SCREENSHOT_DIR`         | `$XDG_PICTURES_DIR/Screenshots` | By default files will be stored in `$XDG_PICTURES_DIR/Screenshots`, which typically means `~/Pictures/Screenshots`. |
| `$ROFI_SCREENSHOT_DATE_FORMAT` | `+%d-%m-%Y %H:%M:%S`            | Possible alternative: `+%Y-%m-%d-%H-%M-%S`                                                                          |

### Dependencies

* [rofi](https://github.com/davatorium/rofi)
* [grim](https://sr.ht/~emersion/grim/)
* [slurp](https://github.com/emersion/slurp)
* [ffmpeg](https://ffmpeg.org/)
* [wl-clipboard](https://github.com/bugaevc/wl-clipboard)
* [wl-screenrec](https://github.com/russelltg/wl-screenrec)
* [libnotify](https://gitlab.gnome.org/GNOME/libnotify)
* [jq](https://jqlang.github.io/jq/)
* [swappy](https://github.com/jtheoof/swappy) optional, for Edit with swappy action in notification
* [nautilus](https://github.com/GNOME/nautilus) optional, for Show in files action in notification
* [xdg-utils](https://www.freedesktop.org/wiki/Software/xdg-utils/) optional, for open screenshot with your default application in notification
* [tesseract](https://github.com/tesseract-ocr/tesseract) optional, for OCR your screenshot and copy the content to clipboard in notification
