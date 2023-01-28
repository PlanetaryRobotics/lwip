cmake_minimum_required(VERSION 3.10)

project(lwipcore LANGUAGES C)

set(LWIPCORE_DIR ${CMAKE_CURRENT_SOURCE_DIR})

file(GLOB LWIPCORE_SOURCE
    ${LWIPCORE_DIR}/*.c 
    ${LWIPCORE_DIR}/ipv4/*.c
    ${LWIPCORE_DIR}/ipv6/*.c)

add_library (
    ${PROJECT_NAME}
    ${LWIPCORE_SOURCE})

target_include_directories(
    ${PROJECT_NAME}
    PUBLIC
    ${LWIPSRC_INCLUDE})

