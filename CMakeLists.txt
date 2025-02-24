cmake_minimum_required(VERSION 3.28)
project(
  macos-gtest
  VERSION 0.1.0
  DESCRIPTION "macos-gtest"
  HOMEPAGE_URL https://example.com
  LANGUAGES CXX)

# GoogleTest requires at least C++14
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED yes)
set(CMAKE_CXX_EXTENSIONS off)  # prevents std=gnu++23
set(CMAKE_EXPORT_COMPILE_COMMANDS on)

enable_testing()
add_subdirectory(src)
add_subdirectory(tests)
