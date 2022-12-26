cmake_minimum_required(VERSION 3.18.1)

project("gifdemo")

file(GLOB_RECURSE GIF_LIB ${CMAKE_SOURCE_DIR}/giflib/*.*)

add_library(
        gifdemo
        SHARED
        ${GIF_LIB} # 添加giflib
        native-lib.cpp)

find_library(
        log-lib
        log)

target_link_libraries(
        gifdemo
        jnigraphics # 增加依赖
        ${log-lib})