# polybar-brightness

This polybar module allows you to control and display the screen brightness using `brightnessctl`. The script dynamically detects the appropriate backlight device and provides options to increase, decrease, set, and display the brightness level directly within your polybar.


## Dependencies

- [brightnessctl](https://github.com/Hummer12007/brightnessctl) - A command-line utility to control brightness levels on Linux systems.

## Setup

Ensure you have `brightnessctl` installed on your system. This script will automatically detect your backlight device, so there should be no need to hardcode it.

Add the following to your polybar configuration. Set the appropriate interval for updating the brightness display as needed.

```ini
[bar/BAR_NAME]
enable-ipc = true
modules-center = brightness
```

Configure the brightness module in your polybar config. Replace `BAR_NAME` with the actual name of your polybar bar configuration.

```ini
[module/brightness]
type = custom/script
tail = true
exec = ~/path-to-your-script/brightness.sh get
click-left = ~/path-to-your-script/brightness.sh up
click-right = ~/path-to-your-script/brightness.sh down
scroll-up = ~/path-to-your-script/brightness.sh up
scroll-down = ~/path-to-your-script/brightness.sh down
```

### Available Commands

- `up`: Increase brightness by 5%
- `down`: Decrease brightness by 5%
- `max`: Set brightness to 100%
- `min`: Set brightness to 0%
- `get`: Display current brightness percentage


