cmake_minimum_required(VERSION 2.8.3)
project(dill)

# Minimal Python module setup
find_package(catkin REQUIRED COMPONENTS
    roslint
)
catkin_python_setup()

# Lint Python modules
file(GLOB_RECURSE ${PROJECT_NAME}_PY_SRCS
     RELATIVE ${PROJECT_SOURCE_DIR} dill/*.py)
roslint_python(${${PROJECT_NAME}_PY_SRCS})

## Unit tests
if (CATKIN_ENABLE_TESTING)
  add_subdirectory(tests)
endif()

