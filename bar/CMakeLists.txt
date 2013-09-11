cmake_minimum_required(VERSION 2.8)

project(bar)

set(srcs
bar.cpp
bar.hpp
)

add_library(bar ${srcs})

install(TARGETS bar ARCHIVE
DESTINATION lib
COMPONENT libraries
)


