# CMakeList.txt: rtsp 的 CMake 项目，在此处包括源代码并定义
# 项目特定的逻辑。
#
cmake_minimum_required (VERSION 3.8)

project ("rtsp")
aux_source_directory(src/xop/ XOP_SRCS)
aux_source_directory(src/net/ NET_SRCS)
# 将源代码添加到此项目的可执行文件。
link_libraries(-lrt -pthread -lpthread -ldl -lm  -std=c++11)
add_executable (rtsp ${XOP_SRCS} ${NET_SRCS} "src/3rdpart/md5/md5.hpp" "rtsp_h264_file.cpp")
# TODO: 如有需要，请添加测试并安装目标。
