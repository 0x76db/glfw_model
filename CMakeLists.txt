cmake_minimum_required(VERSION 2.8)
###############################################################################
set(TARGET_NAME glfw_model)

###############################################################################
project(${TARGET_NAME})

LINK_DIRECTORIES(${CMAKE_SOURCE_DIR}/lib)

FILE(GLOB TARGET_SOURCE_FILES "*.cpp")
FILE(GLOB_RECURSE TARGET_HEADER_FILES "headers/*.h" "headers/*.hpp" "*.hpp")

add_executable(${TARGET_NAME} "${TARGET_SOURCE_FILES}" "${TARGET_HEADER_FILES}")

include_directories("${CMAKE_SOURCE_DIR}/deps/" "${CMAKE_SOURCE_DIR}/headers/")

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin)

###############################################################################
# LINKING
target_link_libraries(${TARGET_NAME} glad optimized glfw3 debug glfw3-d)

###############################################################################
# dependencies
add_subdirectory("${CMAKE_SOURCE_DIR}/deps/glad")