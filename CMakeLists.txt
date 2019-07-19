cmake_minimum_required(VERSION 2.8.3)
project(bag2mp4)

## Compile as C++11, supported in ROS Kinetic and newer
# add_compile_options(-std=c++11)

SET(OpenCV_DIR /usr/local/lib/cmake/opencv4/)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS
    roscpp
    rosbag
    OpenCV REQUIRED
)

###################################
## catkin specific configuration ##
###################################
## The catkin_package macro generates cmake config files for your package
## Declare things to be passed to dependent projects
## INCLUDE_DIRS: uncomment this if you package contains header files
## LIBRARIES: libraries you create in this project that dependent projects also need
## CATKIN_DEPENDS: catkin_packages dependent projects also need
## DEPENDS: system dependencies of this project that dependent projects also need
catkin_package(
  INCLUDE_DIRS 
  LIBRARIES bag2mp4
#  CATKIN_DEPENDS other_catkin_pkg
#  DEPENDS system_lib
)

###########
## Build ##
###########

## Specify additional locations of header files
## Your package locations should be listed before other locations
include_directories( include
  ${catkin_INCLUDE_DIRS}
  ${OpenCV_INCLUDE_DIRS} 
)

## Declare a cpp executable
add_executable(bag2mp4 src/bag2mp4.cpp)

## Specify libraries to link a library or executable target against
target_link_libraries(bag2mp4
  ${catkin_LIBRARIES}
  ${OpenCV_LIBS}
)
