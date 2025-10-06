cmake_minimum_required(VERSION 3.16...4.1.1 FATAL_ERROR)

#--------------------------------------------------------------------
# Project and version.
#--------------------------------------------------------------------

project(Stb-TrueType)

if (CMAKE_CURRENT_SOURCE_DIR STREQUAL CMAKE_SOURCE_DIR)
  set(STBTRUETYPE_IS_TOP_LEVEL ON)
else()
  set(STBTRUETYPE_IS_TOP_LEVEL OFF)
endif()

#--------------------------------------------------------------------
# Configure variables for the library   
#--------------------------------------------------------------------

set(STBTRUETYPE_LIB_NAME "stbtruetype")

set(STBTRUETYPE_TARGET_NAME  ${STBTRUETYPE_LIB_NAME})
set(STBTRUETYPE_SOURCE_FILE "src/stb_truetype.c")
set(STBTRUETYPE_INCLUDE_FILE "include/stb_truetype.h")

#--------------------------------------------------------------------
# Build library
#--------------------------------------------------------------------

add_library(${STBTRUETYPE_LIB_NAME})
target_sources(${STBTRUETYPE_LIB_NAME} PRIVATE ${STBTRUETYPE_SOURCE_FILE})
target_include_directories(${STBTRUETYPE_TARGET_NAME} PUBLIC
 $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>)
