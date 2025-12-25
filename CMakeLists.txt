cmake_minimum_required(VERSION 3.12)
project(mwe_glfw)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)


file(GLOB_RECURSE SOURCES "src/*.cpp")

add_executable(${PROJECT_NAME} ${SOURCES})

foreach(_source ${SOURCES})
    set_property(DIRECTORY APPEND PROPERTY CMAKE_CONFIGURE_DEPENDS ${_source})
endforeach()

# automatically generated from conan install
find_package(glm)
find_package(spdlog)
find_package(fmt)
find_package(glad)
find_package(glfw3)
target_link_libraries(${PROJECT_NAME} glm::glm spdlog::spdlog fmt::fmt glad::glad glfw)
