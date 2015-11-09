
set(NWTCLIBS_SOURCES ModMesh.f90 ModMesh_Mapping.f90 ModMesh_Types.f90
    NWTC_Base.f90 NWTC_FFTPACK.f90 NWTC_IO.f90 NWTC_LAPACK.f90
    NWTC_FitPack.f90 NWTC_Library.f90 NWTC_Library_Types.f90
    NWTC_Num.f90 NWTC_ScaLAPACK.f90 dlasrt2.f fftpack4.1.f slasrt2.f
    SingPrec.f90 dierckx_fitpack.f )

#get_filename_component(FCNAME ${CMAKE_Fortran_COMPILER} NAME)

if (APPLE OR UNIX)
  if (FCNAME MATCHES "gfortran.*")
    list (APPEND NWTCLIBS_SOURCES SysGnuLinux.f90)
  elseif (FCNAME MATCHES "ifort.*")
    list (APPEND NWTCLIBS_SOURCES SysIFL.f90)
  endif (FCNAME MATCHES "gfortran.*")
elseif (WIN32)
  if (FCNAME MATCHES "gfortran.*")
    list (APPEND NWTCLIBS_SOURCES SysGnuWin.f90)
  elseif (FCNAME MATCHES "ifort.*")
    list (APPEND NWTCLIBS_SOURCES SysIFV.f90)
  endif (FCNAME MATCHES "gfortran.*")
endif (APPLE OR UNIX)

add_library(nwtclibs SHARED ${NWTCLIBS_SOURCES})
target_link_libraries(nwtclibs ${LAPACK_LIBRARIES})
