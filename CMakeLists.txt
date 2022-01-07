cmake_minimum_required(VERSION 3.15)
project(cpp-project
        LANGUAGES C CXX
        VERSION 0.1.0
        DESCRIPTION "Description for C++ project")

set(CMAKE_CXX_STANDARD 20)

add_subdirectory(src)

option(BUILD_TESTS "Also build the tests" ON)
if (BUILD_TESTS)
    add_subdirectory(tests)
endif()
