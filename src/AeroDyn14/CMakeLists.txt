
add_library(aerodyn14 SHARED AeroDyn14.f90 AeroDyn14_Types.f90 AeroSubs.f90
            DWM.f90 DWM_Types.f90 DWM_Wake_Sub_ver2.f90 GenSubs.f90 )

target_link_libraries(aerodyn14 nwtclibs inflowwind)
