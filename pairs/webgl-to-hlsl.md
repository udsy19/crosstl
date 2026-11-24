# CrossTL translation matrix: WebGL to HLSL

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native WebGL probe whose feature HLSL has too straight to HLSL, and dxc checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 99.6 %: 256 supported, 0 refused, 1 wrong, 0 untested.

## Gaps

<details>
<summary>1 gaps: 0 refused, 1 wrong</summary>

Wrong, by cause:

- `use of undeclared identifier 'gl_ViewID_OVR'`: `view-index`

</details>
