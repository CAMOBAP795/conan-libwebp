cmake_minimum_required(VERSION 2.8.11)
project(cmake_wrapper)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup()

if (BUILD_SHARED_LIBS AND MSVC)
	# Building a dll
	add_definitions(-DWEBP_DLL)
endif()

include("CMakeListsOriginal.txt")
