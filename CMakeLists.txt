# 设置最小cmake版本要求
cmake_minimum_required(VERSION 3.5)

# 设置项目信息
project(cpp_algo
        VERSION 0.1.0
        LANGUAGES CXX
)

# 设置当前cmake路径为主路径
set(CMAKE_HOME_PATH ${CMAKE_CURRENT_SOURCE_DIR})

# 自动生成版本文件
configure_file(${CMAKE_HOME_PATH}/src/version.h.in ${CMAKE_HOME_PATH}/inc/version.h)

# 设置安装路径
set(INSTALL_PATH ${CMAKE_CURRENT_SOURCE_DIR}/install)

# 头文件目录
set(HEADERS_PATH ${CMAKE_CURRENT_SOURCE_DIR}/inc)

# 源文件目录
set(SOURCES_PATH ${CMAKE_CURRENT_SOURCE_DIR}/src)

# 库源文件
add_subdirectory(src)

## 单元测试
add_subdirectory(test_googletest)

## 性能测试
add_subdirectory(test_benchmark)