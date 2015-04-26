# This is the root ITK CMakeLists file.
cmake_minimum_required(VERSION 2.8)


INCLUDE_DIRECTORIES(
 ${CMAKE_CURRENT_SOURCE_DIR} 
    ${CMAKE_CURRENT_BINARY_DIR} 
)

SET(APPLICATION_SOURCES
  FolderReader.cxx
  DeformableRegistration16.cxx
  )
set(HEADER_FILES FolderReader.h)

# This project is designed to be built outside the Insight source tree.
project(DeformableRegistration16)

# Find ITK.
find_package(ITK REQUIRED)
include(${ITK_USE_FILE})

if (ITKVtkGlue_LOADED)
  find_package(VTK REQUIRED)
  include(${VTK_USE_FILE})
else()
  find_package(ItkVtkGlue REQUIRED)
  include(${ItkVtkGlue_USE_FILE})
  set(Glue ItkVtkGlue)
endif()

add_executable(DeformableRegistration16 MACOSX_BUNDLE DeformableRegistration16.cxx FolderReader.cxx ${HEADER_FILES})

add_library( ${HEADER_FILES} FolderReader.cxx)
target_link_libraries(DeformableRegistration16 ${ITK_LIBRARIES})

SET_TARGET_PROPERTIES(FolderReader.h PROPERTIES LINKER_LANGUAGE C++)
