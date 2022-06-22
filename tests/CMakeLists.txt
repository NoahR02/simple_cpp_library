cmake_minimum_required(VERSION 3.15)
project(tests)

set(CMAKE_CXX_STANDARD 17)

add_executable(${PROJECT_NAME} main.cpp)

target_link_libraries(${PROJECT_NAME} PUBLIC Catch2::Catch2WithMain scpp)
add_test(NAME ${PROJECT_NAME} COMMAND ${PROJECT_NAME})