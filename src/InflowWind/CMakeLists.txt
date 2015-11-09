
add_library(inflowwind  IfW_BladedFFWind.f90
            IfW_BladedFFWind_Types.f90 IfW_HAWCWind.f90
            IfW_HAWCWind_Types.f90 IfW_TSFFWind.f90
            IfW_TSFFWind_Types.f90 IfW_UniformWind.f90
            IfW_UniformWind_Types.f90 IfW_UserWind.f90
            IfW_UserWind_Types.f90 InflowWind.f90 InflowWind_Subs.f90
            InflowWind_Types.f90 Lidar.f90 Lidar_Types.f90 )


target_link_libraries(inflowwind nwtclibs)
