cmake_minimum_required(VERSION 3.20)
project(w1 LANGUAGES CXX)

add_library(mathlib STATIC mathlib.cpp)
target_include_directories(mathlib PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_compile_features(mathlib PUBLIC cxx_std_20)
target_compile_options(mathlib PRIVATE -Wall -Wextra -Wpedantic)

add_executable(app main.cpp)
target_link_libraries(app PRIVATE mathlib)
target_compile_options(app PRIVATE -Wall -Wextra -Wpedantic)
