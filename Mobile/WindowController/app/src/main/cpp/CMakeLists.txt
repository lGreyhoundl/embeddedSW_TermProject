# For more information about using CMake with Android Studio, read the
# documentation: https://d.android.com/studio/projects/add-native-code.html

# Sets the minimum version of CMake required to build the native library.

cmake_minimum_required(VERSION 3.18.1)

# Declares and names the project.

project("windowcontroller")

# Creates and names a library, sets it as either STATIC
# or SHARED, and provides the relative paths to its source code.
# You can define multiple libraries, and CMake builds them for you.
# Gradle automatically packages shared libraries with your APK.

add_library(
        setStepMotor
        SHARED
        setStepMotor.cpp)

add_library(
        setDotMatrix
        SHARED
        setDotMatrix.cpp)

add_library(
        setTextLcd
        SHARED
        setTextLcd.cpp)

add_library(
        setFnd
        SHARED
        setFnd.cpp)

add_library(
        setBuzzer
        SHARED
        setBuzzer.cpp)


find_library( # Sets the name of the path variable.
        log-lib
        # Specifies the name of the NDK library that
        # you want CMake to locate.
        log)


target_link_libraries( # Specifies the target library.
        setStepMotor
        ${log-lib})

target_link_libraries(
        setDotMatrix
        ${log-lib})

target_link_libraries(
        setTextLcd
        ${log-lib})

target_link_libraries(
        setFnd
        ${log-lib})

target_link_libraries(
        setBuzzer
        ${log-lib})