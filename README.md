# TIC-80 Build Tutorial

This is a tutorial to build the open source fantasy console [TIC-80](https://github.com/nesbox/TIC-80)

## Tools you'll need

You'll have to have these tools installed:
- MinGW32 (32 bits version is a must)
- EMScripten Compiler

#### Installing Mingw32

Download the installer from its [donwload page](https://sourceforge.net/projects/mingw/files/Installer/mingw-get-setup.exe/download).
Once you have MinGW Installation Manager running (search for mingw-get.exe if you don't), select "All Packages > MinGW > MinGW Base System" on the left column. On the main panel, mark for installation `ming32-base` and check "Installation > Apply Changes".

After you finished the setup, open a command prompt and type in
```
gcc --version
```
and make sure you have both `gcc` and `mingw32-make` on path. If you don't, you add them manually. These tools are usually located under `C:/MinGW/bin`.

#### Installing EMScripten Compiler

Just follow the instructions on [this page](https://kripken.github.io/emscripten-site/docs/getting_started/downloads.html).

## Cloning TIC-80

Clone TIC from [github](https://github.com/nesbox/TIC-80).
From TIC's official README:
```
mkdir tic
cd tic
git clone https://github.com/nesbox/3rd-party
git clone https://github.com/nesbox/TIC-80
```

## Building TIC-80

The first time you build TIC, you'll need to run these commands:
```
cd TIC-80
cd tools/bin2txt
mingw32-make
cd ../..
mingw32-make emscripten
mingw32-make mingw
```

You should now be able to run the `bin\tic.exe` executable.

Further TIC builds should be done with
```
mingw32-make mingw
```
inside the `TIC-80` folder.

### Note

If you still get errors from building TIC, try opening the `makefile` in the `TIC-80` folder and change the first line from
```
CC=gcc
```
to
```
CC=mingw32-gcc -m32
```


### Another Note

You may have to copy some needed dlls into the `bin` folder. These dlls you can get by compiling the 3rd party libs you find in the [3rd-party repository](https://github.com/nesbox/3rd-party).

## That's all!
