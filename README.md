# Alacritty Pywal Setter

A bash script to export generated colors from pywal to Alacritty's updated config.

Tested on Arch Linux (March 5th 2024) with Alacritty (0.13.1-1) and it works.
The results won't matter on any linux distro.

## Fork Purpose
Original project was based on yaml, but Alacritty changed it's default config from yaml to toml.

## Installation
```sh
git clone https://github.com/davynoe/alacritty-pywal-setter
cd alacritty-pywal-setter
chmod +x script.sh
```

## Usage
Comment out your existing colors in your Alacritty config or remove them before running the script to avoid duplication errors.

Generate wal colors based on your image if you never done it or if you want to use a different image from before:
###
```sh
wal -i <image>
```

```sh
# Execute
./script.sh

# Execute with custom config
./script.sh </path/to/config.toml>
```

You can take a look at example.toml on this repository, it is an example of the expected config after you run the script.

## Possible Issues
- ~~If there isn't ``# BEGIN ACE`` comment, the script wipes out whole config.~~

## License
This software is under [The Do What The Fuck You Want To Public License (WTFPL)](http://www.wtfpl.net/about/).
