cmake_minimum_required(VERSION 2.8.3)
project(baxter_pickup_msgs)
INCLUDE(FindPkgConfig)

#find_package(Boost COMPONENTS date_time filesystem system thread REQUIRED)

find_package(catkin REQUIRED COMPONENTS
  message_generation
  roscpp
  rospy
  sensor_msgs
  std_msgs
  genmsg
  geometry_msgs
)


add_service_files(
  FILES
  BaxterIK.srv
)

add_message_files(
  FILES
  BlockArray.msg
  Block.msg
  Step.msg
  Plan.msg
)

generate_messages(DEPENDENCIES std_msgs sensor_msgs geometry_msgs)

catkin_package(
  INCLUDE_DIRS 
  LIBRARIES 
  CATKIN_DEPENDS roscpp rospy sensor_msgs std_msgs baxter_core_msgs message_runtime geometry_msgs
  DEPENDS system_lib 
)



