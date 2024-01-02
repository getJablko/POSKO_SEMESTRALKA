cmake_minimum_required(VERSION 3.18)
project(socket_server_src C)

set(CMAKE_C_STANDARD 11)

find_package(Threads REQUIRED)

include_directories(socket_server_src)
include_directories(socket_server_src/pos_sockets)

add_executable(socket_server_src
        socket_server_src/pos_sockets/active_socket.c
        socket_server_src/pos_sockets/active_socket.h
        socket_server_src/pos_sockets/char_buffer.c
        socket_server_src/pos_sockets/char_buffer.h
        socket_server_src/pos_sockets/linked_list.h
        socket_server_src/pos_sockets/passive_socket.c
        socket_server_src/pos_sockets/passive_socket.h
        socket_server_src/buffer.h
        socket_server_src/main.c)

target_link_libraries(socket_server_src PRIVATE Threads::Threads)