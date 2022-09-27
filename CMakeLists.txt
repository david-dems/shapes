project( Shapes )
cmake_minimum_required( VERSION 3.10 )

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ../bin)

include_directories( 
    ./include 
    ./SFML/include 
)

find_package(X11 REQUIRED)
include_directories(${X11_INCLUDE_DIR})

add_executable(${PROJECT_NAME} "")
add_subdirectory(./src)
add_subdirectory(./SFML)


