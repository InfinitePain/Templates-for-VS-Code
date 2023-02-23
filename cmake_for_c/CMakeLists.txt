cmake_minimum_required(VERSION 3.25)

project(CMake_Test VERSION 1.1.1)

# Set the output directory for the binary file
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR}/${PROJECT_NAME}/)

# configure a header file to pass some of the CMake settings
# to the source code
configure_file(CMakeProjectConfig.h.in CMakeProjectConfig.h)

# Set up source directories and files
include_directories(${PROJECT_SOURCE_DIR}/include)
file(GLOB SOURCES "src/*.c")
add_executable(${PROJECT_NAME} ${SOURCES})

# Add any additional external libraries that use CMake
# add_subdirectory(${PROJECT_SOURCE_DIR}/ext/PDCurses)
# target_link_libraries(${PROJECT_NAME} PUBLIC PDCurses)

# Add any additional external libraries that do not use CMake
# set(PDCURSES_LIBRARY ${PROJECT_SOURCE_DIR}/ext/PDCurses/wincon/pdcurses.a)
# include_directories(${PROJECT_SOURCE_DIR}/ext/PDCurses)
# find_library(PDCURSES_LIBRARY NAMES pdcurses PATHS ${CMAKE_SOURCE_DIR}/ext/PDCurses/wincon)
# target_link_libraries(${PROJECT_NAME} ${PDCURSES_LIBRARY})

# Add any additional libraries
# set(NCURSES_LIBRARY ncurses)
# include_directories("C:/msys64/mingw64/include/ncurses")
# find_library(NCURSES_LIBRARY NAMES ncurses)
# target_link_libraries(${PROJECT_NAME} PUBLIC ${NCURSES_LIBRARY})

# add the install targets
install(TARGETS ${PROJECT_NAME} DESTINATION bin)
install(FILES "${PROJECT_BINARY_DIR}/CMakeProjectConfig.h" DESTINATION include)

# Set up testing
include(CTest)
enable_testing()

# Set up packaging
set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)