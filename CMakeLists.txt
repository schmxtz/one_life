cmake_minimum_required(VERSION 3.16)
project(one_life)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/$<CONFIGURATION>")
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/$<CONFIGURATION>")

add_subdirectory(vendored/SDL EXCLUDE_FROM_ALL)

add_executable(main WIN32 src/main.c)

# Link to the actual SDL3 library.
target_link_libraries(main PRIVATE SDL3::SDL3)