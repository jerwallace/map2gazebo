cmake_minimum_required(VERSION 3.0.2)
project(map2gazebo)

find_package(catkin REQUIRED COMPONENTS rospy)

catkin_python_setup()

catkin_package(
  CATKIN_DEPENDS
    rospy
)

include_directories(
  include
  ${catkin_INCLUDE_DIRS}
)

catkin_install_python(PROGRAMS
  nodes/map2gazebo.py
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

install(DIRECTORY launch worlds config
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

