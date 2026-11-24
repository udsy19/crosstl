# CrossTL translation matrix: Metal to WebGL

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native Metal probe whose feature WebGL has too straight to WebGL, and glslangValidator checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 72.2 %: 13 supported, 3 refused, 2 wrong, 0 untested.

## Gaps

<details>
<summary>5 gaps: 3 refused, 2 wrong</summary>

Wrong, by cause:

- `the translation loses BuiltIn.ViewIndex, Capability.MultiView`: `view-index`
- `the translation loses Decoration.Centroid`: `centroid-interpolation`

Refused, by diagnostic:

- `project.translate.webgl-lowering-unsupported: WebGLLoweringRefused: WebGL cannot lower N construct: WebGL target does not support storage buffer resource '<probe>' (RWStructuredBuffer) (target webgl) [project.translate.webgl-lowering-unsupported]` (3): `dfdx`, `dfdy`, `fwidth`

</details>
