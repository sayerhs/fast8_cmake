
add_library(elastodyn SHARED ElastoDyn.f90 ElastoDyn_Types.f90)
target_link_libraries(elastodyn servodyn nwtclibs)
