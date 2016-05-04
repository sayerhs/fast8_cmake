
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

* `FAST                      v8.15.00a-bjj  (12-Apr-2016)`
* `NWTC Subroutine Library   v2.08.00       ( 5-Apr-2016)`
* `BeamDyn                   v1.01.03       (12-Apr-2016)`
* `ElastoDyn                 v1.03.02a-bjj  ( 8-Apr-2016)`
* `ServoDyn                  v1.05.00a-bjj  (11-Mar-2016)`
* `AeroDyn                   v15.02.03      (12-Apr-2016)`
* `AirfoilInfo               v1.01.00a-bjj  ( 5-Apr-2016)`
* `BEM                       v1.01.00a      (12-Apr-2016)`
* `AeroDyn14                 v14.05.00a-bjj (11-Apr-2016)`
* `InflowWind                v3.02.00a-bjj  (11-Apr-2016)`
* `IfW_BladedFFWind          v1.01.00       (14-Dec-2015)`
* `IfW_HAWCWind              v1.01.00       (14-Dec-2015)`
* `IfW_TSFFWind              v1.01.00       (14-Dec-2015)`
* `IfW_UniformWind           v2.03.00       (14-Dec-2015)`
* `IfW_UserWind              v0.00.00       (00-Jan-0000)`
* `Lidar                     v1.01.00a-bjj  (14-Dec-2015)`
* `DWM                       v2.01.03-yh    (11-Apr-2016)`
* `FEAMooring                v1.02.00       ( 7-Jan-2016)`
* `Conv_Radiation            v1.01.00       (23-Dec-2015)`
* `Current                   v1.010.00      (23-Dec-2015)`
* `HydroDyn                  v2.05.00       (15-Mar-2016)`
* `Morison                   v1.01.00       (23-Dec-2015)`
* `SS_Radiation              v1.01.00       (23-Dec-2015)`
* `WAMIT                     v1.01.00       (23-Dec-2015)`
* `WAMIT2                    v1.01.00       (17-Dec-2015)`
* `Waves                     v1.01.00       (23-Dec-2015)`
* `Waves2                    v1.01.00       (23-Dec-2015)`
* `IceDyn                    v1.02.00       ( 8-Jan-2016)`
* `IceFloe                   v1.01.00       ( 8-Jan-2016)`
* `MoorDyn                   v1.01.02F      ( 8-Apr-2016)`
* `OpenFOAM Integration      v1.00.00a-bjj  (11-Aug-2015)`
* `OrcaFlexInterface         v1.01.01       (11-Apr-2016)`
* `TMD                       v1.02.01-sp    ( 8-Jan-2016)`
* `SubDyn                    v1.03.00       (11-Apr-2016)`
