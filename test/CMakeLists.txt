include_directories("${PROJECT_SOURCE_DIR}")

set(PROJECT_TEST_NAME ${PROJECT_NAME}-test)
# First Simple Google Test
add_executable(${PROJECT_TEST_NAME} main.cpp pass_and_fail_test.cpp)

include_directories(${PROJECT_SOURCE_DIR}/include)

target_link_libraries(${PROJECT_TEST_NAME} gtest gmock_main ${PROJECT_NAME})

add_test(NAME ${PROJECT_TEST_NAME}-runner COMMAND ${PROJECT_TEST_NAME})
