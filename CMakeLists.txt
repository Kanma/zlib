cmake_minimum_required(VERSION 2.6)
project(ZLIB)

# Options
if (NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE "Release" CACHE STRING "Choose the type of build, options are: None (CMAKE_CXX_FLAGS or CMAKE_C_FLAGS used) Debug Release RelWithDebInfo MinSizeRel." FORCE)
endif()

# Set the output path
if (NOT ATHENA_BINARY_DIR)
    set(ATHENA_BINARY_DIR "${ZLIB_BINARY_DIR}")
    set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY "${ZLIB_BINARY_DIR}/lib")
endif()

# List the source files
set(SRCS adler32.c
         compress.c
         crc32.c
         deflate.c
         gzio.c
         infback.c
         inffast.c
         inflate.c
         inftrees.c
         trees.c
         uncompr.c
         zutil.c
)

# Declaration of the library
add_library(zlib STATIC ${SRCS})
