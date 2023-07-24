cmake_minimum_required(VERSION 3.25)
project(lab02)

set(CMAKE_CXX_STANDARD 17)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fopenmp")

include(cmake/CPM.cmake)

#https://github.com/fmtlib/fmt.git
CPMAddPackage("gh:fmtlib/fmt#10.0.0")

#https://github.com/abdes/cryptopp-cmake.git
CPMAddPackage("gh:abdes/cryptopp-cmake#v8.8.0")

add_executable(lab02 main.cpp)

target_link_libraries(lab02 fmt::fmt benchmark::benchmark)

