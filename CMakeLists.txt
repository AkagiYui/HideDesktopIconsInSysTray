cmake_minimum_required(VERSION 3.23)
project(HideDesktopIconInSysTray)

set(CMAKE_CXX_STANDARD 23)

aux_source_directory(src DIR_SRCS)

#add_link_options(/SUBSYSTEM:WINDOWS)

set(CMAKE_MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Debug>:DebugDLL>")

add_executable(HideDesktopIconInSysTray ${DIR_SRCS})
