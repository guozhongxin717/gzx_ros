cmake_minimum_required(VERSION 3.0.2)
project(task3)

add_compile_options(-std=c++11)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  sensor_msgs
)

find_package(PCL REQUIRED)

catkin_package(
INCLUDE_DIRS include
#  LIBRARIES task3
CATKIN_DEPENDS roscpp sensor_msgs
DEPENDS system_lib
)

include_directories(
  ${catkin_INCLUDE_DIRS}
  ${PCL_INCLUDE_DIRS}
)



add_executable(show_point_cloud src/show_point_cloud.cpp)

target_link_libraries(show_point_cloud
  ${catkin_LIBRARIES}
  ${PCL_LIBRARIES}
)
