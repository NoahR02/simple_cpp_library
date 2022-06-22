cmake_minimum_required(VERSION 3.15)
project(scpp
  VERSION 0.0
  DESCRIPTION "Simple C++ Library."
  LANGUAGES CXX
)
set(CMAKE_CXX_STANDARD 17)

set(LIB_FILES scpp/DynamicArray.h)

add_library(${PROJECT_NAME} STATIC ${LIB_FILES})
# This can be removed in the future when we have a cpp file.
set_target_properties(${PROJECT_NAME} PROPERTIES LINKER_LANGUAGE CXX)
target_include_directories(${PROJECT_NAME} PUBLIC ./)

# Testing
# Only Enable The Tests If We Are Building The Project(not a user).
if(${CMAKE_SOURCE_DIR} STREQUAL ${CMAKE_CURRENT_SOURCE_DIR})
  include(CTest)
  add_subdirectory(third-party)
  add_subdirectory(tests)
  enable_testing()
endif ()
