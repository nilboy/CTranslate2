enable_testing()

add_subdirectory(${CMAKE_SOURCE_DIR}/third_party/googletest ${CMAKE_CURRENT_BINARY_DIR}/googletest)

add_executable(ctranslate2_test
  layers_test.cc
  model_test.cc
  storage_view_test.cc
  ops_test.cc
  transformer_test.cc
  translator_test.cc
  test.cc)
target_link_libraries(ctranslate2_test
  ${PROJECT_NAME}
  gtest_main
  )

add_executable(benchmark_ops
  benchmark_ops.cc
  )
target_link_libraries(benchmark_ops
  ${PROJECT_NAME}
  )
