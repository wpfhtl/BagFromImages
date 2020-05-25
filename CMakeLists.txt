cmake_minimum_required(VERSION 2.4.6)

project(bagfromimages)

find_package(catkin REQUIRED COMPONENTS roscpp std_msgs 
message_generation sensor_msgs image_transport cv_bridge rosbag)

FIND_PACKAGE(OpenCV REQUIRED)

include_directories(
  ${OpenCV_INCLUDE_DIRS}
  ${catkin_INCLUDE_DIRS}
)

add_executable(${PROJECT_NAME}
main.cc
Thirdparty/DLib/FileFunctions.cpp)

add_dependencies(${PROJECT_NAME} ${catkin_EXPORTED_TARGETS})
target_link_libraries(${PROJECT_NAME}  ${catkin_LIBRARIES} ${OpenCV_LIBRARIES})
