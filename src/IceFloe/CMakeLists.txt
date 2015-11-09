
generate_f90types(IceFloe_FASTRegistry.inp IceFloe_Types.f90)

add_library(icefloe  IceFlexBase.F90 IceFlexIEC.f90 IceFlexISO.f90 IceFloe.f90 IceFloeBase.F90 IceFloe_Types.f90 RANLUX.f90 coupledCrushing.F90 crushingIEC.F90 crushingISO.F90 iceInput.f90 iceLog.F90 intermittentCrushing.F90 lockInISO.F90 randomCrushing.F90)
target_link_libraries(icefloe nwtclibs)
