cmake_minimum_required(VERSION 3.3...3.12 FATAL_ERROR)


PROJECT (LabeledMesh)

find_package(VTK REQUIRED)
vtk_module_config(VTK
  vtkCommonCore
  vtkCommonDataModel
  vtkFiltersSources
  vtkInteractionStyle
  vtkRenderingLabel
  vtkRenderingOpenGL2
)
include(${VTK_USE_FILE})

add_executable(${PROJECT_NAME} MACOSX_BUNDLE ${PROJECT_NAME}.cxx)
target_link_libraries(${PROJECT_NAME} ${VTK_LIBRARIES})
