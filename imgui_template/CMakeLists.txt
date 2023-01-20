# CMakeList.txt : CMake project for imgui_template, include source and define
# project specific logic here.
#

# glfw3
find_package(glfw3 REQUIRED)
include_directories(${GLFW_INCLUDE_DIRS})

# opengl
find_package(OpenGL REQUIRED)
include_directories(${OPENGL_INCLUDE_DIRS})

# Add source to this project's executable.
add_executable (imgui_template "imgui_template.cpp" "imgui_template.h" "imgui/imconfig.h" "imgui/imgui.cpp" "imgui/imgui.h" "imgui/imgui_demo.cpp" "imgui/imgui_draw.cpp" "imgui/imgui_impl_glfw.cpp" "imgui/imgui_impl_glfw.h" "imgui/imgui_impl_opengl3.cpp" "imgui/imgui_impl_opengl3.h" "imgui/imgui_impl_opengl3_loader.h" "imgui/imgui_internal.h" "imgui/imgui_stdlib.cpp" "imgui/imgui_stdlib.h" "imgui/imgui_tables.cpp" "imgui/imgui_widgets.cpp" "imgui/imstb_rectpack.h" "imgui/imstb_textedit.h" "imgui/imstb_truetype.h" "zpp_bits/zpp_bits.h")

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET imgui_template PROPERTY CXX_STANDARD 20)
endif()

# TODO: Add tests and install targets if needed.

target_link_libraries(${PROJECT_NAME} PRIVATE
	glfw
	${OPENGL_LIBRARIES}
)