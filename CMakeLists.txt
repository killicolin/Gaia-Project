#===============================================================================
# Check if we are in the build dir
#===============================================================================
set(CMAKE_BINARY_DIR ${CMAKE_SOURCE_DIR}/build)
if ( NOT ${CMAKE_CURRENT_BINARY_DIR} STREQUAL ${CMAKE_BINARY_DIR})
    message(FATAL_ERROR "In-source builds not allowed. Please make a new directory \"build\" and run CMake from there. You may need to remove CMakeCache.txt and CMakeFiles.")
endif()

project(gaia)
cmake_minimum_required(VERSION 3.4.0)


#===============================================================================
# CMake Options
#===============================================================================
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin)

#===============================================================================
# Options
#===============================================================================
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14 -Werror -Wall")

#===============================================================================
# Dependencies
#===============================================================================
# find_package(Qt5 REQUIRED)

#===============================================================================
# Add sub-directories
#===============================================================================
include_directories(include)
add_subdirectory(src)
