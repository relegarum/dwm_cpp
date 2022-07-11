cmake_minimum_required(VERSION 3.23)
project(DwmCpp)

add_executable(${PROJECT_NAME} dwm.cpp)
target_compile_definitions(${PROJECT_NAME} PUBLIC -DXINERAMA -DVERSION="1.0.0")

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++20 -Wall")

target_link_libraries(${PROJECT_NAME} "-L/usr/X11R6/lib -lX11 -lXinerama")

install(TARGETS ${PROJECT_NAME} DESTINATION /usr/local/bin)
