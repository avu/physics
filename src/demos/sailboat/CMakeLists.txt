project(sailboat)
add_executable(sailboat sailboat.cpp)
target_link_libraries(sailboat cyclone)
target_link_libraries(sailboat demo)
target_link_libraries(sailboat ${EXTRA_LIBS})