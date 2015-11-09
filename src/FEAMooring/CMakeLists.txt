
add_library(feamooring SHARED FEAM.f90 FEAMooring_Types.f90)
target_link_libraries(feamooring nwtclibs)
