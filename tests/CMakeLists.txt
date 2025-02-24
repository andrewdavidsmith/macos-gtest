add_executable(
  hello_test
  hello_test.cpp
)
target_link_libraries(
  hello_test
  GTest::GTest
  GTest::Main
)
target_include_directories(hello_test PRIVATE ${PROJECT_SOURCE_DIR}/src)

gtest_discover_tests(hello_test)
