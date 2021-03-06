project(demos)

if (MINGW)
set(GLUT_ROOT_PATH ${CMAKE_SOURCE_DIR}/lib/win32/glut)
endif()
#########################################################
# FIND GLUT
#########################################################
find_package(GLUT REQUIRED)
include_directories(SYSTEM ${GLUT_INCLUDE_DIR})
link_directories(${GLUT_LIBRARIES})
add_definitions(${GLUT_DEFINITIONS})
if(NOT GLUT_FOUND)
    message(ERROR " GLUT not found!")
endif(NOT GLUT_FOUND)

#########################################################
# FIND OPENGL
#########################################################
find_package(OpenGL REQUIRED)
include_directories(SYSTEM ${OpenGL_INCLUDE_DIRS})
link_directories(${OpenGL_LIBRARY_DIRS})
add_definitions(${OpenGL_DEFINITIONS})
if(NOT OPENGL_FOUND)
    message(ERROR " OPENGL not found!")
endif(NOT OPENGL_FOUND)

set(EXTRA_LIBS ${OPENGL_LIBRARIES} ${GLUT_LIBRARY})

include_directories(SYSTEM ../../include/)

add_library(
demo
app.cpp
ogl_headers.h
main.cpp
timing.cpp
)

target_link_libraries(demo cyclone)


set( CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR}/bin )
add_custom_target(copy_glut)

add_custom_command(
     TARGET copy_glut PRE_BUILD
     COMMAND ${CMAKE_COMMAND}
     -E copy ${CMAKE_SOURCE_DIR}/lib/win32/glut/bin/freeglut.dll
     ${PROJECT_BINARY_DIR}/bin/freeglut.dll
   )

if (MINGW)
target_link_libraries(demo winmm)
add_dependencies(demo copy_glut)
endif()

add_subdirectory(ballistic)
add_subdirectory(bigballistic)
add_subdirectory(blob)
add_subdirectory(bridge)
add_subdirectory(explosion)
add_subdirectory(fireworks)
add_subdirectory(flightsim)
add_subdirectory(fracture)
add_subdirectory(platform)
add_subdirectory(ragdoll)
add_subdirectory(sailboat)