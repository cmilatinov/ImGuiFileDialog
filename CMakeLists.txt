# Minimum Version
cmake_minimum_required(VERSION 3.20)

# C++ standard
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Required libraries
find_package(imgui CONFIG REQUIRED)

# Clump source files from src
file(GLOB_RECURSE FILE_DIALOG_SRC "ImGuiFileDialog.cpp")

# Library
add_library("FileDialog" STATIC ${FILE_DIALOG_SRC})

# Link target
target_link_libraries("FileDialog" PUBLIC imgui::imgui IconFonts)
target_include_directories("FileDialog" PUBLIC "./")