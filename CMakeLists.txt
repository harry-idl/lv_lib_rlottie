cmake_minimum_required(VERSION 3.14)

### Espressif specific
idf_component_register(
    SRCS "lv_rlottie.c" "lv_rlottie_example_fingerprint.c"
    INCLUDE_DIRS "." "rlottie_lib/rlottie/inc"
    REQUIRES lvgl)

option(LOTTIE_MODULE OFF)
option(LOTTIE_THREAD OFF)
option(BUILD_SHARED_LIBS OFF)
function(install)
endfunction()

function(export)
endfunction()

add_subdirectory (rlottie_lib)

# Link rlottie to main component
target_link_libraries(${COMPONENT_LIB} PUBLIC rlottie)
