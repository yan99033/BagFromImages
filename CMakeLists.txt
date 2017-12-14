cmake_minimum_required(VERSION 2.8.3)

project(BagFromImages)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  sensor_msgs
  std_msgs
  rosbag
  cv_bridge
  image_transport
)

FIND_PACKAGE(OpenCV REQUIRED)

include_directories(
  ${catkin_INCLUDE_DIRS}
)

set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)

add_executable(${PROJECT_NAME} main.cc Thirdparty/DLib/FileFunctions.cpp)

target_link_libraries (${PROJECT_NAME} ${OpenCV_LIBS} ${catkin_LIBRARIES})
