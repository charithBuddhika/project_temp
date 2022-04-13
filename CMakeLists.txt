cmake_minimum_required(VERSION 3.0.0)
project(project_temp VERSION 0.1.0)

include(CTest)
enable_testing()

add_executable(project_temp src/main.c)
add_subdirectory(facil.io)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
target_link_libraries(project_temp PUBLIC facil.io)
include(CPack)
