# Sets the minimum version of CMake required to build your native library.
# This ensures that a certain set of CMake features is available to
# your build.

cmake_minimum_required(VERSION 3.4.1)

# Specifies a library name, specifies whether the library is STATIC or
# SHARED, and provides relative paths to the source code. You can
# define multiple libraries by adding multiple add_library() commands,
# and CMake builds them for you. When you build your app, Gradle
# automatically packages shared libraries with your APK.

add_library( # Specifies the name of the library.
        native-lib

        # Sets the library as a shared library.
        SHARED

        # Provides a relative path to your source file(s).
        src/main/cpp/native-lib.cpp
        src/main/cpp/Instance.cpp
        src/main/cpp/TileCache.cpp
        src/main/cpp/Tile.cpp
        src/main/cpp/TextureDrawer.cpp
        )


find_library(log-lib log)

target_link_libraries(
        native-lib

        GLESv2
        jnigraphics
        android

        ${log-lib}
)