project(stereoVision)
cmake_minimum_required(VERSION 3.16)


set(CMAKE_BUILD_TYPE "Release")
# 添加c++ 14标准支持
set(CMAKE_CXX_FLAGS "-std=c++14 -O2")

# Eigen
include_directories("/usr/include/eigen3")

# 寻找OpenCV库
find_package(OpenCV REQUIRED)

# 寻找Sophus库
find_package(Sophus REQUIRED)

# 寻找Pangolin库
find_package(Pangolin REQUIRED)

find_package(fmt REQUIRED)

add_executable(stereoVision stereoVision.cpp)
# 链接OpenCV、Sophus和Pangolin库
target_link_libraries(stereoVision ${OpenCV_LIBS} ${Sophus_LIBRARIES} ${Pangolin_LIBRARIES} fmt::fmt)