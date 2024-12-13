<div align="center">
  
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://github.com/pcsagan/conf/blob/main/LICENSE)

</div>

## What is it?

A simple shell script for editing common configuration files by name.

`$EDITOR` must be set for this script to work. Do this by adding `export EDITOR='program'` to your `.bashrc` or `.zprofile`, or by prefixing script execution with `EDITOR=program`.

A default configuration file is written to `${HOME}/.config/conf/conf.conf` if it does not exist when the script is run.

If the user does not have write permissions to the desired configuration file, then `sudoedit` will be used in place of `$EDITOR`.

## Usage

Assuming `EDITOR=nvim` and a configuration file of:
```
pacman=/etc/pacman.conf
yay=$pacman
neofetch=${HOME}/.config/neofetch/config.conf
```

`conf` is equivalent to `nvim ${HOME}/.config/conf/conf.conf`

`conf conf` is equivalent to `conf`

`conf pacman` is equivalent to `sudoedit /etc/pacman.conf`

`conf yay` is equivalent to `conf pacman`

`conf neofetch` is equivalent to `nvim ${HOME}/.config/neofetch/config.conf`

## Notes

1. Wherever possible the script will verify a file or directory exists before trying to use it.
2. Default configuration paths are only written to the default configuration file if they exist.
3. Configuration file paths can contain variables and refer to other configuration names.

## License

This project is licensed under the **MIT license**. Feel free to edit and distribute this template as you like.

See [LICENSE](LICENSE) for more information.