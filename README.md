# xrandr-extend
Extend a HIDPI screen to a normal DPI external display. This command line tool
implements various solutions described in the [HIDPI Arch Linux wiki
page](https://wiki.archlinux.org/index.php/HiDPI#Multiple_displays).


## Installation

```
pip install -e git+https://github.com/ashwinvis/xrandr-extend.git#egg=xrandr_extend
```
or alternatively

```
git clone https://github.com/ashwinvis/xrandr-extend.git
cd xrandr-extend
# edit the `xrandr-extend` script
pip install -e .
```

## Quick reference

```
usage: xrandr-extend [-h] [-p PRI_RES PRI_RES] [-e EXT_RES EXT_RES] [-m] [-n]
                     [-o] [-s] [-d]
                     profile

Extend a HIDPI screen to a normal DPI external display

positional arguments:
  profile               Use preset external resolution profiles (available:
                        ['hdmi', 'vga']).

optional arguments:
  -h, --help            show this help message and exit
  -p PRI_RES PRI_RES, --pri-res PRI_RES PRI_RES
                        Modify preset resolution of primary display (default
                        [3200, 1800])
  -e EXT_RES EXT_RES, --ext-res EXT_RES EXT_RES
                        Modify preset resolution of ext. display (default
                        based on profile)
  -m, --mirror          Mirror the ext. display
  -n, --pan             pan the position of ext. display
  -o, --only            extend and use only ext. display
  -s, --pos             set the position of ext. display explicitly
  -d, --dry-run         Preview command without executing it

Examples
--------
# Default option requires only the scaling factors and display name
$ xrandr-extend --dry-run vga
$ xrandr-extend vga
$ xrandr-extend hdmi

# Other options to extend the display
$ xrandr-extend --pan hdmi
$ xrandr-extend --only hdmi
$ xrandr-extend -e 1024 768 -n vga  # Pan with custom external resolution
```
