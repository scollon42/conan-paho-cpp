project(test_package)
cmake_minimum_required(VERSION 2.8.11)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup()

## --- C++11 build flags ---

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

file(GLOB SOURCE_FILES *.cpp)

message("LIBS: ${CONAN_LIBS}")

add_executable(${PROJECT_NAME} ${SOURCE_FILES})
target_link_libraries(${PROJECT_NAME} ${CONAN_LIBS})