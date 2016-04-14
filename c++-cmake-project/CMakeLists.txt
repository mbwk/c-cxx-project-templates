cmake_minimum_required(VERSION 2.8)

project( EXAMPLEPROJECT ) # project name, this is case sensitive

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -Wall -Werror \
    -fdiagnostics-show-location=every-line -pedantic \
    -Wfatal-errors -g")

######################################
# finds OpenGL, GLU and X11
#find_package(OpenGL REQUIRED) # searches for specified library/package on system
#find_package(Threads REQUIRED)
#if(NOT OPENGL_FOUND)
#    message("ERROR: OpenGL not found")
#endif(NOT OPENGL_FOUND)
#set(GL_LIBRARY GL GLU X11 GLEW)

file(GLOB SOURCES src/*.cpp) # globs source files every time you run cmake
file(GLOB HEADERS src/*.hpp) # globs include files, similar to previous usage (this is only to force rebuilds if a header is changed)

add_executable(example ${SOURCES} ${HEADERS}) # adds compilation target: a standalone executable

#target_link_libraries(eexec ${GL_LIBRARY} ${CMAKE_THREAD_LIBS_INIT}) # link to given libraries

