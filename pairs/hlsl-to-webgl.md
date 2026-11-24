# CrossTL translation matrix: HLSL to WebGL

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native HLSL probe whose feature WebGL has too straight to WebGL, and glslangValidator checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 73.3 %: 11 supported, 4 refused, 0 wrong, 0 untested.

## Gaps

<details>
<summary>4 gaps: 4 refused, 0 wrong</summary>

Refused, by diagnostic:

- `project.translate.webgl-lowering-unsupported: WebGLLoweringRefused: WebGL cannot lower N construct: WebGL target does not support storage buffer resource '<probe>' (RWStructuredBuffer) (target webgl) [project.translate.webgl-lowering-unsupported]` (3): `ddx`, `ddy`, `fwidth`
- `project.translate.relative-vertex-id-unsupported: RelativeVertexIdUnsupportedError: gl_RelativeVertexID (Direct3D SV_VertexID): vertex entry point '<probe>' reads it, which excludes the draw's base vertex while the target's vertex index includes it, and GLSL ES N.N has no base vertex to subtract; declare source_options={'zero_base_vertex': True} if every draw has a zero base vertex (`: `vertex-index`

</details>
