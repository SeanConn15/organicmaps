project(benchmark_tool)

include_directories(
  ${OMIM_ROOT}/3party/gflags/src
  ${OMIM_ROOT}/3party/jansson/src
)

set(
  SRC
  api.cpp
  api.hpp
  features_loading.cpp
  main.cpp
)

omim_add_executable(${PROJECT_NAME} ${SRC})

omim_link_libraries(
  ${PROJECT_NAME}
  map
  ge0
  editor
  indexer
  geometry
  platform
  coding
  base
  gflags
  icu
  jansson
  oauthcpp
  opening_hours
  protobuf
  pugixml
  succinct
  ${LIBZ}
)

link_qt5_core(${PROJECT_NAME})
link_qt5_network(${PROJECT_NAME})
