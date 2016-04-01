
# NREL FAST source with CMake build

This is a fork of the [NREL FAST v8](https://nwtc.nrel.gov/FAST8) source code to
adapt it to use CMake for the build system. The source formatting has been
rearranged slightly, but otherwise no source files have been modified from the
base source downloadable at the NWTC download portal. See version information
below to determine the exact version of FAST and dependencies used in this
repository.

## Installation instructions

```
git clone <repository_url> fast8 # Clone from public repo
cd fast8/build                   # Change into the build directory 
cmake ../src                     # Or ccmake ../src for GUI configuration
make                             # Build sources
make install                     # Optionally install 

```

## Current CMake options

* `DOUBLE_PRECISION` - Enable/disable `-DDOUBLE_PRECISION` flag (Default: ON)
* `USE_DLL_INTERFACE` - Enable dynamic library loading capability (Default: ON)
* `CMAKE_BUILD_TYPE` - Release, Debug builds (Default: Release)
* `BUILD_SHARED_LIBS` - Enable/disable building shared libraries (Default: OFF)
* `LIB_LOAD` - Enable/disable OrcaFlex DLL loading (Default: OFF)
* `CMAKE_INSTALL_PREFIX` - Set desired installation directory

## License information

Please see `license.txt` and `Disclaimer.txt` for more information.

## Documentation and test cases

Please consult the official NWTC portal for the information.

# Version information

* FAST          - `v8.12.00a-bjj  ( 6-Oct-2015)`
* NWTC Library  - `v2.06.05a-bjj  ( 5-Oct-2015)`
* ElastoDyn     - `v1.03.00a-bjj  ( 5-Oct-2015)`
* AeroDyn14     - `v14.04.00a-bjj ( 6-Oct-2015)`
* AeroDyn       - `v15.00.00b-bjj ( 6-Oct-2015)`
* InflowWind    - `v3.01.00a-adp  ( 5-Oct-2015)`
* ServoDyn      - `v1.03.01a-bjj  ( 5-Oct-2015)`
* AirfoilInfo   - `v1.00.01a-bjj  (11-May-2015)`
* BEM           - `v0.01.00a-gjh  (10-Jul-2014)`

