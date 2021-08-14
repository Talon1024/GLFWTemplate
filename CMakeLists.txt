cmake_minimum_required(VERSION 3.10)

project(template)

set(GLAD_SOURCES glad/src/glad.c)
set(CMAKE_CXX_STANDARD 11)

add_executable(template main.cpp ${GLAD_SOURCES})

set(GLFW_BUILD_EXAMPLES 0)
set(GLFW_BUILD_TESTS 0)
add_subdirectory(glfw)

target_include_directories(template PRIVATE glfw/include/GLFW glad/include)

target_link_libraries(template glfw)
