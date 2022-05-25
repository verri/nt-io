cmake_minimum_required(VERSION 3.0)

if(DEFINED NT_PROJECT_IO_GUARD)
    if(NOT NT_PROJECT_IO_GUARD STREQUAL ${CMAKE_CURRENT_BINARY_DIR})
        return()
    endif()
else()
    set(NT_PROJECT_IO_GUARD ${CMAKE_CURRENT_BINARY_DIR} CACHE INTERNAL "ProjectIO guard")
endif()

project(nt_io VERSION 1.0)

add_library(nt_io src/io.cpp)

target_compile_features(nt_io PRIVATE cxx_std_14)
target_include_directories(nt_io PUBLIC include/)
