# dual-display
The bash utility that extend a primary screen of a computer to be able to connect external devices without direct VGA or HDMI ports (e.g. tablets) as monitors. **No cables required!**

## Requirements
The following packages should be installed:
- [xrandr](https://wiki.archlinux.org/index.php/xrandr) - an official configuration utility to the RandR X Window System extension.
- [x11vnc](https://wiki.archlinux.org/index.php/x11vnc) - a virtual network computing server which allows to view remotely and interact with real X displays.

## Acknowledgement
I was inspired to write the script by [this article](https://bbs.archlinux.org/viewtopic.php?id=191555). Thank you **kjans** for your community contribution :)

## Getting started
It's recommended (for quick access) place the `.dual-display` script into the home directory (however you can place it wherever you want):
```bash
$ mv .dual-display ~/
```
1. Setup proper **output names** (may be specific for your system). You can see a list of output names by the following command:
    ```bash
    $ xrandr
    ```
2. Provide **executable permissions** for the script:
    ```bash
    $ sudo chmod +x .dual-display
    ```

3. **Use the script** (the following command prints a manual):
    ```bash
    $ bash .dual-display
    ```

Use primary commands **in order** mentioned in the documentation if you don't understand how `xrandr` works (in other case unexpected behavior may occur).

Don't try to create several same modes (with identical parameters) per a user session! That will not work ;)

## Documentation
### Primary commands
`**-c**` – **create** a mode for a virtual output.

`**-e**` – **enable** a mode of a virtual output.

`**-d**` – **disable** a mode of a virtual output.

### Configuration
> It's recommended to **manually edit this configuration** of the script if you will use it frequently with same parameters which differ from defaults!

`**-h**` – **height** of a virtual screen (default `800`, used with the `-c` and `-d` flags).

`**-p**` – **primary output name** (default `LVDS-1`, used with the `-c` flag).

`**-r**` – **refresh frequency** of a virtual screen (default `60`, used with the `-c` flag).

`**-v**` – **virtual output name** (default `VGA-1`, used with the `-c` and `-d` flags).

`**-w**` – **width** of a virtual screen (used with the `-c` and `-d` flags).


## Copyright and License
Copyright (c) 2017 Yuriy Rabeshko. Code released under the MIT license.