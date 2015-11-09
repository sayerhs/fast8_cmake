
add_library(moordyn  MoorDyn.f90 MoorDyn_IO.f90 MoorDyn_Types.f90)
target_link_libraries(moordyn nwtclibs)

