# CS330-OpenGL-Workspace
A 3D desktop workspace scene built with C++ and OpenGL. Features custom primitives, texture tiling, and a multi-light Phong shading model.

> A fully realized 3D scene built with C++ and OpenGL, demonstrating primitive composition, texture mapping, and multi-light Phong shading.

---

## Table of Contents
- [Project Overview](#project-overview)
- [Artifacts](#artifacts)
- [Technologies Used](#technologies-used)
- [Reflection](#reflection)

---

## Project Overview

This repository contains the final artifacts for **CS 330: Computational Graphics and Visualization**. The centerpiece is a **3D Desktop Workspace Scene** — a technically grounded showcase of low-level graphics programming built from the ground up using **C++** and the **OpenGL** graphics pipeline.

The project demonstrates:
- **Object composition** from 3D primitives (cylinders, tori, box meshes)
- **Realistic texture mapping** with UV tiling and material properties
- **Multi-light Phong shading** using Key Light and Fill Light sources implemented in GLSL

---

## Artifacts

| Artifact | Description |
|---|---|
| `3D Scene Source Code` | Complete C++ solution — mesh generation, shader rendering, and full scene composition |
| `Design Decisions Document` | Retrospective analysis of the creative and technical choices made throughout development |

---

## Technologies Used

| Category | Tools |
|---|---|
| **Language** | C++ |
| **Graphics API** | OpenGL |
| **Libraries** | GLEW, GLFW, GLM (OpenGL Mathematics) |
| **Shaders** | GLSL (Vertex & Fragment Shaders) |
| **IDE** | Visual Studio 2022 |

---

## Reflection

### How do I approach designing software?

Working on this project fundamentally shifted my perspective from purely functional coding to **spatial reasoning and structural decomposition**. I learned to view complex real-world objects — a monitor, a ceramic mug — not as single entities but as composites of fundamental primitives. This demanded a new design skill: mentally visualizing 3D coordinate space *before* writing a single line of code.

My design process followed a **bottom-up approach**:

1. **Foundation** — Implement and render a single shape to validate the pipeline
2. **Composition** — Arrange primitives into recognizable objects (e.g., a torus rotated 90° to form a mug handle)
3. **Aesthetics** — Apply texture tiling to the desk surface and fine-tune material properties for lighting

The core takeaway — **modular decomposition** — is a universal principle I'll carry forward. Whether designing a database schema or a UI component library, isolating complexity into small, reusable pieces keeps software scalable and maintainable.

---

### How do I approach developing programs?

**Defensive Programming**
A major strategy I adopted was building defensively around memory management. Early on, a missing texture file would immediately throw an Access Violation (`0xC0000005`). I implemented input validation within my `SetShaderTexture()` method to catch null pointers and missing assets gracefully, defaulting to a solid color fallback rather than crashing.

**Iterative Development**
The lighting system was built across four deliberate iterations rather than attempted all at once:

| Iteration | Goal |
|---|---|
| 1 | Basic camera with unlit wireframe objects |
| 2 | Static texture application to verify UV mapping |
| 3 | Single dynamic light source |
| 4 | Full GLSL shader array supporting Key Light + Fill Light |

**Evolution of Approach**
My coding approach matured from hard-coded values to flexible, data-driven systems. Early in the project I defined vertices manually for every object. By the end, geometry was generated programmatically via arrays and loops, with dynamic variables passed directly to the GPU — a shift that was essential for managing scene complexity at scale.

---

### How can computer science help me reach my goals?

**Educational Pathway**
Computational graphics gave me a tangible application for abstract mathematics. Seeing how **linear algebra** — scale, rotate, translate matrices — maps directly to visual output solidified my understanding in a way lectures alone could not. This foundation will carry into future coursework involving physics simulations, game engine architecture, and advanced algorithms.

**Professional Pathway**
This project sharpened my skills in **low-level debugging and performance optimization**. Managing memory manually and reasoning about the GPU pipeline makes me a more resilient developer — one capable of writing robust, crash-resistant software. These skills extend well beyond game development into fields like **data visualization, architectural simulation, and training software**, where communicating complex information through 3D visuals is increasingly valuable.

---

*Final project — CS 330: Computational Graphics and Visualization*
