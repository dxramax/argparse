cmake_minimum_required(VERSION 3.5.0)
project(argparse)

SET(SRC_FILES
	argparse.c
	argparse.h
)

if(WIN32)
 #    LIST(APPEND LIBS "m" "Shlwapi")
elseif(${CMAKE_SYSTEM_NAME} MATCHES "Darwin")
    LIST(APPEND LIBS "m")
elseif(${CMAKE_SYSTEM_NAME} MATCHES "Linux")
    LIST(APPEND LIBS "m" "rt")
endif()

ADD_LIBRARY(argparse ${SRC_FILES})

target_link_libraries(argparse ${LIBS})