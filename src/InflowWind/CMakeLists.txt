
generate_f90types(InflowWind.txt InflowWind_Types.f90)
generate_f90types(Lidar.txt Lidar_Types.f90)
generate_f90types(IfW_BladedFFWind.txt IfW_BladedFFWind_Types.f90 -noextrap)
generate_f90types(IfW_HAWCWind.txt IfW_HAWCWind_Types.f90 -noextrap)
generate_f90types(IfW_TSFFWind.txt IfW_TSFFWind_Types.f90 -noextrap)
generate_f90types(IfW_UniformWind.txt IfW_UniformWind_Types.f90 -noextrap)
generate_f90types(IfW_UserWind.txt IfW_UserWind_Types.f90 -noextrap)

add_library(inflowwind  IfW_BladedFFWind.f90
            IfW_BladedFFWind_Types.f90 IfW_HAWCWind.f90
            IfW_HAWCWind_Types.f90 IfW_TSFFWind.f90
            IfW_TSFFWind_Types.f90 IfW_UniformWind.f90
            IfW_UniformWind_Types.f90 IfW_UserWind.f90
            IfW_UserWind_Types.f90 InflowWind.f90 InflowWind_Subs.f90
            InflowWind_Types.f90 Lidar.f90 Lidar_Types.f90 )


target_link_libraries(inflowwind nwtclibs)
