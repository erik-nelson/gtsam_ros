cmake_minimum_required(VERSION 2.8.3)
project(gtsam_ros)
find_package(catkin REQUIRED)
catkin_package()

include(ExternalProject)

externalproject_add(gtsam_ros
  GIT_REPOSITORY https://bitbucket.org/gtborg/gtsam
  GIT_TAG 3.2.1
  CMAKE_ARGS -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=${CMAKE_INSTALL_PREFIX} -DSHARED_LIBS=ON
  UPDATE_COMMAND ""
)

install(FILES package.xml DESTINATION share/${PROJECT_NAME})
