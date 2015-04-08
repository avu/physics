project(physics)
cmake_minimum_required(VERSION 3.1)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
if (MINGW)
set(GLUT_ROOT_PATH lib/win32/glut)
add_custom_target(copy_glut)
add_custom_command(
     TARGET copy_glut PRE_BUILD
     COMMAND ${CMAKE_COMMAND}
     -E copy ${CMAKE_CURRENT_SOURCE_DIR}/lib/win32/glut/bin/freeglut.dll
     ${CMAKE_CURRENT_BINARY_DIR}/${CMAKE_CFG_INTDIR}/freeglut.dll
   )
endif()
add_subdirectory(src)
add_subdirectory(src/demos)