cmake_minimum_required(VERSION 3.10)

project(
  libmorton
  VERSION
    0.2 DESCRIPTION
    "C++ header-only library with methods to efficiently encode/decode Morton codes in/from 2D/3D coordinates"
  LANGUAGES C CXX)

set(LIBMORTON_INCLUDE_DIR
    ${CMAKE_CURRENT_SOURCE_DIR}/libmorton/include/libmorton)

add_library(libmorton INTERFACE)

# Handle include paths
target_include_directories(libmorton
                           INTERFACE $<BUILD_INTERFACE:${LIBMORTON_INCLUDE_DIR}>
                                     $<INSTALL_INTERFACE:include>)

# Modify target compiler properties
target_compile_features(libmorton
                        INTERFACE
                        cxx_std_11 # Require C++11 for some features
                        )
