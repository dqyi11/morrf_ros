# Declare the version of the CMake API for forward-compatibility
cmake_minimum_required(VERSION 2.8)

# Declare the name of the CMake Project
project(morrf_ros)

# Find Catkin
find_package(catkin REQUIRED COMPONENTS
             roscpp
             std_msgs
             geometry_msgs
             message_generation
            )

add_message_files (
  FILES
  int_array.msg
  morrf_init.msg
  multi_objective_path.msg
)

add_service_files(
  FILES
  morrf.srv
)

generate_messages (
  DEPENDENCIES
  std_msgs
  geometry_msgs
)

# Declare this project as a catkin package
catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES hello_world
   CATKIN_DEPENDS message_runtime
)

# Add the headers from roscpp
include_directories(include ${catkin_INCLUDE_DIRS}
                            )






