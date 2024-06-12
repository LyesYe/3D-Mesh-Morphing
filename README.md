# 3D-Mesh-Morphing
This project was made in collaboration with @sami delves into the fascinating world of 3D mesh morphing, using Unity to implement and explore various morphing techniques. We focus on three primary methods: linear interpolation, Radial Basis Function (RBF) morphing, and Signed Distance Field (SDF) morphing. This repository is a valuable resource for anyone interested in 3D graphics and animation, offering detailed explanations, code, and visual examples.

## Overview

3D mesh morphing is a technique used to transform one 3D model into another smoothly and seamlessly. This project explores three methods of 3D mesh morphing: Linear Interpolation, Radial Basis Function (RBF) Morphing, and Signed Distance Field (SDF) Morphing. The implementation is done using Unity, a powerful game development engine.

## Morphing Methods

### 1. Linear Interpolation

Linear Interpolation is the most straightforward morphing technique. It works by linearly interpolating the positions of corresponding vertices in the source and target meshes.

- **Concept:** For each vertex in the source mesh, find the corresponding vertex in the target mesh and compute the intermediate positions using linear interpolation.
- **Implementation:** This method involves iterating through each pair of corresponding vertices and applying the formula:
  \[
  V_{morphed} = (1 - t) \cdot V_{source} + t \cdot V_{target}
  \]
  where \( t \) ranges from 0 to 1 over the duration of the morph.
- **Usage:** This technique is computationally efficient and simple to implement, making it suitable for real-time applications where performance is critical.

### 2. Radial Basis Function (RBF) Morphing

RBF Morphing uses radial basis functions to create a smooth transformation of the mesh. This method is more flexible and can handle more complex morphs compared to linear interpolation.

- **Concept:** RBF morphing involves defining a set of control points on both the source and target meshes. The deformation field is computed using radial basis functions, which ensures smooth transitions.
- **Implementation:** The deformation function \( \phi(x) \) is defined as:
  \[
  \phi(x) = \sum_{i=1}^{N} w_i \cdot \phi_i(\| x - c_i \|)
  \]
  where \( c_i \) are the control points, \( \phi_i \) are the radial basis functions, and \( w_i \) are the weights determined by solving a system of linear equations.
- **Usage:** This method is useful for creating smooth, organic deformations and is widely used in character animation and special effects.

### 3. Signed Distance Field (SDF) Morphing

SDF Morphing involves using signed distance fields to represent and morph the shapes. This technique can handle complex topological changes and provides high-quality results.

- **Concept:** An SDF represents a shape by the distance of each point in space to the nearest surface point, with the sign indicating whether the point is inside or outside the shape.
- **Implementation:** The morphing process involves computing the SDF for both the source and target meshes and interpolating between these fields:
  \[
  SDF_{morphed} = (1 - t) \cdot SDF_{source} + t \cdot SDF_{target}
  \]
  The final mesh is then extracted from the morphed SDF using techniques like marching cubes.
- **Usage:** SDF Morphing is powerful for applications requiring high-quality transformations and can handle changes in topology, such as merging or splitting parts of the mesh.



## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

Special thanks to the authors of the referenced algorithms and the contributors of the libraries used in this project.

---

### Place for Images

Include images here to illustrate the morphing techniques:
1. **Linear Interpolation Example:**
   - Before
   - During
   - After

2. **RBF Morphing Example:**
   - Before
   - During
   - After

3. **SDF Morphing Example:**
   - Before
   - During
   - After
