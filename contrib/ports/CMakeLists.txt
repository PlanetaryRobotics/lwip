cmake_minimum_required(VERSION 3.10)

project(ports LANGUAGES C)

set(PORT_DIR ${CMAKE_CURRENT_SOURCE_DIR})

set(PORT_INCLUDE 
    ${PORT_DIR}/freertos/include/arch
)

file(GLOB PORT_SOURCES 
    ${PORT_DIR}/freertos/sys_arch.c)

add_library(
    ${PROJECT_NAME}
    ${PORT_SOURCES})

target_include_directories(
    ${PROJECT_NAME}
    PUBLIC
    ${PORT_INCLUDE}
    ${LWIPSRC_INCLUDE})
