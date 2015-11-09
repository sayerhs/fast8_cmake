
add_library(aerodyn SHARED AeroDyn.f90 AeroDyn_IO.f90 AeroDyn_Types.f90 AirfoilInfo.f90 AirfoilInfo_Types.f90 BEMT.f90 BEMTCoupled.f90 BEMTUncoupled.f90 BEMT_Registry.txt BEMT_Types.f90 BladeElement.f90 Brent.f90 UnsteadyAero.f90 UnsteadyAero_Types.f90 fmin_fcn.f90 mod_root1dim.f90 nwtc_bemt_minpack.f90)

target_link_libraries(aerodyn nwtclibs)

