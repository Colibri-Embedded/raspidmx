set(SOURCES pngview.c)

find_package(PNG REQUIRED)
pkg_check_modules(BCM_HOST bcm_host=1)
pkg_check_modules(VCSM vcsm=1)

set(RPI_LDFLAGS "${VCSM_LDFLAGS}" -lbcm_host -lvchostif)

add_executable(pngview ${SOURCES})
target_include_directories(pngview PRIVATE ../common "${RPI_INCLUDE_DIRS}")
target_compile_options(pngview PRIVATE "${RPI_CFLAGS_OTHER}")
target_link_libraries(pngview "${RPI_LDFLAGS}" raspidmx PNG::PNG)

install(TARGETS pngview DESTINATION bin)