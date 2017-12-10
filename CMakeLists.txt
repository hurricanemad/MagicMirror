cmake_minimum_required(VERSION 3.6)
project(videocapture)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
set(CMAKE_CXX_STANDARD 11)

add_subdirectory(src bin)
add_subdirectory(lib lib)
install(DIRECTORY model DESTINATION install)

