# Set the minimum required version of cmake for a project.
cmake_minimum_required(VERSION 3.10)

# Set your project name and specify the C and CXX languages.
project(drm-framebuffer LANGUAGES C)

# Optionally set the C standard explicitly.
set(CMAKE_C_STANDARD 99)
set(CMAKE_C_STANDARD_REQUIRED ON)

# Add compiler flags.
add_compile_options(-O0 -ggdb -pedantic -Wall)
include_directories(/usr/include/libdrm)

# Define the executable name and the list of source files that contribute to the executable.
add_executable(drm-framebuffer main.c framebuffer.c)

# Link the executable to the necessary libraries.
target_link_libraries(drm-framebuffer drm)

# Installation instructions
#include(GNUInstallDirs)
#install(TARGETS drm-framebuffer
#        RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR})

