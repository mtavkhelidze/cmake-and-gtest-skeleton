set(CMAKE_INCLUDE_CURRENT_DIR ON)

include_directories(${PROJECT_SOURCE_DIR}/include)

# Declare the library
add_library(pocket STATIC
        pocket.cpp
        )

# Specify here the include directories exported by this library
target_include_directories(pocket PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
