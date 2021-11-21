cmake_minimum_required(VERSION 3.10)

set(TARGET hello_actions)

project(${TARGET})

set(CMAKE_DEBUG_POSTFIX d)
set(CMAKE_CXX_STANDARD 17)

if(MSVC)
else()
    set(CMAKE_CXX_FLAGS "-Wall -Wextra -Wshadow -pedantic")
endif()

set(SOURCES
    ${CMAKE_CURRENT_SOURCE_DIR}/main.cpp
)


add_executable(${TARGET} ${SOURCES})

set_target_properties(${TARGET} PROPERTIES DEBUG_POSTFIX ${CMAKE_DEBUG_POSTFIX})
target_compile_features(${TARGET} PRIVATE cxx_std_17)

install(TARGETS ${TARGET})

enable_testing()
add_test(NAME ${TARGET} COMMAND ${TARGET})
