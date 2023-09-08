cmake_minimum_required(VERSION 3.18.5)

set(NDK_PATH C:/Users/Administrator/AppData/Local/Android/Sdk/ndk/25.1.8937393)

set(CMAKE_SYSTEM_NAME ANDROID)
set(CMAKE_BUILD_TYPE Debug)
set(CMAKE_SYSTEM_VERSION 21)
set(ANDROID_PLATFORM 21)
set(ANDROID_SDK_TOOLS_VERSION 20)
set(ANDROID_ABI arm64-v8a)
set(ANDROID_NDK ${NDK_PATH})
set(CMAKE_TOOLCHAIN_FILE ${NDK_PATH}/build/cmake/android.toolchain.cmake)
set(ANDROID_SDK_ROOT ${NDK_PATH})

project(UE5Dumper)

set(CMAKE_CXX_STANDARD 17)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY
        ${CMAKE_SOURCE_DIR}/outputs/${CMAKE_ANDROID_ARCH_ABI}/
)

# Add debug flags to generate debugging information
set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -g")
set(CMAKE_C_FLAGS_DEBUG "${CMAKE_C_FLAGS_DEBUG} -g")

include_directories(.)

add_executable(UE5Dumper
        base.h
        dumper.cpp
        dumper.h
        engine.cpp
        engine.h
        file.cpp
        file.h
        generic.cpp
        generic.h
        main.cpp
        Mem.cpp
        Mem.h
)
