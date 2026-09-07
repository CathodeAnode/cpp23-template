cmake_minimum_required(VERSION 4.4...4.4)

# This experimental API has a version-specific activation key.
if(CMAKE_VERSION VERSION_GREATER_EQUAL 4.5)
    message(FATAL_ERROR "Use CMake 4.4.x; review the import-std gate before upgrading.")
endif()
set(CMAKE_EXPERIMENTAL_CXX_IMPORT_STD "f35a9ac6-8463-4d38-8eec-5d6008153e7d")

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED YES)
set(CMAKE_CXX_EXTENSIONS NO)

project(PROJECT_NAME VERSION 0.1.0 LANGUAGES CXX)

if(NOT 23 IN_LIST CMAKE_CXX_COMPILER_IMPORT_STD)
    message(FATAL_ERROR "The toolchain cannot import std. Install the standard library's module sources..")
endif()

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
add_executable(EXECUTABLE_NAME src/main.cpp)
set_target_properties(EXECUTABLE_NAME PROPERTIES
    CXX_STANDARD 23
    CXX_STANDARD_REQUIRED YES
    CXX_EXTENSIONS NO
    CXX_MODULE_STD YES
)
