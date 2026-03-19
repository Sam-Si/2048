# 2048_game_cpp

This is a C++ implementation of the 2048 game using SDL for graphics.

*This version has been updated to focus exclusively on macOS support.*

# --Dependencies--
Requires:
- SDL2
- SDL2_image
- SDL2_ttf

### For MacOS
```sh
brew install sdl2 sdl2_image sdl2_ttf
```

# --Compilation on macOS--

**You should make sure all dependencies are installed before compiling.**

To build and run the game on macOS, use the following commands:
```sh
mkdir -p build && rm -rf build/*
cmake -S . -B build -DSOFTWARE_ACC=ON
cmake --build build
./build/2048
```

## Alternatively, use the Makefile:
```sh
make clean && make release CXXFLAGS="-DSOFTWARE_ACC"
./2048
```

# --Directions--
Usage: `./2048 <-s/--size> <-w/--window>`
- `-s/--size` specifies number of tiles in each row (default is 4)
- `-w/--window` specifies initial size of window (default is 600)

**Example:**
```sh
./2048 -s 4 -w 600
```
Would start game with a 4x4 board on a 600x600 pixel window.

# --License and Credits--
Original code by Nicholas Metcalf. Updates for macOS and CMake support added.

# Enjoy!
