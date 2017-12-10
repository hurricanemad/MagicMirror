cmake_minimum_required(VERSION 3.6)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
set(CMAKE_CXX_STANDARD 11)

find_package(OpenCV REQUIRED)
find_package(Caffe REQUIRED)

#message(FATAL_ERROR ${Caffe_INCLUDE_DIRS})
include_directories(${OpenCV_INCLUDE_DIRS})
include_directories(${Caffe_INCLUDE_DIRS})

set(SOURCE_FILES MTCNN.cpp)
add_library(MTCNN SHARED ${SOURCE_FILES})

target_link_libraries(MTCNN ${OpenCV_LIBS} )
target_link_libraries(MTCNN ${Caffe_LIBRARIES})

install(TARGETS MTCNN DESTINATION install/lib)
