# 2048 SDL C++

A sleek C++ implementation of the 2048 game using SDL2 for graphics. Optimized for macOS.

## Prerequisites

Ensure you have the required dependencies installed via [Homebrew](https://brew.sh/):

```bash
brew install sdl2 sdl2_image sdl2_ttf cmake
```

## Quick Start (macOS)

Build and run the game using CMake:

```bash
# Configure and build
cmake -S . -B build -DSOFTWARE_ACC=ON
cmake --build build

# Run
./build/2048
```

## Usage

You can customize the board size and window dimensions:

```bash
./build/2048 --size 4 --window 600
```

- `-s, --size`: Number of tiles per row/column (default: 4)
- `-w, --window`: Initial window size in pixels (default: 600)

## Controls

- **Arrow Keys**: Move tiles
- **Q / ESC**: Quit game

---
*Original code by Nicholas Metcalf. Updated for modern macOS support.*
