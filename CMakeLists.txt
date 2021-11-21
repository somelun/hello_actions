cmake_minimum_required(VERSION 3.10)

project(hello_actions)

set(CMAKE_CXX_STANDARD 17)

if(MSVC)
else()
    set(CMAKE_CXX_FLAGS "-Wall -Wextra -Wshadow -pedantic")
endif()

set(SOURCES
    ${CMAKE_CURRENT_SOURCE_DIR}/main.cpp
)

set(TARGET hello_actions)

add_executable(${TARGET} ${SOURCES} ${HEADERS})
