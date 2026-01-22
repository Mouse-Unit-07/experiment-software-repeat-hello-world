#--------------------------------- FILE INFO ----------------------------------#
# Filename           : CMakeLists.txt                                          #
#                                                                              #
# Top level CMakeLists.txt file (for this software repo)                       #
#                                                                              #
#------------------------------------------------------------------------------#
cmake_minimum_required(VERSION 4.0.2)
project(repeat_hello_world_lib LANGUAGES C) # <== Name your software project

include(FetchContent)

# \/=== Add dependencies to other GitHub repos
# Example dependency on Hello World project:
FetchContent_Declare(
    print_hello_world
    GIT_REPOSITORY https://github.com/Mouse-Unit-07/experiment-software-hello-world
    GIT_TAG main
)
FetchContent_MakeAvailable(print_hello_world)

add_library(repeat_hello_world_lib STATIC) # <== Define your build target

# \/=== Add all interface directories (each w/ a CMakeLists.txt)
add_subdirectory(repeat_hello_world)

# \/=== Add all directories w/ header files
target_include_directories(repeat_hello_world_lib PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}/repeat_hello_world
)

# \/=== Link to other GitHub repos
# Example dependency on Hello World project:
target_link_libraries(repeat_hello_world_lib PUBLIC
    hello_world_lib
)