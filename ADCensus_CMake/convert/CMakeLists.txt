CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

PROJECT(convert)

SET(SRC convert.cpp)

ADD_EXECUTABLE(convert ${SRC})

INCLUDE_DIRECTORIES(..)

IF(UNIX)
    SET_TARGET_PROPERTIES(convert PROPERTIES
                          COMPILE_FLAGS "-Wall -Wextra -Werror")
ENDIF(UNIX)

TARGET_LINK_LIBRARIES(convert IO)

INSTALL(FILES CMakeLists.txt ${SRC} DESTINATION src/convert)
