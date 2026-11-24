# CrossTL translation matrix: SPIR-V to GLSL

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native SPIR-V probe whose feature GLSL has too straight to GLSL, and glslangValidator checked the result. Its compute probes also ran on a runtime. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 98.6 %: 503 supported, 7 refused, 0 wrong, 0 untested.

## Gaps

<details>
<summary>7 gaps: 7 refused, 0 wrong</summary>

Refused, by diagnostic:

- `project.translate.opengl-unsized-array-unsupported: UnsizedArrayUnsupportedError: unsized array 'B0.fin' is a struct member: only a storage buffer's last member or an array of resources may omit its element count (HLSL allows unsized arrays only for resources, MSL array bounds are constant expressions, and GLSL and WGSL allow runtime-sized arrays only as the last member of a stor` (6): `OpControlBarrier`, `OpGroupNonUniformElect`, `OpImageQueryLevels`, `OpImageQuerySamples`, `OpImageQuerySize`, `OpMemoryBarrier`
- `project.translate.opengl-refused: OpenGLRefusal: OpenGL texture operation 'textureLod' requires a declared texture or image resource argument: FunctionCallNode(function=IdentifierNode(name=nonuniformEXT), arguments=N)`: `array-of-textures-nonuniform-index`

</details>
