bspline-fortran
============

Multidimensional B-Spline Interpolation of Data on a Regular Grid created by Jacob Williams. Look [here](https://github.com/jacobwilliams/bspline-fortran) for original and description. This fork provides CMake installation of subroutines (no object-oriented interface). Useful when you have old compiler (Gfortran < 4.9).

# Installation

The library is installed in user-space (`${HOME}/lib/bspline`) and (`${HOME}/include/bspline`) by default.

```
mkdir build; cd build
cmake ..
cmake --build .
cmake --build . --target install
```

# License

The bspline-fortran source code and related files and documentation are distributed under a permissive free software [license](https://github.com/jacobwilliams/bspline-fortran/blob/master/LICENSE) (BSD-style).
