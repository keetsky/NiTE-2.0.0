cmake_minimum_required(VERSION 2.8)

project(cmaketest)

#set(
 #   CMAKE_RUNTIME_OUTPUT_DIRECTORY
 #   ${CMAKE_HOME_DIRECTORY}/bin
 #   )


find_package(OpenGL REQUIRED)
find_package(GLUT REQUIRED)


set(OPENNI2_DIR ~/OpenNI-Linux-x64-2.2)
set(NITE2_DIR ~/NiTE-2.0.0/)
set(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/lib)
link_directories(${OPENNI2_DIR}/Redist)
include_directories(${OPENNI2_DIR}/Include)
link_directories(${NITE2_DIR}/Redist)
include_directories(${NITE2_DIR}/Include)
#include_directories(../../../thirdparty/comm/include) 



# Find Nite2


#add_executable(
#    SimpleHandTracker
 #   src/main.cpp
 #   )


include_directories( ${OPENGL_INCLUDE_DIRS}  ${GLUT_INCLUDE_DIRS} ${OpenNI2_INCLUDEDIR} ${Nite2_INCLUDEDIR})
add_executable(cmaketest cmaketest.cpp)
target_link_libraries(cmaketest ${OPENGL_LIBRARIES} ${GLUT_LIBRARY} OpenNI2 NiTE2)
