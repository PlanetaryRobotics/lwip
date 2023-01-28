cmake_minimum_required(VERSION 3.10)

project(netifppp LANGUAGES C)

set(NETIFPPP_DIR ${CMAKE_CURRENT_SOURCE_DIR})

file(GLOB NETIFPPP_SOURCES
    ${NETIFPPP_DIR}/*.c
    ${NETIFPPP_DIR}/polarssl/*.c)

add_library (
    ${PROJECT_NAME}
    ${NETIFPPP_SOURCES})

target_include_directories(
    ${PROJECT_NAME}
    PUBLIC
    ${LWIPSRC_INCLUDE})
