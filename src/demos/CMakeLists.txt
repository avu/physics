project(demos)

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

add_library(demo app.cpp main.cpp timing.cpp)
target_link_libraries(demo cyclone)

if (MINGW)
target_link_libraries(demo winmm)
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