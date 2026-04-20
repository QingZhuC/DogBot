cmake_minimum_required(VERSION 3.20)

project(main)

include_directories(includes)

aux_source_directory(./src SRC)
aux_source_directory(./tools TOOLS)

add_library(SRC_STATIC STATIC ${SRC})
add_library(TOOLS_STATIC STATIC ${TOOLS})

add_executable(${PROJECT_NAME} ${SRC})
target_link_libraries(${PROJECT_NAME} SRC_STATIC TOOLS_STATIC)