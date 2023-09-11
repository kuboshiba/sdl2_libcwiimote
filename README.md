## OS
- Ubuntu 20.04.1 LTS

## Installing SDL2
First, update/upgrade repo.
```
$ sudo apt update -y
$ sudo apt upgrade -y
```
Install the packages required for build.
```
$ sudo apt install build-essential -y
```
Install SDL2 and required packages.
```
$ sudo apt install libsdl2-dev libsdl2-2.0-0 -y
$ sudo apt install libjpeg-dev libwebp-dev libtiff5-dev libsdl2-image-dev libsdl2-image-2.0-0 -y
$ sudo apt install libmikmod-dev libfishsound1-dev libsmpeg-dev liboggz2-dev libflac-dev libfluidsynth-dev libsdl2-mixer-dev libsdl2-mixer-2.0-0 -y
$ sudo apt install libfreetype6-dev libsdl2-ttf-dev libsdl2-ttf-2.0-0 -y
$ sudo apt install libsdl2-gfx-dev libsdl2-gfx-dev -y
```
The installation of SDL2 is now complete. SDL2 header files are installed in `/usr/include/SDL2`.

#### About compile options
Please change the link and other options as appropriate.
```
gcc [filename] -lm -lSDL2 -lSDL2_image -lSDL2_mixer -lSDL2_ttf -lSDL2_ttf -lSDL2_gfx -lSDL2_net
```

## Installing libwiimote
Install required packages.
```
$ sudo apt install libical-dev libreadline-dev libbluetooth-dev -y
```

clone this repository.
```
$ sudo apt install git -y
$ git clone https://github.com/kuboshiba/sdl2_libcwiimote
```
Copy libcwiimote header files to `/usr/local/include/`
```
$ cd sdl2_libcwiimote/include
$ sudo cp -r libcwiimote /usr/local/include/
```
Copy the libcwiimote shared library to `/usr/local/lib/`
```
$ cd ../lib/
$ sudo cp * /usr/local/lib/
```
Create shared library permissions and symbolic links.
```
$ cd /usr/local/lib/
$ sudo chmod 644 libcwiimote.a
$ sudo chmod 644 libcwiimote.so.3.1.0
$ sudo chmod 755 libcwiimote.la
$ sudo ln -s libcwiimote.so.3.1.0 ./libcwiimote.so
$ sudo ln -s libcwiimote.so.3.1.0 ./libcwiimote.so.3
```

Edit `/etc/ld.so.conf` Add `/usr/local/lib`
```
$ sudo vim /etc/ld.so.conf
```
Apply settings.
```
$ sudo ldconfig
```

#### About compile options
Please change the link and other options as appropriate.
```
$ gcc [filename] -lm -lcwiimote
```
