cmake_minimum_required(VERSION 2.6)

project(parg C)

option(BUILD_TEST "Build unit test" ON)

include_directories(${PROJECT_SOURCE_DIR})

add_library(parg parg.c parg.h)

if(BUILD_TEST)
	add_executable(test_parg test/test_parg.c test/greatest.h parg.h)
	target_link_libraries(test_parg parg)

	enable_testing()
	add_test(test_parg test_parg)
endif()