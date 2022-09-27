cmake_minimum_required( VERSION 3.10 )
project(Shapes LANGUAGES CXX C  VERSION 0.1)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ../bin)

include_directories( 
    ./include 
    ${PROJECT_SOURCE_DIR}/SFML/include 
)

find_package(X11 REQUIRED)
include_directories(${X11_INCLUDE_DIR})

add_executable(${PROJECT_NAME} "")
add_subdirectory(./SFML ../SFML/cmake_build)
add_subdirectory(./src)

link_directories(./SFML/cmake_build/lib)
target_link_libraries(${PROJECT_NAME} PUBLIC sfml-graphics sfml-window sfml-system)

target_compile_features(${PROJECT_NAME} PUBLIC cxx_std_17)