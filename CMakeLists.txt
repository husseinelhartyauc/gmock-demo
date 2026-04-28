cmake_minimum_required(VERSION 3.10)
project(my_project)

set (CMAKE_CXX_STANDARD 17)
set (CHAKE_CXX_STANDARD_REQUIRED ON)

find_package(GTest REQUIRED)


enable_testing()

add_executable(mock UserRegistration.cpp  UserRegistration.hpp  test.cpp)
target_link_libraries(mock PRIVATE  GTest::gmock_main)

include(GoogleTest)
gtest_discover_tests(mock)
