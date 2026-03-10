cmake_minimum_required(VERSION 3.14)
project(main VERSION 0.1.0)

set(CMAKE_EXPORT_COMPILE_COMMANDS 1)

include(FetchContent) # once in the project to include the module
FetchContent_Declare(
    stb
    URL https://github.com/nothings/stb/archive/refs/heads/master.zip
    DOWNLOAD_EXTRACT_TIMESTAMP TRUE
)
FetchContent_MakeAvailable(stb)
set(STB_INCLUDE ${stb_SOURCE_DIR})

include_directories(${STB_INCLUDE})
add_executable(main main.cpp)
