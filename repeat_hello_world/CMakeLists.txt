#--------------------------------- FILE INFO ----------------------------------#
# Filename           : CMakeLists.txt                                          #
#                                                                              #
# CMakeLists.txt file for repeat_hello_world source files                      #
#                                                                              #
#------------------------------------------------------------------------------#
# \/=== Add all .c files to your build target here
target_sources(repeat_hello_world_lib PRIVATE # <=== Rename to your build target
    ${CMAKE_CURRENT_LIST_DIR}/repeat_hello_world.c
)

target_include_directories(repeat_hello_world_lib PUBLIC  # <=== Rename to your build target
    ${CMAKE_CURRENT_LIST_DIR}
)
