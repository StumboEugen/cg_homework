cmake_minimum_required(VERSION 3.5)
project(Map)

include_directories(${PROJECT_SOURCE_DIR}/lib)
link_directories(${PROJECT_SOURCE_DIR}/lib)
find_package( OpenGL REQUIRED )
if(OPENGL_FOUND)
  include_directories(${OPENGL_INCLUDE_DIR})
  MESSAGE(STATUS "OpenGL_LIBRARIES is: " ${OPENGL_LIBRARIES})
endif()

find_package( GLUT REQUIRED )
if(GLUT_FOUND)
  include_directories(${GLUT_INCLUDE_DIR})
  MESSAGE(STATUS "GLUT_LIBRARIES is: " ${GLUT_LIBRARIES})
endif()

add_executable(Maze src/maze.cpp)
target_link_libraries(Maze ${GLUT_LIBRARIES} ${OPENGL_LIBRARIES} libSOIL.a)
