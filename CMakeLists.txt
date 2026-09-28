cmake_minimum_required(VERSION 3.10)

project(SoapyMiri LANGUAGES CXX)

# SoapyMiri est un MODULE (plugin)
add_library(SoapyMiri MODULE
        Registration.cpp
        Settings.cpp
        Streaming.cpp
)

# Link libraries
# NB: the real CMake target from third_party/libmirisdr is "mirisdr_shared"
# (OUTPUT_NAME is "mirisdr", giving libmirisdr.so, but the target
# identifier used for linking/include propagation is mirisdr_shared).
target_link_libraries(SoapyMiri PRIVATE
        SoapySDR
        mirisdr_shared
        log
        android
)
