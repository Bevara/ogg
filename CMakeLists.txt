cmake_minimum_required(VERSION 3.7)
project(Filters)

include(filters.cmake)

add_definitions(-fpic)

#set(USE_DEBUG "-g")
#set(USE_FLAGS "${USE_DEBUG}")
#set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${USE_FLAGS}")
#set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} ${USE_FLAGS}")

set(CMAKE_BUILD_TYPE Release)
set(CMAKE_CXX_FLAGS "-O3 -Wall -Wextra")
set(CMAKE_C_FLAGS "-O3 -Wall -Wextra")

SET(ogg_SRC
        ${CMAKE_CURRENT_SOURCE_DIR}/dmx_ogg.c
        ${CMAKE_CURRENT_SOURCE_DIR}/av_parsers.c
)

SET(ogg_INCLUDE
        ${CMAKE_CURRENT_SOURCE_DIR}/include
)

SET(ogg_LIB
        ${CMAKE_CURRENT_SOURCE_DIR}/lib/libogg.a
)

add_filter(ogg
        "${ogg_SRC}"
        "${ogg_LIB}"
        []
        ""
        "${ogg_INCLUDE}"
        ""
        "1")
