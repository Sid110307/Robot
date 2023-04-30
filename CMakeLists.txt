cmake_minimum_required(VERSION 3.20)
project(robot)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wextra")

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})
set(CMAKE_PREFIX_PATH "${CMAKE_PREFIX_PATH};/usr/share/libtorch")

set(SOURCE_FILES
  src/main.cpp
  src/environment.cpp
  src/agent.cpp
  src/neuralNetwork.cpp)

set(HEADERS
  src/include/environment.h
  src/include/agent.h
  src/include/neuralNetwork.h)

set(SHADERS
  shaders/vertex.glsl
  shaders/fragment.glsl)

add_executable(robot ${SOURCE_FILES} ${HEADERS} ${SHADERS})

find_package(Torch REQUIRED)
find_package(OpenGL REQUIRED)
find_package(GLEW REQUIRED)
find_package(glfw3 REQUIRED)

target_link_libraries(robot ${TORCH_LIBRARIES} ${OPENGL_LIBRARIES} GLEW::GLEW glfw)
target_include_directories(robot PRIVATE ${OPENGL_INCLUDE_DIRS} ${GLEW_INCLUDE_DIRS} ${GLFW_INCLUDE_DIRS})
target_compile_definitions(robot PRIVATE ${TORCH_DEFINITIONS})

