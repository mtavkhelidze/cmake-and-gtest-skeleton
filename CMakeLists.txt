cmake_minimum_required(VERSION 3.8)
project(pocket)

set(CMAKE_CXX_STANDARD 11)

if (${CMAKE_BUILD_TYPE} MATCHES "Debug")
    # Download and unpack googletest at configure time
    set(INSTALL_GTEST OFF CACHE BOOL "Do not install gtest" FORCE)
    set(INSTALL_GMOCK OFF CACHE BOOL "Do not install gmock" FORCE)

    configure_file(CMakeLists.txt.in
            googletest-download/CMakeLists.txt)
    execute_process(COMMAND ${CMAKE_COMMAND} -G "${CMAKE_GENERATOR}" .
            WORKING_DIRECTORY ${CMAKE_BINARY_DIR}/googletest-download)
    execute_process(COMMAND ${CMAKE_COMMAND} --build .
            WORKING_DIRECTORY ${CMAKE_BINARY_DIR}/googletest-download)

    # Prevent GoogleTest from overriding our compiler/linker options
    # when building with Visual Studio
    set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)

    # Add googletest directly to our build. This adds
    # the following targets: gtest, gtest_main, gmock
    # and gmock_main
    add_subdirectory(${CMAKE_BINARY_DIR}/googletest-src
            ${CMAKE_BINARY_DIR}/googletest-build)

    enable_testing()
    add_subdirectory(test)
endif ()

add_subdirectory(src)
