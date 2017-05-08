set (CMAKE_FORTRAN_FLAGS "-O3")

file (GLOB SRCFiles *.f*)

set (CMAKE_Fortran_MODULE_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/mod)

add_library(bspline SHARED ${SRCFiles})

# configure pkg-config
configure_file(
	"${CMAKE_CURRENT_SOURCE_DIR}/libbspline.pc.in"
	"${CMAKE_CURRENT_BINARY_DIR}/libbspline.pc" @ONLY
)

# install library
install(
	TARGETS bspline
	EXPORT BSPLINETargets
	RUNTIME DESTINATION "${INSTALL_BIN_DIR}"
	LIBRARY DESTINATION "${INSTALL_LIB_DIR}"
	ARCHIVE DESTINATION "${INSTALL_LIB_DIR}/static"
	PUBLIC_HEADER DESTINATION "${INSTALL_INCLUDE_DIR}"
)

# install fortran module files (note the trailing "/" after module directory)
install(
	DIRECTORY ${CMAKE_Fortran_MODULE_DIRECTORY}/
	DESTINATION "${INSTALL_INCLUDE_DIR}"
)

# install pkg-config
install(
	FILES "${CMAKE_CURRENT_BINARY_DIR}/libbspline.pc"
	DESTINATION "${INSTALL_PKGCONFIG_DIR}"
)