
cmake_minimum_required(VERSION 3.10.2)
project(EdgeViewAR)

add_library(native-lib SHARED
    jni/native-lib.cpp
    jni/image_processor.cpp
    gl/GLUtils.cpp
    gl/TextureRenderer.cpp)

find_package(OpenCV REQUIRED)

target_include_directories(native-lib PRIVATE
    ${OpenCV_INCLUDE_DIRS}
    jni
    gl)

target_link_libraries(native-lib
    ${OpenCV_LIBS}
    android
    log
    GLESv2
    jnigraphics)
