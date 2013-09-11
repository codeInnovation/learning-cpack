cmake_minimum_required(VERSION 2.8)

project(demo)

add_subdirectory(bar)

set(includes
bar
)

include_directories(${includes})

set(srcs
main.cpp
)

add_executable(demo ${srcs})

set(libs
bar
)

target_link_libraries(demo ${libs})

install(TARGETS demo RUNTIME
DESTINATION bin
COMPONENT applications
)

set(CPACK_PACKAGE_DESCRIPTION_SUMMARY "demo prototype")
set(CPACK_PACKAGE_VENDOR "Me Inc.")
set(CPACK_PACKAGE_VERSION_MAJOR "1")
set(CPACK_PACKAGE_VERSION_MINOR "0")
set(CPACK_PACKAGE_VERSION_PATCH "0")

set(CPACK_COMPONENTS_ALL applications libraries)
set(CPACK_GENERATOR "DEB")
set(CPACK_DEB_COMPONENT_INSTALL ON)

# If we want to ignore the groups and package each target
#  as a separate component
#set(CPACK_COMPONENTS_IGNORE_GROUPS 1)

set(CPACK_DEBIAN_PACKAGE_MAINTAINER "myself")

include(CPack)


