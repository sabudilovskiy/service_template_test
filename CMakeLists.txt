cmake_minimum_required(VERSION 3.12)
project(service_template CXX)

# Adding userver dependency
add_subdirectory(third_party/userver)
userver_setup_environment()


# The Service
add_executable(${PROJECT_NAME} src/main.cpp)
target_link_libraries(${PROJECT_NAME} PUBLIC userver-core)

# Functional Tests
include(UserverTestsuite)

userver_testsuite_add_simple()