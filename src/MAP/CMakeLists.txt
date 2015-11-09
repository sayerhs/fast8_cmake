
add_subdirectory(mappp)

add_library(map_fast  MAP.f90 MAP_Types.f90)
target_link_libraries(map_fast mapcpp nwtclibs)


