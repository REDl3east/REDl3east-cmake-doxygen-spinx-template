cmake_minimum_required(VERSION 3.0.0)
project(main VERSION 0.1.0)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

set(SRC_DIR
    ${CMAKE_SOURCE_DIR}/src
)

set(SOURCES
    ${SRC_DIR}/main.cpp
)
set(INCLUDE_DIR
  ${CMAKE_SOURCE_DIR}/include
)

set(INCLUDES
    ${INCLUDE_DIR}
)

add_executable(${CMAKE_PROJECT_NAME} ${SOURCES})
target_include_directories(${CMAKE_PROJECT_NAME} PUBLIC ${INCLUDES})
target_compile_features(${CMAKE_PROJECT_NAME} PRIVATE cxx_std_20)

list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_LIST_DIR}/cmake")
add_subdirectory(doc)