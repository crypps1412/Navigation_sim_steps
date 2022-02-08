cmake_minimum_required(VERSION 3.0.2)
project(gazebo_autoscan)

find_package(catkin REQUIRED COMPONENTS
  roscpp # to compile c++ source code
  gazebo_ros
)

# To link to file exe when using ros command
catkin_package()

# Read include folders (.h files) from this package and catkin
include_directories(
  include
  ${catkin_INCLUDE_DIRS}
)

# Compile and turn source code into executable file
add_executable(autoscan src/autoscan.cpp)
# Add catkin library path to exe file
target_link_libraries(autoscan ${catkin_LIBRARIES})
