# CrossTL translation matrix: HLSL to GLSL

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native HLSL probe whose feature GLSL has too straight to GLSL, and glslangValidator checked the result. Its compute probes also ran on a runtime. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 94.8 %: 421 supported, 20 refused, 3 wrong, 0 untested.

## Gaps

<details>
<summary>23 gaps: 20 refused, 3 wrong</summary>

Wrong, by cause:

- `on vulkan-lavapipe as SPIR-V from dxc and glslangValidator, the translation computes different results from the native probe`: `cross`
- `the translation loses ImageFormat.R32ui`: `integer-storage-image`
- `the translation loses ImageFormat.Rgba8`: `unorm-storage-image`

Refused, by diagnostic:

- `project.translate.opengl-geometry-stream-unsupported: GeometryStreamUnsupportedError: input vertex member 'position' is an array or structure; opengl geometry shaders write vertices through stage outputs and EmitVertex() (target opengl) [project.translate.opengl-geometry-stream-unsupported]` (10): `Stream.Append`, `Stream.RestartStrip`, `geometry-input-lines`, `geometry-input-lines-adjacency`, `geometry-input-triangles`, `geometry-input-triangles-adjacency`, `geometry-invocations`, `geometry-output-line-strip`, `geometry-output-triangle-strip`, `geometry-streams`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N construct: call to '<feature>', which is neither a GLSL built-in function nor a function the program declares (target opengl) [project.translate.opengl-lowering-unsupported]` (4): `InterlockedCompareExchangeFloatBitwise`, `InterlockedCompareStoreFloatBitwise`, `f16tof32`, `f32tof16`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N constructs: tessellation patch parameter 'patch' of type 'OutputPatch<ControlPoint, 3>' has no GLSL stage variable form: GLSL reads control points through <feature>[] and per-vertex input arrays; GLSL tessellation_evaluation stage cannot declare HLSL control-point patch parameter '` (3): `tessellation-evaluation`, `tessellation-level-input`, `tessellation-patch-input`
- `project.translate.opengl-geometry-stream-unsupported: GeometryStreamUnsupportedError: input vertex member 'position' is an array or structure; opengl geometry shaders write vertices through stage outputs and EmitVertex() (target opengl) [project.translate.opengl-geometry-stream-unsupported]`: `geometry`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N constructs: tessellation patch parameter 'patch' of type 'OutputPatch<ControlPoint, 2>' has no GLSL stage variable form: GLSL reads control points through gl_in[] and per-vertex input arrays; GLSL tessellation_evaluation stage cannot declare HLSL control-point patch parameter '`: `tessellation-domain-isolines`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N constructs: tessellation patch parameter 'patch' of type 'OutputPatch<ControlPoint, 4>' has no GLSL stage variable form: GLSL reads control points through gl_in[] and per-vertex input arrays; GLSL tessellation_evaluation stage cannot declare HLSL control-point patch parameter '`: `tessellation-domain-quads`

</details>
