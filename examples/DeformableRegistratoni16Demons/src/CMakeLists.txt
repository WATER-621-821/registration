# This is the root ITK CMakeLists file.
cmake_minimum_required(VERSION 2.4)
if(COMMAND CMAKE_POLICY)
  cmake_policy(SET CMP0003 NEW)
endif()

SET(APPLICATION_SOURCES
  FolderReader.cxx
  DeformableRegistration16.cxx
  )
set(HEADER_FILES FolderReader.h )

# This project is designed to be built outside the Insight source tree.
project(DeformableRegistration16)

# Find ITK.
find_package(ITK REQUIRED)
include(${ITK_USE_FILE})
add_library( ${HEADER_FILES})

add_executable(DeformableRegistration16 DeformableRegistration16.cxx FolderReader.cxx)

target_link_libraries(DeformableRegistration16 ${ITK_LIBRARIES})
SET_TARGET_PROPERTIES(FolderReader.h PROPERTIES LINKER_LANGUAGE C++)