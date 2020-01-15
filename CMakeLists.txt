cmake_minimum_required( VERSION 3.10.0 )
project( window )

# external glfw
set( GLFW_BUILD_DOCS OFF CACHE INTERNAL "" )
set( GLFW_BUILD_TESTS OFF CACHE INTERNAL "" )
set( GLFW_BUILD_EXAMPLES OFF CACHE INTERNAL "" )
add_subdirectory( external/glfw )

# external includes
include_directories( SYSTEM "external/glm" )
include_directories( SYSTEM "external/glad/include" )

# application code
include_directories( "include" )
add_executable(
    window 
    "window.c"
    "external/glad/src/glad.c" )
target_link_libraries(
    window 
    PRIVATE glfw
    )
