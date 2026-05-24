cmake_minimum_required(VERSION 3.10)

project(cs221util)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Add the cs221util library
add_library(cs221util STATIC
        cs221util/PNG.cpp
        cs221util/PNG.h
        cs221util/RGBAPixel.cpp
        cs221util/RGBAPixel.h
        cs221util/RGB_HSL.h
        cs221util/lodepng/lodepng.cpp
        cs221util/lodepng/lodepng.h
)

target_include_directories(cs221util PUBLIC
        cs221util
        cs221util/lodepng
)

# Add imglist executable
add_executable(imglist imglist.cpp)
target_link_libraries(imglist cs221util)
