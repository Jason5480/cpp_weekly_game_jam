find_package(docopt CONFIG)
find_package(ftxui CONFIG)
find_package(fmt CONFIG)
find_package(spdlog CONFIG)

# Generic test that uses conan libs
add_executable(intro main.cpp)
target_link_libraries(
  intro
  PRIVATE project_options
          project_warnings
          docopt::docopt
          ftxui::screen
          ftxui::dom
          ftxui::component
          fmt::fmt
          spdlog::spdlog)

target_include_directories(intro PRIVATE "${CMAKE_BINARY_DIR}/configured_files/include")
