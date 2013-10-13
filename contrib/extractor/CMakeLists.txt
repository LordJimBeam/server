# This code is part of MaNGOS. Contributor & Copyright details are in AUTHORS/THANKS.
#
# This file is free software; as a special exception the author gives
# unlimited permission to copy and/or distribute it, with or without
# modifications, as long as this notice is preserved.
#
# This program is distributed in the hope that it will be useful, but
# WITHOUT ANY WARRANTY, to the extent permitted by law; without even the
# implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.

cmake_minimum_required (VERSION 2.8)

project (MANGOS_MAP_EXTRACTOR)

include_directories (${MANGOS_MAP_EXTRACTOR_SOURCE_DIR}/loadlib ${MANGOS_MAP_EXTRACTOR_SOURCE_DIR}/../../dep/StormLib/src/)

add_subdirectory (loadlib)

# needs make -f Makefile.linux libStorm.a in ../../dep/StormLib/ before
link_directories (${MANGOS_MAP_EXTRACTOR_SOURCE_DIR}/loadlib ${MANGOS_MAP_EXTRACTOR_SOURCE_DIR}/../../dep/StormLib/)

add_executable (ad dbcfile.cpp System.cpp)

target_link_libraries (ad loadlib Storm bz2)
