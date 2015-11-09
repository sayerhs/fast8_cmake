

add_subdirectory(mappp)
generate_f90types(MAP_Registry.txt Map_Types.f90 -ccode)

add_library(map_fast  MAP.f90 MAP_Types.f90)
target_link_libraries(map_fast mapcpp nwtclibs)


