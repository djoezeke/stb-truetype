cmake_minimum_required(VERSION 3.16...4.1.1 FATAL_ERROR)

#--------------------------------------------------------------------
# Project and version.
#--------------------------------------------------------------------

project(Stb-TrueType)

if (CMAKE_CURRENT_SOURCE_DIR STREQUAL CMAKE_SOURCE_DIR)
  set(STB_IS_TOP_LEVEL ON)
else()
  set(STB_IS_TOP_LEVEL OFF)
endif()

#--------------------------------------------------------------------
# Configure variables for the library   
#--------------------------------------------------------------------

set(STB_LIB_NAME "stbtruetype")

set(STB_TARGET_NAME  ${STB_LIB_NAME})
set(STB_SOURCE_FILE "src/stb_truetype.c")
set(STB_INCLUDE_FILE "include/stb_truetype.h")

#--------------------------------------------------------------------
# Build library
#--------------------------------------------------------------------

add_library(${STB_LIB_NAME})
target_sources(${STB_LIB_NAME} PRIVATE ${STB_SOURCE_FILE})
target_include_directories(${STB_TARGET_NAME} PUBLIC
 $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>)
