This repository contains a collection of CMake files that will be
used to build sac2c packages.  We are going to use this repository
as a sub-module in the packages so that maintenance of the common
part of the build system gets easier.

Individual files have the following functionality:

  * `check-sac2c.cmake` checks whether we have an operational sac2c
     compiler.  The `SAC2C_EXEC` variable overrides search for
     `sac2c` on the PATH.

  * `sac2c-variables.cmake` defines a number of useful sac2c variables
     that are mainly coming from parsing sac2crc for a given TARGET.
     Also it performs some sanity checks like: chosen target is set
     in sac2crc, sac2c executable is set, etc.

  * `resolve-sac2c-dependencies.cmake` defines a function that for
     a given file runs `sac2c -M`, checks whether external dependencies
     to the Tree and Mod shared libraries can be found; and generates
     a list of local dependencies that can be used while defining
     a custom target in CMake.

