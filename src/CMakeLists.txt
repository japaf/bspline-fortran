set (CMAKE_FORTRAN_FLAGS "-O3")
file (GLOB _sources *.f*)
set (CMAKE_Fortran_MODULE_DIRECTORY mod)
add_library(bspline SHARED ${_sources})
install(DIRECTORY ${CMAKE_Fortran_MODULE_DIRECTORY}/
    DESTINATION $ENV{HOME}/include)
install(TARGETS bspline DESTINATION $ENV{HOME}/lib)
