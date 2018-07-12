cmake_minimum_required(VERSION 2.8.3)
project(dscl_msgs)

## Add support for C++11, supported in ROS Kinetic and newer
# add_definitions(-std=c++11)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS
  message_generation
  geometry_msgs
  std_msgs
)

## Generate messages in the 'msg' folder
add_message_files(
  DIRECTORY msg
  FILES
  Imu9DOF.msg
  ImuBias.msg
  KvhImu.msg
  FilterOutput.msg
  )


## Generate added messages and services with any dependencies listed here
generate_messages(
  DEPENDENCIES
  geometry_msgs
  std_msgs
  )

catkin_package(
  CATKIN_DEPENDS geometry_msgs std_msgs message_generation
)

###########
## Build ##
###########

include_directories(
  ${catkin_INCLUDE_DIRS}
)

