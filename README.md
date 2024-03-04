# Alacritty Pywal Setter

A bash script to export generated colors from pywal to Alacritty's updated config.

Tested on Arch Linux (March 5th 2024) with Alacritty (0.13.1-1) and it works.
The results won't matter on any linux distro.

## Fork Purpose
Original project was based on yaml, but Alacritty changed it's default config from yaml to toml.

## Installation
```sh
git clone https://github.com/davynoe/alacritty-pywal-setter
cd alacritty-color-export
chmod +x script.sh
```

## Usage
Comment out your existing colors in your Alacritty config or remove them before running the script to avoid duplication errors.
Generate wal colors based on your image if you never did it before:
### On Linux
```sh
wal -i <image.png>
```

### On Mac
```sh
wal -ni <image.png>
```

```sh
# Execute
./script.sh

# Execute with custom config
./script.sh </path/to/config.toml>
```

## Example

##### Terminal emulator:

```bash
$ ./script.sh
```

##### Input (~/.cache/wal/colors.sh):

```
...
color0='#0a0c0a'
color1='#514739'
color2='#6B4F39'
color3='#776338'
color4='#5E5747'
color5='#936843'
color6='#75936F'
color7='#d6c6a6'
color8='#958a74'
color9='#514739'
color10='#6B4F39'
color11='#776338'
color12='#5E5747'
color13='#936843'
color14='#75936F'
color15='#d6c6a6'
...
```

##### Output (~/.config/alacritty/alacritty.yml):

```toml
...
# BEGIN ACE
[colors.primary]
background = "0x0e0400"
foreground = "0xf5e6c6"

[colors.cursor]
text =       "0x0e0400"
cursor =     "0xf5e6c6"

[colors.normal]
black =      "0x0e0400"
red =        "0xBB6E37"
green =      "0xAE8F38"
yellow =     "0xC3913F"
blue =       "0xDBAA4B"
magenta =    "0xF7C95E"
cyan =       "0xE3BB87"
white =      "0xf5e6c6"

[colors.bright]
black =      "$color8"
red =        "0xBB6E37"
green =      "0xAE8F38"
yellow =     "0xC3913F"
blue =       "0xDBAA4B"
magenta =    "0xF7C95E"
cyan =       "0xE3BB87"
white =      "0xf5e6c6"
# END ACE
```

## Possible Issues
- ~~If there isn't ``# BEGIN ACE`` comment, the script wipes out whole config.~~

## License
This software is under [The Do What The Fuck You Want To Public License (WTFPL)](http://www.wtfpl.net/about/).