# Adafruit GFX Library
# https://github.com/adafruit/Adafruit-GFX-Library
# BSD License

cmake_minimum_required(VERSION 3.5)

if(DEFINED ESP_PLATFORM AND ESP_PLATFORM)
    idf_component_register(SRCS "Adafruit_GFX.cpp" "Adafruit_GrayOLED.cpp" "Adafruit_SPITFT.cpp" "glcdfont.c" INCLUDE_DIRS ".")
else()
    # Standard CMake settings
    add_library(Adafruit-GFX-Library STATIC
        "Adafruit_GFX.cpp"
        "Adafruit_GrayOLED.cpp"
        "Adafruit_SPITFT.cpp"
        "glcdfont.c"
    )
    target_include_directories(miniz PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}
    )
endif()

project(Adafruit-GFX-Library)
