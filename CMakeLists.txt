cmake_minimum_required(VERSION 2.8.3)
project(cantcoap)

set(CMAKE_BUILD_TYPE "Release")
set(CMAKE_CXX_FLAGS "-std=c++11")
set(CMAKE_CXX_FLAGS_RELEASE "-O3 -Wall -g")


include_directories(
    ${PROJECT_SOURCE_DIR}/src
)

add_library(${PROJECT_NAME} SHARED
    src/cantcoap.cpp
    src/nethelper.c
)

add_executable(server
    demo/server.cpp
)

add_executable(client
    demo/client.cpp
)

target_link_libraries(server cantcoap)
target_link_libraries(client cantcoap) 
