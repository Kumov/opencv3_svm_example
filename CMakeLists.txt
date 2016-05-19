cmake_minimum_required (VERSION 2.6)

# Set the project name to the name of the folder
project ("opencvSvmExample")

#INCLUDE("$ENV{MUROX_CMAKE_MODULES}/FindOctave.cmake")

# Read the modules
find_package(OpenCV 3.1 REQUIRED)

# Set the include path
include_directories(
  ${OpenCV_INCLUDE_DIRS}
)

# add the executable
add_executable (opencvSvmExample main.cpp)

LINK_DIRECTORIES (
  ${OpenCV_LIBRARY_DIRS}
)

target_link_libraries (
  opencvSvmExample
  ${OpenCV_LIBRARIES}
)


SET ( CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -Wall -O0 -g -std=c++11" )
SET ( CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} -Wall -O3 -std=c++11" )  
