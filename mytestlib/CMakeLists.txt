cmake_minimum_required(VERSION 3.15)
project(mytestlib)

set(CMAKE_CXX_STANDARD 14)

add_library(mytestlib SHARED library.cpp library.h)