# GTest include code would
# go somewhere in here
cmake_minimum_required(VERSION 3.28)

add_library(GTest::GTest INTERFACE IMPORTED)
target_link_libraries(GTest::GTest INTERFACE gtest gtest_main)

add_executable(hello_test hello_test.cpp)

target_link_libraries(hello_test
  PRIVATE
  GTest::GTest
  hello)

target_include_directories(hello_test PRIVATE ${PROJECT_SOURCE_DIR}/src)

add_test(hello_gtests hello_test)
include(GoogleTest)
gtest_discover_tests(hello_test)
