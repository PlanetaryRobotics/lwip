cmake_minimum_required(VERSION 3.10)

project(lwipapps LANGUAGES C)

set(LWIPAPPS_DIR ${CMAKE_CURRENT_SOURCE_DIR})

file(GLOB LWIPAPPS_SOURCE
    ${LWIPAPPS_DIR}/sntp/*.c)

add_library (
    ${PROJECT_NAME}
    ${LWIPAPPS_SOURCE})

target_include_directories(
    ${PROJECT_NAME}
    PUBLIC
    ${LWIPSRC_INCLUDE})
