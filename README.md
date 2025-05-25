# 🧱 DirectX-DualCubeRenderer

This project is a **DirectX 11 graphics application** built with C++. It renders two cubes on screen — one rotating clockwise and one counter-clockwise — using a full graphics pipeline setup including:

- Device/swapchain creation
- Custom vertex/index buffers
- HLSL shaders
- Matrix transformations
- Wireframe rasterizer

## 🖼️ Features

- Real-time cube rendering with `D3D11`
- **Two independent rotations** around the Y-axis
- World → View → Projection matrix transformation
- Wireframe rendering using custom rasterizer state
- ComPtr for safe COM object management

## 🧱 Core Files

| File             | Description                                     |
|------------------|-------------------------------------------------|
| `DirectXApp.cpp` | Main application logic (init, render, update)   |
| `DirectXApp.h`   | Class declaration and private DirectX members   |
| `Geometry.h`     | Vertex structure and mesh definitions (not shown) |
| `README.md`      | This documentation                              |

## 📐 Render Pipeline

```text
World Transform
   ↓
View Transform (LookAtLH)
   ↓
Projection Transform (PerspectiveFovLH)
   ↓
Shader Pipeline (HLSL)
   ↓
Output to Back Buffer
```

## 🎮 What It Does

Bottom cube: rotates around Y-axis clockwise
Top cube: rotates around Y-axis counter-clockwise
Constant buffers pass the transformation matrix to shaders
IASetVertexBuffers, VSSetShader, and DrawIndexed used for rendering

## 🖥️ How to Build & Run

Open in Visual Studio with DirectX 11 SDK installed.
Make sure your Geometry.h and Shader.hlsl files are present.
Press F5 to build and run.
You’ll see two cubes rotating above/below each other.

## 📚 Concepts Covered

DirectX initialization (device/context/swapchain)
Depth buffer and render target setup
Constant buffers and matrix math
Viewport resizing and handling WM_SIZE
Rasterizer state (wireframe toggle)

## 🧠 Learning Outcomes

How to build a full DirectX rendering pipeline
Using transformation matrices in 3D graphics
Implementing animation through rotation updates
Structuring DirectX apps using C++ classes and COM wrappers
