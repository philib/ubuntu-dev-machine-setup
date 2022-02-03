# Custom xkb keyboard layout

1. Places the custom keyboard layout in the following folder: `/usr/share/X11/xkb/symbols`
2. Adds the keyboard layout to `/usr/share/X11/xkb/rules/evdev.xml`
3. Runs `sudo dpkg-reconfigure xkb-data` to apply the custom keyboard variant
4. You can now choose this variant in the system settings or by setting via `setxkbmap us-de-vim`

