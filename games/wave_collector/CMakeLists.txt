# Setup the project and settings
project(wave_collector)

include("../../cmake/utils.cmake")


# Make sure raylib has been built
# TODO `build` directory should maybe be something else...
include_directories("../../build/release")

# Grab the screens
file(GLOB screen_sources "screens/*.c")

# Executable & linking
add_executable(wave_collector wave_collector.c  ${screen_sources})
link_libraries_to_executable(wave_collector)

# Resources
# Copy all of the resource files to the destination
file(COPY "resources/"  DESTINATION "resources/")

