cmake_minimum_required(VERSION 3.10)

project(Example LANGUAGES CXX)

include(CTest)

# Create a variable to enable the flux capacitor
# "ENABLE" is a common convention for turning features on/off in CMake
set (ENABLE_FLUX_CAPACITOR False CACHE BOOL "Flux capacitor option enabled")

# message is CMake "printf"
message(STATUS "Flux capacitor : " ${ENABLE_FLUX_CAPACITOR})

# Compilation flag used for #ifdef tests in the code, convention in
# C/C++ is "HAVE" so let's use that as our C flag name.  
if (${ENABLE_FLUX_CAPACITOR})
  set (EXAMPLE_HAVE_FLUX_CAPACITOR True)
endif ()

configure_file(config.h.in config.h)

# Add two subdirectories to the project build
add_subdirectory(library)
add_subdirectory(main)





