cmake_minimum_required(VERSION 4.0)

find_package(cmake-bare REQUIRED PATHS node_modules/cmake-bare)
find_package(cmake-fetch REQUIRED PATHS node_modules/cmake-fetch)

project(ninja_runtime C)

fetch_package("github:ninja-build/ninja@1.13.1")

add_custom_target(ninja_runtime ALL DEPENDS ninja)

bare_target(target)

install(
  TARGETS ninja
  RUNTIME DESTINATION ${target}/bin
)
