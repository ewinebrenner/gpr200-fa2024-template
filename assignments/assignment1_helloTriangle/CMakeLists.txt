#Hello Triangle example

file(
 GLOB_RECURSE HELLOTRIANGLE_INC CONFIGURE_DEPENDS
 RELATIVE ${CMAKE_CURRENT_SOURCE_DIR}
 *.h *.hpp
)

file(
 GLOB_RECURSE HELLOTRIANGLE_SRC CONFIGURE_DEPENDS
 RELATIVE ${CMAKE_CURRENT_SOURCE_DIR}
 *.c *.cpp
)

install(FILES ${HELLOTRIANGLE_INC} DESTINATION include/assignment1_helloTriangle)
add_executable(assignment1_helloTriangle ${HELLOTRIANGLE_SRC} ${HELLOTRIANGLE_INC} ${HELLOTRIANGLE_ASSETS})
target_link_libraries(assignment1_helloTriangle PUBLIC core IMGUI glm)
target_include_directories(assignment1_helloTriangle PUBLIC ${CORE_INC_DIR} ${stb_INCLUDE_DIR})