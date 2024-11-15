cmake_minimum_required(VERSION 3.8)
project(templatesbook)
  

# CC=clang-18 CXX=clang++-18 CC_LD=lld cmake --build /home/usr/learning/Template-Metaprogramming-with-CPP/build.ninja --config Release --target all

if(MSVC)
  message(status "Setting MSVC flags")
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /EHc /Zc:__cplusplus /std:c++latest")
  add_definitions(-D_CRT_SECURE_NO_WARNINGS)
else()
  message(status "Setting GCC/Clang flags")
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++20 -fexceptions -g -Wall" )
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS}  -Wno-unused-variable -Wno-unused-local-typedefs -Wno-unused-but-set-variable")
  # set(CC_LD lld)
  # set(cpp_args "-stdlib=libc++ -fexperimental-library" )
  # set(cpp_link_args "-stdlib=libc++ -fexperimental-library")
endif()

find_package(Boost REQUIRED)
include_directories(${Boost_INCLUDE_DIRS})

add_subdirectory(src/chapter_01)
add_subdirectory(src/chapter_02)
add_subdirectory(src/chapter_03)
add_subdirectory(src/chapter_04)
add_subdirectory(src/chapter_05)
add_subdirectory(src/chapter_06)
add_subdirectory(src/chapter_07)
add_subdirectory(src/chapter_08)
add_subdirectory(src/chapter_09)
