cmake_minimum_required(VERSION 3.8)
set(TARGET "StereoSGBMPclTest")
project(${TARGET})
set(EVAR "StereoMatch")
# required packages
find_package(OpenCV REQUIRED)
find_package(PCL REQUIRED)
FILE(GLOB SOURCES src/stereo_match.cpp src/*.h)
include_directories(${OpenCV_INCLUDE_DIRS})
include_directories(../inc)
include_directories(${PCL_INCLUDE_DIRS})
link_directories(${PCL_LIBRARY_DIRS})
add_definitions(${PCL_DEFINITIONS})
add_executable(${EVAR} ${SOURCES})
target_link_libraries (${EVAR} ${PCL_LIBRARIES})
target_link_libraries(${EVAR} ${OpenCV_LIBS})
