
# NREL FAST source with CMake build

This is a fork of the [NREL FAST v8](https://nwtc.nrel.gov/FAST8)
source code to adapt it to use CMake for the build system. The source
formatting has been rearranged slightly, but otherwise no source files
have been modified from the base source downloadable at the NWTC
download portal.

## Installation instructions

```
git clone <repository_url> fast8 # Clone from public repo
cd fast8/build                   # Change into the build directory 
cmake ../src                     # Or ccmake ../src for GUI configuration
make                             # Build sources
make install                     # Optionally install 

```

## Current CMake options

* `DOUBLE_PRECISION` - Enable/disable `-DDOUBLE_PRECISION` flag
* `BUILD_SHARED_LIBS` - Enable/disable building shared libraries
* `LIB_LOAD` - Enable/disable OrcaFlex DLL loading
* `CMAKE_INSTALL_PREFIX` - Set desired installation directory

## License information

Please see `license.txt` and `Disclaimer.txt` for more information.

## Documentation and test cases

Please consult the official NWTC portal for the information.




