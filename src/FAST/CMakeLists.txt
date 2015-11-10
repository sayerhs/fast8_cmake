
generate_f90types(../OpenFOAM/OpenFOAM_Registry.txt OpenFOAM_Types.f90 -ccode)
generate_f90types(../OrcaFlex/OrcaFlexInterface.txt OrcaFlexInterface_Types.f90)
generate_f90types(FAST_Registry.txt FAST_Types.f90 -noextrap)

# FIXME: OpenFOAM and OrcaFlex types include FAST_Types and FAST_Types
# requires OpenFOAM_Types and OrcaFlex_Types. Include them together
# for now so that CMake resolver can figure out the right ordering of
# the compilation.
add_library(fast8lib 
  FAST_Mods.f90
  FAST_Prog.f90
  FAST_Subs.f90
  FAST_Types.f90
  ../OpenFOAM/OpenFOAM.f90
  OpenFOAM_Types.f90
  OrcaFlexInterface_Types.f90
  ../OrcaFlex/OrcaFlexInterface.f90)
add_executable(fast8 FAST_Prog.f90)

target_link_libraries(fast8lib nwtclibs inflowwind aerodyn aerodyn14
  servodyn elastodyn beamdyn subdyn feamooring icedyn icefloe map_fast
  mapcpp moordyn hydrodyn)

target_link_libraries(fast8 fast8lib)

install(TARGETS fast8 fast8lib
  RUNTIME DESTINATION bin
  LIBRARY DESTINATION lib
  ARCHIVE DESTINATION lib)

install (FILES
  ${CMAKE_CURRENT_BINARY_DIR}/OpenFOAM_Types.h
  DESTINATION include)
