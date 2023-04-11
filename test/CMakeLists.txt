cmake_minimum_required(VERSION 3.5)
project(testing CXX)

find_package(Threads REQUIRED)
find_package(cpprestsdk REQUIRED)


set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
# Set compiler flags with O0 ggdb sanitizer
# set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -O0 -ggdb -fsanitize=address -fsanitize=undefined -fno-sanitize-recover=all -fno-omit-frame-pointer")

# # Enable all warnings and treat them as errors
# set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wextra -Werror")

# Set include directory to ${CMAKE_WORK_DIR}/Release/include/cpprest/json.h
include_directories(${CMAKE_SOURCE_DIR}/Release/include)

add_executable(testing main.cpp)
target_link_libraries(testing PRIVATE cpprestsdk::cpprest)