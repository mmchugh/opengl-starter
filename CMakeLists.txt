cmake_minimum_required(VERSION 3.2)
project(opengl-starter)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

add_subdirectory("glfw")

include_directories("${GLFW_SOURCE_DIR}/src"
                    "${GLFW_BINARY_DIR}/src"
                    ${glfw_INCLUDE_DIRS})

set(SOURCE_FILES main.cpp glew/glew.c ${glfw_SOURCES})

add_executable(opengl-starter ${SOURCE_FILES})
target_link_libraries(opengl-starter glfw ${GLFW_LIBRARIES})