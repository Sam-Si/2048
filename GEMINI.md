# 2048 SDL C++ Project Context

## Project Overview
This is a C++ implementation of the popular 2048 puzzle game using the **SDL2** (Simple DirectMedia Layer) library for graphics, input, and font rendering. The project is specifically optimized for **macOS** but uses standard C++11 and SDL2, making it potentially portable.

### Key Technologies
- **C++11**: Core logic and object-oriented structure.
- **SDL2**: Window management, event handling, and rendering.
- **SDL2_image**: (Linked, though textures are primarily text-based in current logic).
- **SDL2_ttf**: Rendering text for tile values and UI.
- **CMake**: Primary build system for modern cross-platform support.
- **Makefile**: Legacy/alternative build system.

### Architecture
- **Driver.cpp**: Entry point. Handles command-line arguments (`getopt`), SDL initialization, and the main game loop.
- **Game.h / Game.cpp**: Core game logic. Manages the board state, tile merging, score calculation, and move validation.
- **gui.h / gui.cpp**: UI layer. Handles rendering the grid, tiles, start screen, and game-over screen.
- **LTexture.h / LTexture.cpp**: A wrapper class for `SDL_Texture`, providing utility methods for loading from text and files.
- **res/fonts/Arial.ttf**: Bundled font resource for UI rendering.

## Building and Running

### Dependencies
Install via Homebrew on macOS:
```bash
brew install sdl2 sdl2_image sdl2_ttf
```

### Build with CMake (Recommended)
```bash
mkdir -p build && cd build
cmake .. -DSOFTWARE_ACC=ON
make
./2048
```
*Note: `SOFTWARE_ACC` enables software acceleration, which can be useful if hardware acceleration issues occur on certain macOS environments.*

### Build with Makefile
```bash
make clean
make release CXXFLAGS="-DSOFTWARE_ACC"
./2048
```

### Running with Options
```bash
./2048 --size 4 --window 600
```
- `-s, --size`: Board dimensions (e.g., 4 for 4x4).
- `-w, --window`: Initial window pixel size.

## Development Conventions

### Coding Style
- **Naming**: Classes use `PascalCase` (e.g., `Game`, `LTexture`) or `snake_case` (e.g., `gui`). Methods and variables primarily use `snake_case`.
- **Memory Management**: Uses manual resource management in destructors (e.g., `SDL_DestroyRenderer`, `SDL_DestroyWindow`) following RAII patterns where applicable (like `LTexture`).
- **Standard Library**: Extensive use of `std::vector`, `std::unordered_map`, and `std::string`.

### Key Commands for Development
- **Testing**: `Board_test_1.cpp` exists for logic verification.
- **Cleaning**: `make clean` or `rm -rf build/*`.

### Troubleshooting
- If the game feels laggy or doesn't render, ensure `-DSOFTWARE_ACC` is passed during compilation to bypass potentially problematic hardware drivers on some macOS versions.
