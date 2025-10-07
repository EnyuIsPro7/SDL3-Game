cmake_minimum_required(VERSION 3.16)
project(SDL3_Starter C)

# Use C (not C++) and set a sensible standard
set(CMAKE_C_STANDARD 17)
set(CMAKE_C_STANDARD_REQUIRED ON)

# Try to find SDL3 via its CMake config package (preferred)
find_package(SDL3 QUIET CONFIG)

# Fallback to pkg-config if CMake config was not found (common on Linux)
if (NOT SDL3_FOUND)
    find_package(PkgConfig REQUIRED)
    pkg_check_modules(SDL3 REQUIRED IMPORTED_TARGET sdl3)
    set(SDL3_LINK_TARGET PkgConfig::SDL3)
else()
    set(SDL3_LINK_TARGET SDL3::SDL3)
endif()

add_executable(SDL3_Starter src/main.c)

# Link against SDL3 imported target to get include paths and link flags
target_link_libraries(SDL3_Starter PRIVATE ${SDL3_LINK_TARGET})

# Link SDL3main only if the target exists (provided by the CMake SDL3 package)
if (TARGET SDL3::SDL3main)
    target_link_libraries(SDL3_Starter PRIVATE SDL3::SDL3main)
endif()