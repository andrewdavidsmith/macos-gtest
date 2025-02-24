cmake_minimum_required(VERSION 3.28)

add_library(hello OBJECT
  hello.hpp
  hello.cpp)

add_executable(main)
target_sources(main PRIVATE main.cpp)

target_link_libraries(
  main PRIVATE
  hello
)
install(TARGETS main DESTINATION bin)
