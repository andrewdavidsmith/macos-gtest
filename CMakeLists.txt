cmake_minimum_required(VERSION 3.28)
project(
  macos-gtest
  VERSION 0.1.0
  DESCRIPTION "macos-gtest"
  HOMEPAGE_URL https://example.com
  LANGUAGES CXX)

# GoogleTest requires at least C++14
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(src)

# include(FetchContent)
# FetchContent_Declare(
#   googletest
#   URL https://github.com/google/googletest/archive/03597a01ee50ed33e9dfd640b249b4be3799d395.zip
# )
# FetchContent_MakeAvailable(googletest)

enable_testing()
find_package(GTest REQUIRED)

# Debugging output for gtest path and flags
message(STATUS "GoogleTest found at: ${GTEST_INCLUDE_DIRS}")
message(STATUS "GoogleTest library: ${GTEST_LIBRARIES}")

# Check if GTest was found
if (NOT GTest_FOUND)
    message(FATAL_ERROR "GTest not found. Please ensure it is installed or provide the correct path.")
else()
    message(STATUS "GTest is available, proceeding with the build.")
endif()

include(GoogleTest)
add_subdirectory(tests)
