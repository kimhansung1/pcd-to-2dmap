cmake_minimum_required(VERSION 3.10)
project(pcd_to_2dmap)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(PCL REQUIRED)
find_package(OpenCV REQUIRED)
find_package(Boost REQUIRED COMPONENTS filesystem program_options)

add_executable(pcd_to_2dmap src/main.cpp)


target_include_directories(pcd_to_2dmap PRIVATE ${PCL_INCLUDE_DIRS} ${OpenCV_INCLUDE_DIRS} ${Boost_INCLUDE_DIRS})
target_link_libraries(pcd_to_2dmap PRIVATE ${PCL_LIBRARIES} ${OpenCV_LIBRARIES} Boost::filesystem Boost::program_options)

