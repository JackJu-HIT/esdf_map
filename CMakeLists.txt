cmake_minimum_required(VERSION 2.8.3)
project(esdf_map)

set(CMAKE_CXX_FLAGS "-std=c++17 ${CMAKE_CXX_FLAGS} -O3 -Wall -pthread") # -Wextra -Werror
set(CMAKE_BUILD_TYPE "RELEASE")

include_directories( 
    include 
)



add_library( local_map STATIC
    src/sdf_map.cpp 
    )
add_executable(main main.cpp)
target_link_libraries( main  local_map)  


