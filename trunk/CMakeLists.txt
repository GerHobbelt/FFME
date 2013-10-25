#---------------------------------------------------#
#          CMake Project Configuration              #
#---------------------------------------------------#
# CMake will issue a warning if you don't set this
CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

if(COMMAND cmake_policy)
     cmake_policy(SET CMP0003 NEW)
endif(COMMAND cmake_policy)

SET(PROJECT_NAME "kptsComparison" CACHE STRING "kptsComparison")
PROJECT( ${PROJECT_NAME} )

#---------------------------------------------------#
#              OpenCV Configuration                 #
#---------------------------------------------------#
# Automatically find OpenCV files
FIND_PACKAGE( OpenCV REQUIRED )


SET ( CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/CMakeModules )
SET ( CMAKE_DEBUG_POSTFIX d )
SET ( LIBRARY_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin/ CACHE PATH "Single output directory for building all libraries." FORCE )
SET ( EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin/ CACHE PATH "Single output directory for building all executables." FORCE )


INCLUDE_DIRECTORIES( ${OpenCV_INCLUDE_DIRS})


set(SOURCE_FILES
	main.cpp
	FFME.cpp
	FFME.h
)
set(HEADER_FILES
)

ADD_EXECUTABLE( ${PROJECT_NAME} ${SOURCE_FILES} ${HEADER_FILES})

TARGET_LINK_LIBRARIES( ${PROJECT_NAME} ${OpenCV_LIBS})
