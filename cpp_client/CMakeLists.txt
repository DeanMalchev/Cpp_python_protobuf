cmake_minimum_required(VERSION 3.1...3.29)

project (cpp_client)

file(GLOB SOURCES ${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp)
add_executable(${PROJECT_NAME} ${SOURCES})
target_include_directories(${PROJECT_NAME} PUBLIC
                            ${CMAKE_CURRENT_SOURCE_DIR}/include
                           )
TARGET_LINK_LIBRARIES(${PROJECT_NAME} PUBLIC proto)