# imgui playground

Place to experiment with imgui.

## Getting Started

1. Clone repo.
1. Follow guide below on setting up headers and linked libraries.

### Process

imgui requires it’s own headers (e.g. `imgui.h`), as well as a headers and a library for handling the API between the graphics driver (like GLFW for OpenGL, or SDL for Vulkan/OpenGL). You can use [the imgui examples](https://github.com/ocornut/imgui/tree/master/examples) as the basis for new project, but you’ll need to link up the headers and libraries (unless you’re working directly out of the cloned repo, then you’d only need to setup the library portion).

1. Clone the repo and navigate to the folder (e.g. `imgui-playground`)
2. Create 2 folders inside `imgui-playground` called `includes` and `libs`.
3. [Download the imgui repo](https://github.com/ocornut/imgui/archive/refs/heads/master.zip) and pick an example (e.g. [OpenGL 3.0 GLFW](https://github.com/ocornut/imgui/tree/master/examples/example_glfw_opengl3))
4. Copy the `.cpp` and `.h` files in the `imgui` repo root to your `includes` folder.
5. [Download the GLFW binaries and headers](https://www.glfw.org/download).
6. Extract the `lib-vc2022` into your `libs` folder.
7. Extract the 2 header files (`glfw3.h` and `glfw3native.h`) into the `includes/glfw` folder.
8. Open up the `.vcxproj` file inside the any app/prototype folder (e.g. `imgui_glfw_opengl3`)
9. **Right click** the project name in the **Solution Explorer** window and select **Properties**
10. Go to **C/C++** in left sidebar and go to **Edit** under **Additional Include Directories.**
11. Add all the `includes` folders we created. This lets us `include <headername.h>` stuff.
12. Now lets add the GLFW library that the header is linked to. Go to **Linker** in **Sidebar** and go to **Edit** under **Additional Library Directories.**
13. Add the `libs/lib-vc2022` folder we created and extracted things to.
14. Try building and running the project.

> ℹ️ Since the includes and libraries are a folder above the project, we can copy/paste the example folder and make other projects as needed — without having to copy the imgui headers again.
