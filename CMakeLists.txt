cmake_minimum_required(VERSION 3.31)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_program(buildcache_program NAMES buildcache.exe)
if(buildcache_program)
  set(CMAKE_CXX_COMPILER_LAUNCHER ${buildcache_program})
  set(CMAKE_MSVC_DEBUG_INFORMATION_FORMAT
      "$<$<CONFIG:Debug,RelWithDebInfo>:Embedded>")
else()
  message(FATAL_ERROR "buildcache.exe not found")
endif()

project(HelloWorld LANGUAGES CXX)
add_executable(hello main.cpp)

target_precompile_headers(hello PRIVATE <print>)
