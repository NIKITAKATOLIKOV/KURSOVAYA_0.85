cmake_minimum_required(VERSION 3.11)
project(pacman_0_85 LANGUAGES CXX)

set(SFML_STATIC_LIBRARIES TRUE)
option(BUILD_SHARED_LIBS ON)

find_package(OpenGL REQUIRED)

add_subdirectory(${PROJECT_SOURCE_DIR}/lib/SFML-2.5.1)

add_executable(pacman_0_85 main.cpp Ghost.cpp Ghost.h Pacman.cpp Pacman.h Place.cpp Place.h)
target_link_libraries(pacman_0_85 PRIVATE sfml-audio sfml-graphics sfml-window sfml-system ${OPENGL_LIBRARIES})
