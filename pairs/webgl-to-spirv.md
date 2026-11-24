# CrossTL translation matrix: WebGL to SPIR-V

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native WebGL probe whose feature SPIR-V has too straight to SPIR-V, and spirv-val checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 99.7 %: 296 supported, 1 refused, 0 wrong, 0 untested.

## Gaps

<details>
<summary>1 gaps: 1 refused, 0 wrong</summary>

Refused, by diagnostic:

- `project.translate.vulkan-lowering-unsupported: SpirvLoweringRefused: SPIR-V cannot lower N construct: Unknown variable gl_ViewID_OVR (target vulkan) [project.translate.vulkan-lowering-unsupported]`: `view-index`

</details>
