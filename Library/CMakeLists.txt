cmake_minimum_required(VERSION 3.20)

# define the project name
project(libraries VERSION 1.0 LANGUAGES C)

# define the c standard version
set(CMAKE_C_STANDARD 11)
set(CMAKE_C_STANDARD_REQUIRED True)


add_library(Library_name STATIC src/function.c)

target_include_directories(Library_name PUBLIC include)

add_executable(exec_name src/main.c)
target_include_directories(exec_name PUBLIC include)

target_link_libraries(exec_name PRIVATE Library_name)