cmake_minimum_required(VERSION 3.10)
project(VulkanApp)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Homebrew paths for Apple Silicon
include_directories(/opt/homebrew/opt/glfw/include)
link_directories(/opt/homebrew/opt/glfw/lib)

find_package(Vulkan REQUIRED)
find_package(glm REQUIRED)

add_executable(VulkanApp
        main.cpp
        lve_window.cpp
        first_app.cpp
        lve_pipeline.cpp
        lve_device.cpp
        lve_swap_chain.cpp
        lve_model.cpp
)

target_include_directories(VulkanApp PRIVATE ${GLM_INCLUDE_DIRS})
target_link_libraries(VulkanApp
        glfw
        ${Vulkan_LIBRARIES}
        glm::glm
)