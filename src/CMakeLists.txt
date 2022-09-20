cmake_minimum_required(VERSION 3.18)

set( src 8x256_tables.c	crc.c)

set ( interface	slice_by_8/crc.h)

source_group( TREE ${CMAKE_SOURCE_DIR} FILES ${interface} ${src})

# Add intel_slice_by_8 to the project
add_library(intel_slice_by_8 STATIC ${interface} ${src})

# Include Interface directory to inclusion path
target_include_directories(intel_slice_by_8 PUBLIC . )

# Set output directory
set_target_properties(intel_slice_by_8 PROPERTIES ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/target/${CMAKE_SYSTEM_NAME}_${CMAKE_CXX_COMPILER_ID}_${CMAKE_SYSTEM_PROCESSOR}/${CMAKE_BUILD_TYPE})
