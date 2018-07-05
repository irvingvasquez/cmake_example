#  CMake is an open-source cross platform build system.
#  What CMake provides is an easy way to build C/C++ projects across platforms.
#  CMake allows for a more flexible development environment as it can generate Makefiles or projects for a variety of IDEs.

# 
cmake_minimum_required(VERSION 2.6)


project(talk_seminario_da)


set(SRC_FOLDER src/)
set(SRC_FILES ${SRC_FOLDER}recepcionista.cpp)
include_directories(src/)


#----------------------------- BOOST --------------------
find_package(Boost COMPONENTS system filesystem REQUIRED)
include_directories( ${Boost_INCLUDE_DIR} )


#-----------------------------------------------
add_executable(ejecutable  main.cpp ${SRC_FILES})
target_link_libraries(ejecutable ${Boost_LIBRARIES} -lboost_system)


