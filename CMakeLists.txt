cmake_minimum_required(VERSION 3.5)
project(OpenGL_1 VERSION 0.1.0 LANGUAGES C CXX)

include(CTest)
enable_testing()

set(IMGUI_DIR ${CMAKE_SOURCE_DIR}/imgui)
file(GLOB IMGUI_SOURCES
    ${IMGUI_DIR}/imgui.cpp
    ${IMGUI_DIR}/imgui_demo.cpp
    ${IMGUI_DIR}/imgui_draw.cpp
    ${IMGUI_DIR}/imgui_tables.cpp
    ${IMGUI_DIR}/imgui_widgets.cpp
)

include_directories(${PROJECT_SOURCE_DIR}/include)

add_executable(OpenGL_1 src/main.cpp
${IMGUI_SOURCES}
)

set_property(TARGET OpenGL_1 PROPERTY CXX_STANDARD 17)

target_include_directories(OpenGL_1 PRIVATE
${CMAKE_CURRENT_SOURCE_DIR}/src/imgui
)

link_directories(<C:/glfw-3.3.8.bin.WIN64>)

target_include_directories(OpenGL_1 PRIVATE
    ${IMGUI_DIR}
)

include_directories(${GLFW_INCLUDE_DIRS})
target_link_libraries(OpenGL_1 glfw)