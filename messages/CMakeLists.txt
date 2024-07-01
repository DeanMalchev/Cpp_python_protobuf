cmake_minimum_required(VERSION 3.1...3.29)

set(OUT_PYTHON ${CMAKE_CURRENT_SOURCE_DIR}/../python_scripts/)

set(PROTO_FILE ${CMAKE_CURRENT_SOURCE_DIR}/kinMsg.proto)
include(FindProtobuf)
find_package(Protobuf REQUIRED)
protobuf_generate_cpp(PROTO_SRC PROTO_HEADER ${PROTO_FILE})
protobuf_generate_python(PROTO_PY ${PROTO_FILE} PROTOC_OUT_DIR ${OUT_PYTHON})
add_library(proto ${PROTO_HEADER} ${PROTO_SRC})
add_custom_target(pyproto ALL 
                  DEPENDS ${PROTO_PY})
target_include_directories(proto
                           INTERFACE ${PROTOBUF_INCLUDE_DIR}
                           INTERFACE ${CMAKE_CURRENT_BINARY_DIR}
                           )
target_link_libraries(proto ${PROTOBUF_LIBRARY})