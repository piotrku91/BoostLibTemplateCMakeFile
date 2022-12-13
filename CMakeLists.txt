cmake_minimum_required (VERSION 3.20)

project (BoostTest)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(FLAGS -Wall -Wextra -Werror -Wconversion -pedantic -pedantic-errors -g)

set(PROJECT_INCLUDE_DIR ${PROJECT_SOURCE_DIR}/include)
set(PROJECT_SOURCE_DIR ${PROJECT_SOURCE_DIR}/)
set(CMAKE_OUTPUT_BUILD_DIR ${PROJECT_SOURCE_DIR}/build)

set(BOOST_ROOT_DIR "/home/piotr/external_libs")
set(BOOST_REQUIRED_VERSION 1.80.0)

set(Boost_NO_SYSTEM_PATHS ON)
set(Boost_USE_MULTITHREADED ON)
set(Boost_USE_STATIC_LIBS ON)
set(Boost_USE_STATIC_RUNTIME OFF)
set(BOOST_ALL_DYN_LINK OFF)

find_package (Boost ${BOOST_REQUIRED_VERSION} REQUIRED COMPONENTS system filesystem)
if (Boost_FOUND)
  include_directories (SYSTEM ${Boost_INCLUDE_DIR})
  include_directories (${PROJECT_INCLUDE_DIR})
  add_compile_options(${FLAGS})
  add_executable (${PROJECT_NAME} main.cpp)
  target_link_libraries (${PROJECT_NAME} ${Boost_LIBRARIES})
endif ()

