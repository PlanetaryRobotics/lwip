cmake_minimum_required(VERSION 3.10)

project(lwipnetif LANGUAGES C)

set(LWIPNETIF_DIR ${CMAKE_CURRENT_SOURCE_DIR})

file(GLOB LWIPNETIF_SOURCE 
    ${LWIPNETIF_DIR}/*.c)

add_library (
    ${PROJECT_NAME}
    ${LWIPNETIF_SOURCE})

target_include_directories(
    ${PROJECT_NAME}
    PRIVATE
    ${LWIPSRC_INCLUDE})

add_subdirectory(ppp)
