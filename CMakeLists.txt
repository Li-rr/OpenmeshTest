cmake_minimum_required(VERSION 3.17)
project(test)

set(CMAKE_CXX_STANDARD 11)
#list (APPEND CMAKE_MODULE_PATH ${CMAKE_SOURCE_DIR}/cmake_module)
find_package( OpenMesh REQUIRED)
include_directories( ${OpenMesh_INCLUDE_DIRS} )
aux_source_directory(src DIR_SRCS) # source dir
set(test_MATH ${DIR_SRCS})
add_executable(${PROJECT_NAME} ${test_MATH})
message("---")
message("${OpenMesh_LIBS}")
message("===")
target_link_libraries(${PROJECT_NAME} ${OpenMesh_LIBS} OpenMeshCore OpenMeshTools)