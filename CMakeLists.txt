cmake_minimum_required(VERSION 3.20)
project(LearnOpenGL)

set(CMAKE_CXX_STANDARD 17)

set(GLFW_DIR ${CMAKE_SOURCE_DIR}/external/glfw)
set(GLAD_DIR ${CMAKE_SOURCE_DIR}/external/glad)

include_directories(${GLFW_DIR}/include)
link_directories(${GLFW_DIR}/lib-arm64)

include_directories(${GLAD_DIR}/include)
file(GLOB GLAD_SRC ${GLAD_DIR}/src/glad.c)

add_executable(LearnOpenGL main.cpp ${GLAD_SRC})
target_link_libraries(LearnOpenGL libglfw.3.dylib)