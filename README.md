# module_NURBS.lib

A static library for NURBS (Non-Uniform Rational B-Splines) curve and surface generation, providing core bridge curve and through-curve mesh calculation functions.

1. Overview
  module_NURBS is a Fortran-based static link library dedicated to NURBS curve/surface modeling. It encapsulates two core exported functions for bridge curve construction and through-curve mesh generation, suitable for CAD, geometric modeling, numerical simulation and other engineering scenarios.
2. Core Functions
   The library exports two callable Fortran subroutines (with DLLEXPORT) interface, compatible with C/Fortran cross-calling:
   2.1 build_bridge_curve - NURBS Bridge Curve Construction
     Generates a smooth bridge curve connecting two given point sets, outputs control points and discrete curve coordinates.

   2.2 Through_Curve_Mesh - Through-Curve Mesh Generation
     Generates a NURBS mesh surface through four boundary curves, based on COONS and 3D curve modules.

3. Compilation & Usage
   3.1 Static Library Compilation
     Compile the source code into a static link library using a Fortran compiler (Intel Fortran/GFortran):
       Intel Fortran: /libs:static option
       GFortran: -static option

   3.2 Calling Method
     1. Include the library module in your project
     2. Call the two exported functions directly (supports Fortran program call, C/C++ cross language call with alias )
     3. Input geometric parameter - Get output curve/mesh coordinates

4. Dependencies
   Fortran 90+ standard

5. Notes
   All geometric coordinates use 3D double-precision floating-points
   Array dimension must be pre-allocated before function calls
   Ensure input point set are vaild 3D coordinate to avoid calculation exceptions
