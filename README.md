# CMake-MPIhelper

CMake modules to check for MPI functions.


## Include into your project

To use CMake-MPIhelper, simply add this repository as git submodule into your own repository
```Shell
mkdir externals
git submodule add git://github.com/RWTH-ELP/CMake-MPIhelper.git externals/CMake-MPIhelper
```
and adding ```externals/CMake-MPIhelper/cmake``` to your ```CMAKE_MODULE_PATH```
```CMake
set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/externals/CMake-MPIhelper/cmake" ${CMAKE_MODULE_PATH})
```


## Usage

### check_fortran_mpi_symbol_exists(symbol, variable)

Checks whether fortran MPI symbol ```symbol``` exists and stores result in ```variable```.

Example:
```cmake
find_package(CheckFortranMPISymbolExists)

check_fortran_mpi_symbol_exists(MPI_DOUBLE_COMPLEX, HAVE_MPI_DOUBLE_COMPLEX)
if (HAVE_MPI_DOUBLE_COMPLEX)
	# found MPI_DOUBLE_COMPLEX
endif ()
```


### check_mpi_function_exists(function, variable)

Checks whether C MPI function ```function``` exists and stores result in ```variable```.

Example:
```cmake
find_package(CheckMPIFunctionExists)

check_mpi_function_exists(MPI_Init, HAVE_MPI_INIT)
if (HAVE_MPI_INIT)
	# found MPI_Init
endif ()
```


### check_mpi_symbol_exists(symbol, variable)

Checks whether C MPI symbol ```symbol``` exists and stores result in ```variable```.

Example:
```cmake
find_package(CheckMPISymbolExists)

check_mpi_symbol_exists(MPI_LONG_LONG_INT, HAVE_MPI_LONG_LONG_INT)
if (HAVE_MPI_LONG_LONG_INT)
	# found MPI_LONG_LONG_INT
endif ()
```


### check_type_basic_type(type, basic_type, variable)

Sets variable to a valid basic C type derived from basic_type dependent of the
size of type.

Example:
```cmake
find_package(CheckTypeBasicType)

check_type_basic_type(MPI_Fint uint MPI_FINT_TYPE)
# MPI_FINT_TYPE is e.g. uint64_t
```


## Copyright

Copyright (c) 2015 RWTH Aachen University, Federal Republic of Germany.

See the file [LICENSE](LICENSE) in the package base directory for details.

Written by [Alexander Haase](alexander.haase@rwth-aachen.de).
