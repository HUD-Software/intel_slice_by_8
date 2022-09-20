cmake_minimum_required(VERSION 3.18)

set( src 8x256_tables.c	crc.c)

set ( interface	slice_by_8/crc.h)

source_group( TREE ${CMAKE_SOURCE_DIR} FILES ${interface} ${src})

add_library(slice_by_8 STATIC ${interface} ${src})

target_include_directories(slice_by_8 PUBLIC . )