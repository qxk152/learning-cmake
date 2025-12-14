cmake_minimum_required(VERSION 2.8.4)

add_executable(curltest main.c)

#include_directories(/usr/local/include)
#target_link_libraries(curltest curl)
# 需要下载CURL对应的开发包 才有头文件
find_package(CURL)

if(CURL_FOUND)
  include_directories(${CURL_INCLUDE_DIR})
  target_link_libraries(curltest ${CURL_LIBRARY})
else(CURL_FOUND)
  message(FATAL_ERROR "CURL library not found")
endif(CURL_FOUND)

set(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)
