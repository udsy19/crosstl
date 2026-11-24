# CrossTL translation matrix: SPIR-V to WebGL

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native SPIR-V probe whose feature WebGL has too straight to WebGL, and glslangValidator checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 75.0 %: 15 supported, 5 refused, 0 wrong, 0 untested.

## Gaps

<details>
<summary>5 gaps: 5 refused, 0 wrong</summary>

Refused, by diagnostic:

- `project.translate.webgl-lowering-unsupported: WebGLLoweringRefused: WebGL cannot lower N construct: WebGL target does not support storage buffer resource '_' (RWStructuredBuffer) (target webgl) [project.translate.webgl-lowering-unsupported]` (5): `OpDPdx`, `OpDPdy`, `OpFwidth`, `OpImageSampleImplicitLod`, `OpImageSampleProjImplicitLod`

</details>
