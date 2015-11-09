
generate_f90types(Registry_IceDyn.txt IceDyn_Types.f90)

add_library(icedyn  IceDyn.f90 IceDyn_Types.f90)
target_link_libraries(icedyn nwtclibs)
