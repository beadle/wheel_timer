cmake_minimum_required(VERSION 3.5)
project(wheel_timer)

# config c++ flags
set(CMAKE_BUILD_TYPE "Debug")
set(CMAKE_CXX_COMPILER "g++")
set(CMAKE_CXX_FLAGS_DEBUG "-O0")
set(CMAKE_CXX_FLAGS_RELEASE "-O2")

set(CXX_FLAGS
-g
-std=c++11
-Wall
# -Wextra
# -Werror
# -Wconversion
# -Wno-unused-parameter
# -Wold-style-cast
# -Woverloaded-virtual
# -Wpointer-arith
# -Wshadow
# -Wwrite-strings
# -march=native
# -rdynamic
)
string(REPLACE ";" " " CMAKE_CXX_FLAGS "${CXX_FLAGS}")

# config output paths
set(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)
set(LIBRARY_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin/lib)

# add include paths
include_directories(/home/beadle/libs/boost_1_66_0)
include_directories(${PROJECT_SOURCE_DIR}/sources)

# defind macros
add_definitions(-DBOOST_ERROR_CODE_HEADER_ONLY)

add_subdirectory(sources)
add_subdirectory(examples)
