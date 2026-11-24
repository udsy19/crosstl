# CrossTL translation matrix: WebGL to Slang

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native WebGL probe whose feature Slang has too straight to Slang, and slangc checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 97.4 %: 259 supported, 6 refused, 1 wrong, 0 untested.

## Gaps

<details>
<summary>7 gaps: 6 refused, 1 wrong</summary>

Wrong, by cause:

- `error[E30015]: undefined identifier 'gl_ViewID_OVR'`: `view-index`

Refused, by diagnostic:

- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: call to <feature>: <feature> is a built-in function of another language, and Slang declares no function of that name (target slang) [project.translate.slang-lowering-unsupported]` (6): `packHalf2x16`, `packSnorm2x16`, `packUnorm2x16`, `unpackHalf2x16`, `unpackSnorm2x16`, `unpackUnorm2x16`

</details>
