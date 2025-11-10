cmake_minimum_required(VERSION 3.31)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(HelloWorld LANGUAGES CXX)
add_executable(hello main.cpp)

target_precompile_headers(hello PRIVATE <print>)
