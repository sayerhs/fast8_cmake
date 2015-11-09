
add_library(fast8lib  FAST_Mods.f90 FAST_Subs.f90 FAST_Types.f90)

add_executable(fast8 FAST_Prog.f90)


target_link_libraries(fast8lib nwtclibs inflowwind aerodyn servodyn
                      elastodyn subdyn feamooring icedyn icefloe
                      map_fast mapcpp moordyn hydrodyn)
target_link_libraries(fast8 fast8lib)
