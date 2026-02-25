# CS330-OpenGL-Workspace
A 3D desktop workspace scene built with C++ and OpenGL. Features custom primitives, texture tiling, and a multi-light Phong shading model.

> A fully realized 3D scene built with C++ and OpenGL, demonstrating primitive composition, UV texture mapping, and multi-light Phong shading from the ground up.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Included Artifacts](#included-artifacts)
- [Dependencies](#dependencies)
- [Technologies Used](#technologies-used)
- [Reflection](#reflection)
  - [Designing Software](#1-how-do-i-approach-designing-software)
  - [Developing Programs](#2-how-do-i-approach-developing-programs)
  - [Computer Science and My Goals](#3-how-can-computer-science-help-me-reach-my-goals)

---

## Project Overview

This repository contains the final artifacts for **CS 330: Computational Graphics and Visualization**. The centerpiece is a **3D Desktop Workspace Scene**, a technically grounded showcase of low-level graphics programming built using **C++** and the **OpenGL** graphics pipeline.

The scene demonstrates three core competencies:

- **Object composition** by assembling real-world objects from 3D primitives (cylinders, tori, and box meshes)
- **Texture mapping** with UV tiling and per-object material properties
- **Multi-light Phong shading** using Key Light and Fill Light sources written in GLSL

---

## Included Artifacts

| Artifact | Description |
|---|---|
| **3D Scene Source Code** | Complete C++ solution covering mesh generation, shader rendering, and full scene composition |
| **Design Decisions Document** | Retrospective analysis of the creative and technical choices made throughout development |

---

## Dependencies

The 3D scene source code requires the following libraries to build and run. These are **not included in this repository** due to file size constraints. Download and configure each one before opening the project in Visual Studio 2022.

| Library | Purpose | Download |
|---|---|---|
| **GLEW** 2.1.0 | OpenGL extension loader | [glew.sourceforge.net](http://glew.sourceforge.net/) |
| **GLFW** 3.x | Window creation and input handling | [glfw.org](https://www.glfw.org/download.html) |
| **GLM** 0.9.9+ | Mathematics library for graphics (vectors, matrices) | [github.com/g-truc/glm](https://github.com/g-truc/glm) |
| **stb_image** | Single-header image loader for textures | [github.com/nothings/stb](https://github.com/nothings/stb) |

### Setup Instructions

1. Download each library from the links above
2. Place headers and `.lib` files in your Visual Studio project's include and library directories
3. In Visual Studio, confirm the following under **Project Properties:**
   - `C/C++ > Additional Include Directories` points to your include folder
   - `Linker > Additional Library Directories` points to your lib folder
   - `Linker > Input > Additional Dependencies` includes `glew32.lib`, `glfw3.lib`, and `opengl32.lib`
4. Copy `glew32.dll` into the same directory as the compiled `.exe`

---

## Technologies Used

| Category | Tools |
|---|---|
| **Language** | C++ |
| **Graphics API** | OpenGL |
| **Libraries** | GLEW, GLFW, GLM (OpenGL Mathematics) |
| **Shaders** | GLSL (Vertex and Fragment Shaders) |
| **IDE** | Visual Studio 2022 |

---

## Reflection

### 1. How do I approach designing software?

This project shifted my perspective from purely functional coding toward **spatial reasoning and structural decomposition**. I learned to view complex real-world objects, such as a computer monitor or a ceramic mug, not as single entities but as composites of fundamental primitives. That required a new skill: mentally visualizing 3D coordinate space before writing a single line of code.

My design process followed a **bottom-up approach** across three phases:

1. **Foundation** -- Implement and render a single shape to validate the full pipeline
2. **Composition** -- Arrange primitives into recognizable objects (for example, a torus rotated 90 degrees to form a mug handle)
3. **Aesthetics** -- Apply texture tiling to the desk surface and tune material properties for the lighting model

The core principle, **modular decomposition**, is universally transferable. Whether designing a database schema or a UI component library, isolating complexity into small and reusable pieces keeps software scalable and maintainable over time.

---

### 2. How do I approach developing programs?

#### Defensive Programming

A major strategy I adopted was building defensively around memory management. Early in the project, a missing texture file would immediately throw an Access Violation (`0xC0000005`). I resolved this by adding input validation inside my `SetShaderTexture()` method to handle null pointers and missing assets gracefully, defaulting to a solid color fallback rather than crashing the application.

#### Iterative Development

The lighting system was built across four deliberate iterations rather than attempted all at once:

| Iteration | Focus |
|---|---|
| **1** | Basic camera with unlit wireframe objects |
| **2** | Static texture application to verify UV mapping |
| **3** | Single dynamic light source |
| **4** | Full GLSL shader array supporting Key Light and Fill Light |

#### Evolution of Approach

My coding matured from hard-coded values to flexible, data-driven systems. Early on, I defined vertices manually for every object. By the final milestone, geometry was generated programmatically through arrays and loops, with dynamic variables passed directly to the GPU. This shift from static code to dynamic logic was essential for managing the complexity of the full scene.

---

### 3. How can computer science help me reach my goals?

#### Educational Pathway

Computational graphics gave me a concrete application for abstract mathematics. Watching **linear algebra** operations (scale, rotate, translate matrices) produce direct visual output solidified concepts that lectures alone could not. That foundation will carry into future coursework in physics simulations, game engine architecture, and advanced algorithms.

#### Professional Pathway

This project sharpened my skills in **low-level debugging and performance optimization**. Managing memory manually and reasoning about the GPU pipeline makes me a more resilient developer, one capable of writing robust and crash-resistant software. These skills extend well beyond game development into fields like **data visualization, architectural simulation, and training software**, where communicating complex information through interactive 3D environments is growing in demand.

---

*Final Project for CS 330: Computational Graphics and Visualization*
