project(platform)
add_executable(platform platform.cpp)
target_link_libraries(platform cyclone)
target_link_libraries(platform demo)
target_link_libraries(platform ${EXTRA_LIBS})