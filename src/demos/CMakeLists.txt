project(demos)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
IF(APPLE)
   include_directories (/System/Library/Frameworks)
   find_library(COCOA_LIBRARY Cocoa)
   find_library(GLUT_LIBRARY GLUT )
   find_library(OpenGL_LIBRARY OpenGL )
   mark_as_advanced (COCOA_LIBRARY
                     GLUT_LIBRARY
                     OpenGL_LIBRARY)
   set(EXTRA_LIBS ${COCOA_LIBRARY} ${GLUT_LIBRARY} ${OpenGL_LIBRARY})
ENDIF (APPLE)


include_directories(SYSTEM ../../include/)
add_library(demo app.cpp main.cpp timing.cpp)

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