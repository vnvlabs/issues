
cmake_minimum_required(VERSION 3.6)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

project(Simple)
find_package(MPI REQUIRED)
find_package(Injection REQUIRED)

add_library(issues SHARED ${CMAKE_CURRENT_LIST_DIR}/issues.cpp)
link_vnv_file(issues ISSUES cpp)

install(TARGETS issues DESTINATION lib)

