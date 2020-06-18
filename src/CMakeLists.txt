cmake_minimum_required(VERSION 3.2)
project(argos-buzz-boilerplate)

find_package(Buzz REQUIRED)
include(UseBuzz)
set(BUZZ_BZZ_INCLUDE_DIR ${BUZZ_BZZ_INCLUDE_DIR} ${CMAKE_SOURCE_DIR})

add_subdirectory(hexagon)
add_subdirectory(square)
add_subdirectory(gradient)