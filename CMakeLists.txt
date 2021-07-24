cmake_minimum_required(VERSION 3.18)
project(pi86)

set(CMAKE_CXX_STANDARD 14)
SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14 -lwiringPi -pthread")

find_package(SDL2 REQUIRED)
find_library(wiringPi_LIB wiringPi)
include_directories(${SDL2_INCLUDE_DIRS})

add_executable(pi86 pi86.cpp cga.cpp drives.cpp timer.cpp vga.cpp x86.cpp)

target_link_libraries(pi86 ${SDL2_LIBRARIES} ${wiringPi_LIB})