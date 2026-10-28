cmake_minimum_required(VERSION 3.16)
project(DuplicateFinder CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

file(GLOB_RECURSE SOURCES CONFIGURE_DEPENDS src/*.cpp)

add_executable(dupfinder ${SOURCES})
target_include_directories(dupfinder PRIVATE include)

if(MSVC)
  target_compile_options(dupfinder PRIVATE /W4)
else()
  target_compile_options(dupfinder PRIVATE -Wall -Wextra)
endif()
