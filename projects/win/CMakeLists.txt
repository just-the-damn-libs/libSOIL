cmake_minimum_required (VERSION 2.6)
project (SOIL C)

SET(CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS ON)

IF(NOT CMAKE_BUILD_TYPE)
    SET(CMAKE_BUILD_TYPE "Release")
ENDIF(NOT CMAKE_BUILD_TYPE)

add_definitions (-D_CRT_SECURE_NO_WARNINGS )
include_directories (../..)
add_library (soil SHARED
    ../../SOIL.c
    ../../SOIL.h
    ../../image_DXT.c
    ../../image_DXT.h
    ../../image_helper.c
    ../../image_helper.h
    ../../stb_image_aug.c
    ../../stb_image_aug.h
    ../../stbi_DDS_aug.h
    ../../stbi_DDS_aug_c.h)
target_link_libraries(soil opengl32.lib)
