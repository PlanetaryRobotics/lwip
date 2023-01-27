cmake_minimum_required(VERSION 3.10)

project(lwipsrc LANGUAGES C)

set(LWIPSRC_DIR ${CMAKE_CURRENT_SOURCE_DIR})

set(LWIPSRC_INCLUDE 
    ${LWIPSRC_DIR}/include/compact/posix
    ${LWIPSRC_DIR}/include/compact/posix/arpa
    ${LWIPSRC_DIR}/include/compact/posix/net
    ${LWIPSRC_DIR}/include/compact/posix/sys
    ${LWIPSRC_DIR}/include/compact/stdc
    ${LWIPSRC_DIR}/include/lwip
    ${LWIPSRC_DIR}/include/lwip/apps
    ${LWIPSRC_DIR}/include/lwip/priv
    ${LWIPSRC_DIR}/include/lwip/prot
    ${LWIPSRC_DIR}/include/netif
    ${LWIPSRC_DIR}/include/netif/ppp
    ${LWIPSRC_DIR}/include/netif/ppp/polarssl
)

file(GLOB PORT_SOURCES 
    ${PORT_DIR}/freertos/sys_arch.c
)


target_include_directories(
    ${PROJECT_NAME}
    PUBLIC
    ${LWIPSRC_INCLUDE})

add_subdirectory(lwipapi)
add_subdirectory(lwipapps)
add_subdirectory(lwipcore)
add_subdirectory(lwipnetif)
