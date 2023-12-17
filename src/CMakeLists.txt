# The Flutter tooling requires that developers have CMake 3.10 or later
# installed. You should not increase this version, as doing so will cause
# the plugin to fail to compile for some customers of the plugin.
cmake_minimum_required(VERSION 3.10)

project(demo_ffi_example_library VERSION 0.0.1 LANGUAGES C)

add_library(demo_ffi_example SHARED
  "demo_ffi_example.c"
)

set_target_properties(demo_ffi_example PROPERTIES
  PUBLIC_HEADER demo_ffi_example.h
  OUTPUT_NAME "demo_ffi_example"
)

target_compile_definitions(demo_ffi_example PUBLIC DART_SHARED_LIB)
