cmake_minimum_required(VERSION 2.8)
###############################################################################
set(TARGET_NAME glad)

###############################################################################
project(${TARGET_NAME})

LINK_DIRECTORIES(${CMAKE_SOURCE_DIR}/lib)

FILE(GLOB TARGET_SOURCE_FILES "*.c")
FILE(GLOB_RECURSE TARGET_HEADER_FILES "*.h")

include_directories("${CMAKE_SOURCE_DIR}/..")

add_library(${TARGET_NAME} "${TARGET_SOURCE_FILES}" "${TARGET_HEADER_FILES}")