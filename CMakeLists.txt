project(hello)
cmake_minimum_required(VERSION 2.8)

# get boost
find_package(Boost COMPONENTS python3 REQUIRED)
include_directories(${Boost_INCLUDE_DIRS})

# get python
find_package(PythonLibs 3 REQUIRED)
include_directories(${PYTHON_INCLUDE_DIRS})

add_library(hello SHARED hello.cpp)
target_link_libraries(hello ${Boost_LIBRARIES} ${PYTHON_LIBRARIES})
set_target_properties(hello PROPERTIES PREFIX "")
