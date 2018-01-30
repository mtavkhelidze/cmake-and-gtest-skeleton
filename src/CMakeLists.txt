set(CMAKE_INCLUDE_CURRENT_DIR ON)

# Declare the library
add_library(${PROJECT_NAME} STATIC
        pocket.cpp
        )
set_target_properties(${PROJECT_NAME} PROPERTIES PUBLIC_HEADER
        "${PROJECT_SOURCE_DIR}/include/pocket.hxx")

# Specify here the include directories exported by this library
target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})
target_include_directories(${PROJECT_NAME} PUBLIC ${PROJECT_SOURCE_DIR}/include)

install(TARGETS ${PROJECT_NAME}
        LIBRARY ARCHIVE DESTINATION "lib/${PROJECT_NAME}"
        PUBLIC_HEADER DESTINATION "include/${PROJECT_NAME}"
        )
