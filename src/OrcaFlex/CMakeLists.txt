
add_library(orcaflex SHARED OrcaFlexInterface_Types.f90
  OrcaFlexInterface.f90)

target_link_libraries(orcaflex nwtclibs)
