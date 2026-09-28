cmake_minimum_required(VERSION 3.10)

project(SoapyMiri LANGUAGES CXX)

# SoapyMiri est un MODULE (plugin)
add_library(SoapyMiri MODULE
        Registration.cpp
        Settings.cpp
        Streaming.cpp
)

# Link libraries
target_link_libraries(SoapyMiri PRIVATE
        SoapySDR
        mirisdr
        log
        android
)
