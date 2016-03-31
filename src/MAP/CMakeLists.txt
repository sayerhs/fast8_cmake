

add_subdirectory(mappp)
generate_f90types(MAP_Registry.txt MAP_Types.f90 -ccode)

add_library(map_fast  MAP.f90 MAP_Types.f90)
target_link_libraries(map_fast mapcpp nwtclibs)


install(FILES
  ${CMAKE_CURRENT_BINARY_DIR}/MAP_Types.h
  DESTINATION include)
