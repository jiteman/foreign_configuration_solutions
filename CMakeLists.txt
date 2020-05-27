cmake_minimum_required( VERSION 3.7.1 )

project( foreign_configuration )

add_subdirectory( jmsd_tps_zlib )
add_subdirectory( jmsd_tps_png ) # depends on zlib

set( PNG_PNG_INCLUDE_DIR ${CMAKE_SOURCE_DIR}/jmsd_tps_png )
set( PNG_LIBRARY ${CMAKE_BINARY_DIR}/jmsd_tps_png/libpng.so )

include_directories( ${CMAKE_BINARY_DIR}/jmsd_tps_png )

add_subdirectory( jmsd_tps_freetype ) # depends on zlib, png
add_subdirectory( jmsd_tps_glut/freeglut ) # depends on png

