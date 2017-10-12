# TIC-80 Build Tutorial

This is a tutorial to build the open source fantasy console [TIC-80](https://github.com/nesbox/TIC-80)

## Tools you'll need

You'll have to have these tools installed:
- MinGW32 (32 bits version is a must)
- EMScripten Compiler

#### Installing Mingw32

Download the installer from its [donwload page](https://sourceforge.net/projects/mingw/files/Installer/mingw-get-setup.exe/download).
Once you have MinGW Installation Manager (search for mingw-get.exe if you don't) running, you'll select
"All Packages > MinGW > MinGW Base System" on the left column. On the main panel, mark for installation _at least_
*ming32-base* and *mingw32-gcc*.

After you finished the setup, open a command prompt and type in `gcc --version` and make sure you have both `gcc` and `mingw32-make` on path.
If you don't, you add their folder manually now.

#### Installing EMScripten Compiler

Just follow the instructions on [this page](https://kripken.github.io/emscripten-site/docs/getting_started/downloads.html).

## Cloning TIC-80

Clone from github

## Building TIC-80

- build tools\bin2txt
- run mingw32-make emscripten
- run mingw32-make mingw

You should now find the `bin\tic.exe` executable.

