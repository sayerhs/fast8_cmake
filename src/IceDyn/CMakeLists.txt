
add_library(icedyn SHARED IceDyn.f90 IceDyn_Types.f90)
target_link_libraries(icedyn nwtclibs)
