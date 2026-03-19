cmake_minimum_required(VERSION 3.10)
project(2048_SDL_cpp)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Add SDL2 CMake modules
list(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake/sdl2)

# Find SDL2
find_package(SDL2 REQUIRED)
find_package(SDL2_image REQUIRED)
find_package(SDL2_ttf REQUIRED)

# Source files
set(SOURCES
    Driver.cpp
    Game.cpp
    gui.cpp
    LTexture.cpp
)

add_executable(2048 ${SOURCES})

# Include and link
target_include_directories(2048 PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(2048 SDL2::Main SDL2::Image SDL2::TTF)

# Software Acceleration support via command line: -DCMAKE_CXX_FLAGS="-DSOFTWARE_ACC"
# or we can add it as an option
option(SOFTWARE_ACC "Enable software acceleration" OFF)
if(SOFTWARE_ACC)
    target_compile_definitions(2048 PRIVATE SOFTWARE_ACC)
endif()
