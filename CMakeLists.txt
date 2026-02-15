cmake_minimum_required(VERSION 4.1.2)
project(test VERSION 0.1.0 LANGUAGES C CXX)

add_executable(test main.cpp)
find_package(fmt CONFIG REQUIRED)
target_link_libraries(test PRIVATE fmt::fmt)

find_package(imgui CONFIG REQUIRED)
target_link_libraries(test PRIVATE imgui::imgui)

# add_subdirectory(archlinux_clang21_supportCxx23_template)