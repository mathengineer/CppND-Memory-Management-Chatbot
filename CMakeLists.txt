cmake_minimum_required(VERSION 3.11.3)

set(CMAKE_CXX_STANDARD 17)
set(wxWidgets_ROOT_DIR "/usr/local/Cellar/wxmac/3.0.4_2")
set(wxWidgets_LIB_DIR "/usr/local/Cellar/wxmac/3.0.4_2/lib")
set(CMAKE_BUILD_TYPE Debug)

project(Membot)

find_package(wxWidgets REQUIRED COMPONENTS core base)
include(${wxWidgets_USE_FILE})

file(GLOB project_SRCS src/*.cpp)

add_executable(membot ${project_SRCS})
target_link_libraries(membot ${wxWidgets_LIBRARIES})
target_include_directories(membot PRIVATE ${wxWidgets_INCLUDE_DIRS})
