cmake_minimum_required(VERSION 3.20)

# Create ImGui library
add_library(imgui STATIC
    imgui.cpp
    imgui_demo.cpp
    imgui_draw.cpp
    imgui_tables.cpp
    imgui_widgets.cpp
    
    # Backends for SDL3 and Vulkan
    backends/imgui_impl_sdl3.cpp
    backends/imgui_impl_vulkan.cpp
)

target_include_directories(imgui PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_CURRENT_SOURCE_DIR}/backends
)

# Set C++ standard to match parent
target_compile_features(imgui PUBLIC cxx_std_20)