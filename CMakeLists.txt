cmake_minimum_required(VERSION 3.8)
project(zed-open-capture-ros)

#set(CMAKE_BUILD_TYPE Debug)
#set(CMAKE_PREFIX_PATH _PATH "/opt/ros/melodic;${CMAKE_MODULE_PATH}")

find_package(catkin REQUIRED
    COMPONENTS
        roscpp
        cv_bridge
        image_transport
        sensor_msgs
    )

find_package(OpenCV 4.5.2 REQUIRED)

#find_package(OpenMP)

include_directories(
    include
    ${catkin_INCLUDE_DIRS}
    /usr/local/include
    /usr/include/hidapi
    /home/pi/zed-open-capture
    /home/pi/zed-open-capture/examples/include
    /opt/ros/melodic/
    )

catkin_package(
    LIBRARIES
    CATKIN_DEPENDS
)

add_executable(${PROJECT_NAME} src/zed_node.cpp)
target_link_libraries(${PROJECT_NAME}
    ${catkin_LIBRARIES}
    /usr/local/lib/libzed_open_capture.so
    ${OpenCV_LIBS}
    )
