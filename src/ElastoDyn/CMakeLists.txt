
generate_f90types(ElastoDyn_Registry.txt ElastoDyn_Types.f90)

add_library(elastodyn ElastoDyn.f90 ElastoDyn_IO.f90 ED_UserSubs.f90 ElastoDyn_Types.f90)
target_link_libraries(elastodyn servodyn nwtclibs)
