## OS
- Ubuntu 20.04.1 LTS

## SDL2のインストール
とりあえずパッケージをアップデート・アップグレード
```
$ sudo apt update -y
$ sudo apt upgrade -y
```
ビルドに必要なパッケージをインストール
```
$ sudo apt install build-essential -y
```
SDL2と必要なパッケージをインストール
```
$ sudo apt install libsdl2-dev libsdl2-2.0-0 -y
$ sudo apt install libjpeg-dev libwebp-dev libtiff5-dev libsdl2-image-dev libsdl2-image-2.0-0 -y
$ sudo apt install libmikmod-dev libfishsound1-dev libsmpeg-dev liboggz2-dev libflac-dev libfluidsynth-dev libsdl2-mixer-dev libsdl2-mixer-2.0-0 -y
$ sudo apt install libfreetype6-dev libsdl2-ttf-dev libsdl2-ttf-2.0-0 -y
$ sudo apt install libsdl2-gfx-dev libsdl2-gfx-dev -y
```
これでSDL2の導入は完了です．SDL2のヘッダーファイルは`/usr/include/SDL2`にインストールされます．

#### コンパイルオプションについて
リンクするもの・他オプションは適宜変えてください．
```
gcc ファイル名 -lm -lSDL2 -SDL2_image -lSDL2_mixer -lSDL2_ttf -lSDL2_ttf -lSDL2_gfx -lSDL2_net
```

## libcwiimote のインストール

```
$ git clone https://github.com/kuboshiba/sdl2_libcwiimote
$ cd sdl2_libcwiimote/include
```