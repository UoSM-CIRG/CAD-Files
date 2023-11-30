cmake_minimum_required(VERSION 3.5)

project(display_model)

## Generate symbols for IDE indexer
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# if CMAKE_BUILD_TYPE is not specified, take 'Release' as default
IF(NOT CMAKE_BUILD_TYPE)
    SET(CMAKE_BUILD_TYPE Release)
ENDIF(NOT CMAKE_BUILD_TYPE)

# Find catkin macros and libraries
find_package(catkin REQUIRED COMPONENTS
  roscpp
  robot_state_publisher
  # Add other dependencies if needed
)

# Declare the catkin package
catkin_package()

# Install directories
install(DIRECTORY
  launch
  description
  config
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)