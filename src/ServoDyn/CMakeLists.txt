
generate_f90types(TMD_Registry.txt TMD_Types.f90)
generate_f90types(ServoDyn_Registry.txt ServoDyn_Types.f90)

add_library(servodyn  BladedInterface.f90 PitchCntrl_ACH.f90 ServoDyn.f90 ServoDyn_Registry.txt ServoDyn_Types.f90 TMD.f90 TMD_Registry.txt TMD_Types.f90 UserSubs.f90 UserVSCont_KP.f90)
target_link_libraries(servodyn nwtclibs)
