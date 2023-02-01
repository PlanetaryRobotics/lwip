cmake_minimum_required(VERSION 3.10)

project(ports LANGUAGES C)

set(PORT_DIR ${CMAKE_CURRENT_SOURCE_DIR})

set(PORT_INCLUDE 
    ${PORT_DIR}/freertos/include/arch
)

file(GLOB PORT_SOURCES 
    ${PORT_DIR}/freertos/sys_arch.c
    ${PORT_DIR}/../../src/include/compact/posix
    ${PORT_DIR}/../../src/include/compact/posix/arpa
    ${PORT_DIR}/../../src/include/compact/posix/net
    ${PORT_DIR}/../../src/include/compact/posix/sys
    ${PORT_DIR}/../../src/include/compact/stdc
    ${PORT_DIR}/../../src/include/lwip
    ${PORT_DIR}/../../src/include/lwip/apps
    ${PORT_DIR}/../../src/include/lwip/priv
    ${PORT_DIR}/../../src/include/lwip/prot
    ${PORT_DIR}/../../src/include/netif
    ${PORT_DIR}/../../src/include/netif/ppp
    ${PORT_DIR}/../../src/include/netif/ppp/polarssl)

add_library(
    ${PROJECT_NAME}
    ${PORT_SOURCES})

target_include_directories(
    ${PROJECT_NAME}
    PUBLIC
    ${PORT_INCLUDE}
    ${LWIPSRC_INCLUDE})
