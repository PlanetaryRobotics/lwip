cmake_minimum_required(VERSION 3.10)

project(lwipapi LANGUAGES C)

set(LWIPAPI_DIR ${CMAKE_CURRENT_SOURCE_DIR})

file(GLOB LWIPAPI_SOURCE 
    ${LWIPAPI_DIR}/*.c)

add_library (
    ${PROJECT_NAME}
    ${LWIPAPI_SOURCE})

target_include_directories(
    ${PROJECT_NAME}
    PRIVATE
    ${LWIPSRC_INCLUDE})
