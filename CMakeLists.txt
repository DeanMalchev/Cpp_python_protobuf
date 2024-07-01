cmake_minimum_required(VERSION 3.1...3.29)


set(CMAKE_BUILD_TYPE Release)

list( APPEND CMAKE_CXX_FLAGS "-Wno-deprecated-declarations ${CMAKE_CXX_FLAGS}")

project (Protobuf_cpp_python CXX)
set(CMAKE_CXX_STANDARD 17) 
set(CMAKE_CXX_STANDARD_REQUIRED on)
set(CMAKE_EXE_LINKER_FLAGS "-Wl,--copy-dt-needed-entries")

include(CMakePrintHelpers)

add_subdirectory(messages)
add_subdirectory(cpp_server)
add_subdirectory(cpp_client)









