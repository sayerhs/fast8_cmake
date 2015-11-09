
add_library(mapcpp  bstring/bstraux.c bstring/bstraux.h bstring/bstrlib.c bstring/bstrlib.h cminpack/cminpack.h cminpack/cminpackP.h cminpack/dpmpar.c cminpack/enorm.c cminpack/enorm_u.c cminpack/lmder.c cminpack/lmpar.c cminpack/minpack.h cminpack/qrfac.c cminpack/qrsolv.c freedata.c freedata.h jacobian.c jacobian.h lapack/lapacke.h lapack/lapacke_mangling.h lineroutines.c lineroutines.h lmroutines.cc lmroutines.hpp map.h MAP_Types.h mapapi.c mapapi.h maperror.c maperror.h mapinit.c mapinit.h mapsys.h numeric.c numeric.h outputstream.c outputstream.h residual.c residual.h simclist/simclist.c simclist/simclist.h )

target_include_directories (mapcpp PUBLIC bstring cminpack lapack simclist)
