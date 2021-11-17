cmake_minimum_required( VERSION 3.0 )

project( ush LANGUAGES C VERSION 0.1.0 )

set( CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib )
set( CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib )
set( CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin )

enable_testing( )

add_subdirectory( ${PROJECT_SOURCE_DIR}/src )

add_library(
    ush-lib
    STATIC
    ${USH_SRC_FILES}
)

target_include_directories(
    ush-lib
    PUBLIC
    ${USH_INC_DIRS}
)