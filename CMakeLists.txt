cmake_minimum_required(VERSION 2.8.9)
project(gl_tut)
set (CMAKE_CXX_STANDARD 11)
find_package(Pangolin 0.4 REQUIRED)
include_directories(${PROJECT_SOURCE_DIR}/include
		    /usr/local/include
			${Pangolin_INCLUDE_DIRS})

#add_library(glad "${PROJECT_SOURCE_DIR}/include/glad/glad.h" "glad.c")

add_executable(sample_pan sample_pan.cpp)
target_link_libraries(sample_pan -lglfw3 -lGL -lX11 -lpthread -lXrandr -lXi -ldl  ${Pangolin_LIBRARIES})
