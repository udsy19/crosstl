# CrossTL translation matrix: WebGL to WGSL

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native WebGL probe whose feature WGSL has too straight to WGSL, and naga checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 98.4 %: 252 supported, 0 refused, 4 wrong, 0 untested.

## Gaps

<details>
<summary>4 gaps: 0 refused, 4 wrong</summary>

Wrong, by cause:

- `no definition in scope for identifier: '<feature>'` (4): `fragment-depth`, `front-facing`, `instance-index`, `vertex-index`

</details>
