bspline-fortran
============

Multidimensional B-Spline Interpolation of Data on a Regular Grid created by Jacob Williams. Look [here](https://github.com/jacobwilliams/bspline-fortran) for original and description. This fork provides CMake installation of subroutines (no object-oriented interface). Useful when you have old compiler (Gfortran < 4.9).

# Installation

The library is installed in user-space (`${HOME}/lib/bspline`) and (`${HOME}/include/bspline`) by default.

```
mkdir build; cd build
cmake .. -DCMAKE_INSTALL_PREFIX=$HOME
make
make install
```

Verify that the library and include files can be found:

```
export PKG_CONFIG_PATH=${HOME}/lib/pkgconfig
pkg-config --cflags --libs libbspline
```
Expect output similar to:
```
-I/home/advsim/include/bspline -L/home/advsim/lib/bspline -lbspline
```

# License

The bspline-fortran source code and related files and documentation are distributed under a permissive free software [license](https://github.com/jacobwilliams/bspline-fortran/blob/master/LICENSE) (BSD-style).
