cmake_minimum_required(VERSION 4.1.2)
project(test VERSION 0.1.0 LANGUAGES C CXX)

# 通过在 add_executable 中加入 WIN32 关键字，你告诉了编译器这是一个窗口程序，它会自动去寻找 WinMain 或 wWinMain
add_executable(test WIN32 main.cpp)
# 开启 Unicode 支持，这会让 Win32 API 宏自动指向宽字符版本
target_compile_definitions(test PRIVATE UNICODE _UNICODE)
find_package(fmt CONFIG REQUIRED)
target_link_libraries(test PRIVATE fmt::fmt)

find_package(imgui CONFIG REQUIRED)
target_link_libraries(test PRIVATE imgui::imgui)

target_link_libraries(test PRIVATE user32 gdi32 kernel32)
# add_subdirectory(archlinux_clang21_supportCxx23_template)