cmake_minimum_required(VERSION 2.8.4)

project(hello)
# 添加子目录进行构建
# add_subdirectory 是 CMake 中用于组织大型项目的关键命令，它允许你将项目拆分成多个子目录，每个子目录有自己的 CMakeLists.txt 文件。
add_subdirectory(src)

# 安装普通文件到share/doc/cmake/hello-world-clear这个目录下
INSTALL(FILES COPYRIGHT README.md DESTINATION share/doc/cmake/hello-world-clear)

# 安装可执行脚本到bin这个目录下
INSTALL(PROGRAMS runhello.sh DESTINATION bin)

# 安装doc/ 下的文件到share/doc/cmake/hello-world-clear 如果是doc，则是安装这个目录本身
# install 本质是调用make install 命令 复制文件到指定位置
INSTALL(DIRECTORY doc/ DESTINATION share/doc/cmake/hello-world-clear)
