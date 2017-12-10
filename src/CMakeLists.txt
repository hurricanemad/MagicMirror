cmake_minimum_required(VERSION 3.6)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
set(CMAKE_CXX_STANDARD 11)

SET(CMAKE_MODULE_PATH module)

#set(OPENPOSE_INCLUDE_DIRS /home/dox/Algorithm/openpose-master/include)
#set(OPENPOSE_LIBS )

find_package(OpenCV REQUIRED)
find_package(Caffe REQUIRED)
#find_package(OpenPose REQUIRED)

ADD_DEFINITIONS(-DREENTRANT)
include_directories(${OpenCV_INCLUDE_DIRS})
include_directories(${Caffe_INCLUDE_DIRS})
#include_directories(${OpenPose_INCLUDE_DIRS})
include_directories(../lib)
link_directories(lib)

add_executable(videocapture main.cpp prefix.hpp)

target_link_libraries(videocapture ${OpenCV_LIBS} )
target_link_libraries(videocapture ${Caffe_LIBRARIES})
#target_link_libraries(videocapture ${OpenPose_LIBS})
target_link_libraries(videocapture MTCNN)

install(TARGETS videocapture RUNTIME DESTINATION install)
