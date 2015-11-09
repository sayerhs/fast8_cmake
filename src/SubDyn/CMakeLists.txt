
add_library(subdyn  SD_FEM.f90 SubDyn.f90 SubDyn_Output.f90 SubDyn_Types.f90 qsort_c_module.f90)
target_link_libraries(subdyn nwtclibs)
