# Nomad Space Sim Game

## Installation

### ARM toolchain and devkitPro

This works on Fedora 39 Workstation.

```sh
sudo dnf install pacman
sudo pacman-key --init

export DEVKITPRO=/opt/devkitpro
export DEVKITARM=${DEVKITPRO}/devkitARM
export DEVKITPPC=${DEVKITPRO}/devkitPPC
export PATH=${DEVKITPRO}/tools/bin:$PATH

sudo pacman-key --recv BC26F752D25B92CE272E0F44F7FD5492264BB9D0 --keyserver keyserver.ubuntu.com
sudo pacman-key --lsign BC26F752D25B92CE272E0F44F7FD5492264BB9D0

wget https://pkg.devkitpro.org/devkitpro-keyring.pkg.tar.xz
sudo pacman -U devkitpro-keyring.pkg.tar.xz
```

Edit `sudo vim /etc/pacman.conf` and add these lines at the end of the file.

```ini
[dkp-libs]
Server = https://pkg.devkitpro.org/packages

[dkp-linux]
Server = https://pkg.devkitpro.org/packages/linux/$arch/
```

And now install devkitPro.

```sh
sudo pacman -Syu gba-dev # select all as option
```

### Emulator

- mGBA emulator - https://mgba.io/

## Compile and run

```sh
# Do this first time you open new terminal.
./env.sh

# And then compile and run the game.
# This is for mGBA instalkled through Flatpak. Change this file
# if you need to run the game with something else.
./run.sh
```

## Resources

- https://github.com/gbdev/awesome-gbdev
- https://deep-fold.itch.io/pixel-planet-generator
- https://deep-fold.itch.io/space-background-generator
- https://github.com/mrombout/gbdk_playground
- https://itch.io/jam/gbajam22
- https://devkitpro.org/wiki/devkitPro_pacman
