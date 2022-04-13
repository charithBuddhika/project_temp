cmake_minimum_required(VERSION 3.0.0)
project(project_temp VERSION 0.1.0)

find_package(Threads REQUIRED)

include(CTest)
enable_testing()

set(main_SOURCES
    src/main.c
    src/cli.c
    src/http_service.c
)

add_executable(project_temp ${main_SOURCES})
add_subdirectory(facil.io)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
target_link_libraries(project_temp PUBLIC facil.io)
target_link_libraries(project_temp
  PRIVATE Threads::Threads
  PUBLIC pthread
  PUBLIC m
  )
include(CPack)
