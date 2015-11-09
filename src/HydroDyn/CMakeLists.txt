
generate_f90types(Conv_Radiation.txt Conv_Radiation_Types.f90)
generate_f90types(Current.txt Current_Types.f90)
generate_f90types(HydroDyn.txt HydroDyn_Types.f90)
generate_f90types(Morison.txt Morison_Types.f90)
generate_f90types(SS_Radiation.txt SS_Radiation_Types.f90)
generate_f90types(WAMIT.txt WAMIT_Types.f90)
generate_f90types(WAMIT2.txt WAMIT2_Types.f90)
generate_f90types(Waves.txt Waves_Types.f90)
generate_f90types(Waves2.txt Waves2_Types.f90)


add_library(hydrodyn  Conv_Radiation.f90 Conv_Radiation_Types.f90 Current.f90 Current_Types.f90 HydroDyn.f90 HydroDyn_Input.f90 HydroDyn_Output.f90 HydroDyn_Types.f90 Morison.f90 Morison_Output.f90 Morison_Types.f90 SS_Radiation.f90 SS_Radiation_Types.f90 WAMIT.f90 WAMIT2.f90 WAMIT2_Output.f90 WAMIT2_Types.f90 WAMIT_Interp.f90 WAMIT_Output.f90 WAMIT_Types.f90 Waves.f90 Waves2.f90 Waves2_Output.f90 Waves2_Types.f90 Waves_Types.f90 UserWaves.f90)

target_link_libraries(hydrodyn nwtclibs)
