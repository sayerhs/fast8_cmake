
generate_f90types(Registry-AD14.txt AeroDyn14_Types.f90)
generate_f90types(Registry-DWM.txt DWM_Types.f90)

add_library(aerodyn14  AeroDyn14.f90 AeroDyn14_Types.f90 AeroSubs.f90
            DWM.f90 DWM_Types.f90 DWM_Wake_Sub_ver2.f90 GenSubs.f90 )

target_link_libraries(aerodyn14 nwtclibs inflowwind)
