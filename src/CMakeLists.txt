
cmake_minimum_required(VERSION 2.8.12)
project(FAST8 Fortran C CXX)

# Set default installation dir
get_filename_component(default_install
  "${CMAKE_SOURCE_DIR}/../install" ABSOLUTE)
set(CMAKE_INSTALL_PREFIX ${default_install} CACHE STRING
  "Choose installation directory; default fast8/install" FORCE)
option(BUILD_SHARED_LIBS "Enabled building shared libraries" off)

# Check for BLAS and LAPACK libraries
find_package(BLAS REQUIRED)
find_package(LAPACK REQUIRED)

# Set user selectable option to turn on/off double precision 
option(DOUBLE_PRECISION "Set single or double precision" on)
option(LIB_LOAD "OrcaFlex library loading" off)
option(USE_DLL_INTERFACE "Use Controller DLLS" on)
# By default we set the preprocessor and position independent code
# directives
set(CMAKE_Fortran_FLAGS "${CMAKE_Fortran_FLAGS} -cpp -fPIC")
# Set the fortran modules to be stored in a common directory 
set(CMAKE_Fortran_MODULE_DIRECTORY ${CMAKE_BINARY_DIR}/ftnmods )
# Add that to the include path 
include_directories( ${CMAKE_Fortran_MODULE_DIRECTORY} )
if (DOUBLE_PRECISION)
  add_definitions(-DDOUBLE_PRECISION)
endif (DOUBLE_PRECISION)
if (USE_DLL_INTERFACE)
  add_definitions(-DUSE_DLL_INTERFACE)
endif(USE_DLL_INTERFACE)
if (LIB_LOAD)
  add_definitions(-DLibLoad)
else (LIB_LOAD)
  add_definitions(-DNO_LibLoad)
endif (LIB_LOAD)

#
# Logic for automatically generating *_Types.f90 files from the
# registry information.
#
# FAST_SUBIRS - the directories to include
# REG_INCLUDES - The actual includes "-I <DIR>" string passed to the command
#
set (FAST_SUBDIRS NWTC_Library InflowWind AeroDyn14 AeroDyn ServoDyn
  ElastoDyn BeamDyn SubDyn FEAMooring IceDyn IceFloe MAP MAP/Mapp
  MoorDyn HydroDyn OpenFOAM OrcaFlex)
set (REG_INCLUDES "-I" "${CMAKE_SOURCE_DIR}/FAST" )
foreach(IDIR IN ITEMS ${FAST_SUBDIRS})
  list(APPEND REG_INCLUDES "-I"  "${CMAKE_SOURCE_DIR}/${IDIR}")
endforeach(IDIR IN LISTS ${FAST_SUBDIRS})

#
# Wrapper to autogenerate *_Types.f90
#    Usage: generate_f90types(BeamDyn_Registry.txt BeamDyn_Types.f90)
# 
function (generate_f90types regfile outfile)
  get_filename_component(input ${regfile} ABSOLUTE)
  get_filename_component(output_base ${outfile} NAME)
  set(output "${CMAKE_CURRENT_BINARY_DIR}/${output_base}")
  add_custom_command(
    OUTPUT ${output} 
    DEPENDS fast_registry ${input}
    COMMAND ${CMAKE_BINARY_DIR}/Registry/fast_registry ${input} ${REG_INCLUDES} ${ARGN})
  set_source_files_properties(${output} PROPERTIES GENERATED TRUE)
endfunction (generate_f90types regfile outfile)

# Force free-form compilation 
get_filename_component(FCNAME ${CMAKE_Fortran_COMPILER} NAME)
if (FCNAME MATCHES "gfortran.*")
  set(CMAKE_Fortran_FLAGS "${CMAKE_Fortran_FLAGS} -ffree-line-length-none")
endif (FCNAME MATCHES "gfortran.*")

# Include compilation rules for subdirectories
add_subdirectory(Registry)

add_subdirectory(NWTC_Library)
add_subdirectory(InflowWind)
add_subdirectory(AeroDyn14)
add_subdirectory(AeroDyn)
add_subdirectory(ServoDyn)
add_subdirectory(ElastoDyn)
add_subdirectory(BeamDyn)
add_subdirectory(SubDyn)
add_subdirectory(FEAMooring)
add_subdirectory(IceDyn)
add_subdirectory(IceFloe)
add_subdirectory(MAP)
add_subdirectory(MoorDyn)
add_subdirectory(HydroDyn)
# add_subdirectory(OpenFOAM)
# add_subdirectory(OrcaFlex)
add_subdirectory(FAST)


include(CPack)
