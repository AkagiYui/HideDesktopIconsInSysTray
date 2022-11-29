cmake_minimum_required(VERSION 3.23)
project(HideDesktopIconInSysTray)

set(CMAKE_CXX_STANDARD 23)
add_link_options(/SUBSYSTEM:WINDOWS)
#set(CMAKE_MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Debug>:DebugDLL>")

aux_source_directory(src DIR_SRCS)
file(GLOB_RECURSE SRC_FILES src/*.cpp src/*.h src/*.rc)
add_executable(HideDesktopIconInSysTray ${DIR_SRCS} ${SRC_FILES})
#add_executable(HideDesktopIconInSysTray  src/SysTrayDemo.rc src/resource.h src/stdafx.h  src/main.cpp )

add_subdirectory(src/toggle)
target_link_libraries(${PROJECT_NAME} Toggle)
