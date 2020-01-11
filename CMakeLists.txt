cmake_minimum_required(VERSION 3.0)
project(zlib_test)

set(CMAKE_C_STANDARD 99)
set(CFLAGS -g)

find_package(ZLIB REQUIRED)
if (FOUND)
    include_directories(${PROJECT_NAME} ${ZLIB_INCLUDE_DIRS})
    target_link_libraries(${PROJECT_NAME} ${ZLIB_LIBRARIES})
endif()

set(ZLIB_TEST_SOURCES main.c)

add_executable(zlib_test main.c)