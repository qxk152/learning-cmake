cmake_minimum_required(VERSION 2.8.4)

add_executable(main main.c)

# include_directories(../include/hello)
target_include_directories(main
    PUBLIC ../include/hello
)
message(STATUS ${PROJECT_BINARY_DIR})
# HELLO_LIB 存储找到的库路径的变量名
find_library(HELLO_LIB NAMES hello PATHS "${CMAKE_INSTALL_PREFIX}/lib/")

message(STATUS "Library path HELLO_LIB is " ${HELLO_LIB})

target_link_libraries(main ${HELLO_LIB})

set(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)
