cmake_minimum_required(VERSION 3.20)
project(texteditpro LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(FLTK REQUIRED CONFIG)      # assumes CMAKE_PREFIX_PATH points to your FLTK install

add_executable(texteditpro src/main.cpp)
target_link_libraries(texteditpro PRIVATE FLTK::FLTK)

if (MINGW)
  target_link_libraries(texteditpro PRIVATE gdi32 comctl32 ole32 uuid ws2_32)
endif()
