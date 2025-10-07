# SDL3 Starter App

A minimal starter project for building a desktop application with SDL3 in C/C++. It includes a simple build setup using CMake (recommended) and an alternative Makefile.

## Prerequisites

- A C/C++ compiler (GCC/Clang/MSVC)
- CMake (3.20+ recommended)
- SDL3 development libraries installed and discoverable by your toolchain

### Installing SDL3

- Windows (MSYS2): `pacman -S mingw-w64-<arch>-SDL3`
- Windows (vcpkg): `vcpkg install sdl3`
- macOS (Homebrew): `brew install sdl3`
- Linux (Debian/Ubuntu): `sudo apt install libsdl3-dev` (or build SDL3 from source if not available in your distribution)

Ensure your environment is set so that CMake or your compiler can find SDL3 headers and libraries (e.g., via CMAKE_PREFIX_PATH, pkg-config, or toolchain integration like vcpkg).