CMAKE_MINIMUM_REQUIRED(VERSION 3.0)

SET(PROJECT_NAME libnoiseutils)

INCLUDE_DIRECTORIES(AFTER include)

SET(lnuSources src/noiseutils.cpp)

ADD_LIBRARY(noiseutils SHARED ${lnuSources})
ADD_LIBRARY(noiseutils-static STATIC ${lnuSources})

TARGET_LINK_LIBRARIES(noiseutils noise)
# TARGET_LINK_LIBRARIES(noiseutils-static noise)

ADD_DEFINITIONS("-Wall -ansi -pedantic -O3")

INSTALL(DIRECTORY "${PROJECT_SOURCE_DIR}/include/noise" DESTINATION "${CMAKE_INSTALL_PREFIX}/include")

INSTALL(TARGETS noiseutils DESTINATION "${CMAKE_INSTALL_PREFIX}/lib")
INSTALL(TARGETS noiseutils-static DESTINATION "${CMAKE_INSTALL_PREFIX}/lib")
