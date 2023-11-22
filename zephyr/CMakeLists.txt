# SPDX-License-Identifier: Apache-2.0
if (CONFIG_ROSIDLL)

zephyr_library_named(rosidl)

target_compile_definitions(rosidl PUBLIC
  )
target_compile_options(rosidl PRIVATE -Wno-unused-variable -Wno-implicit-function-declaration -Wno-int-conversion)

zephyr_include_directories(
  ${ZEPHYR_CURRENT_MODULE_DIR}/rosidl_runtime_c/include
  )

zephyr_library_include_directories(
  ${ZEPHYR_CURRENT_MODULE_DIR}/rosidl_runtime_c/include
  )

file(GLOB_RECURSE Sources
  "${ZEPHYR_CURRENT_MODULE_DIR}/rosidl_runtime_c/src/*.c"
)

#message(STATUS "Sources: ${Sources}")

zephyr_library_sources(
  ${Sources}
)

endif()
