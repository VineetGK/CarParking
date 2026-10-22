# CarParking

A small 3D car-park scene written in C with OpenGL and GLUT: a 6x6 lot of
parked cars, optional houses around it, and one car you can drive.

## Build

Linux (Debian/Ubuntu):

```sh
sudo apt install build-essential freeglut3-dev
gcc CarParkingCode.c -o carparking -lGL -lGLU -lglut -lm
./carparking
```

macOS ships GLUT as a framework (deprecated, but it still builds):

```sh
clang CarParkingCode.c -o carparking -framework OpenGL -framework GLUT -Wno-deprecated-declarations
```

Note: on macOS the include is `<GLUT/glut.h>`, so change the first line of the source first.

Windows (MSYS2 MinGW-w64 with freeglut):

```sh
pacman -S mingw-w64-x86_64-gcc mingw-w64-x86_64-freeglut
gcc CarParkingCode.c -o carparking.exe -lfreeglut -lopengl32 -lglu32 -lm
```

## Controls

Camera mode (default):

| Key | Action |
| --- | --- |
| Up / Down arrow | Move the camera forward / backward |
| Left / Right arrow | Turn the camera left / right |
| `a` / `s` | Move the camera along the view axis and raise/lower it (the in-app menu calls these "left" and "away") |
| `w` / `d` | Slide the camera sideways (the in-app menu calls these "near" and "right") |
| `t` | Top view |
| `q` | Quit |

Mouse:

- Right click: a menu listing the controls (informational only).
- Left click: a menu with **HOUSE** (toggle the houses around the lot) and
  **MOVE CAR** (toggle the arrow keys between moving the camera and driving
  the yellow car).

Car mode (after choosing MOVE CAR):

| Key | Action |
| --- | --- |
| Up / Down arrow | Drive forward / reverse |
| Left / Right arrow | Steer left / right while moving |

## License

GPL-3.0, see [LICENSE](LICENSE).
