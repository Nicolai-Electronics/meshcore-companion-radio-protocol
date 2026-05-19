cmake_minimum_required(VERSION 3.5)
project(companion_protocol)

list(APPEND server_sources
    ../server.c
    ../src/mc_companion_serial_interface.c
    ../src/mc_companion_command_parser.c
)

add_executable(companion_server ${server_sources})

target_include_directories(
    companion_server PUBLIC
    ..
    ../include
)
