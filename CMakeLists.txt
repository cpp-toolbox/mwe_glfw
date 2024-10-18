cmake_minimum_required(VERSION 3.10)
project(mwe_glfw)

# Specify the C++ standard
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_executable(mwe_glfw src/main.cpp src/window/window.cpp)

find_package(glad)
find_package(glfw3)
target_link_libraries(${PROJECT_NAME} glad::glad glfw)
