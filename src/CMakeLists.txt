set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(POCKET_SRC
        pocket.cpp
        )

include_directories(${PROJECT_SOURCE_DIR}/include)

# Declare the library
add_library(pocket STATIC ${POCKET_SRC})

# Specify here the include directories exported by this library
target_include_directories(pocket PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
