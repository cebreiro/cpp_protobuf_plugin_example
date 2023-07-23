cmake_minimum_required (VERSION 3.8)

project(test_libprotobuf)

set(CMAKE_CXX_STANDARD 20)

add_executable (test_libprotobuf 
	test_libprotobuf.cpp
)

include(FetchContent)
FetchContent_Declare(
	protobuf
	GIT_REPOSITORY https://github.com/protocolbuffers/protobuf.git
	GIT_TAG v23.4
)
FetchContent_MakeAvailable(protobuf)

target_link_libraries(test_libprotobuf PUBLIC 
	protobuf::libprotoc
	protobuf::libprotobuf
)