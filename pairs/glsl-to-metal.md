# CrossTL translation matrix: GLSL to Metal

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native GLSL probe whose feature Metal has too straight to Metal, and metal checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 97.3 %: 403 supported, 6 refused, 5 wrong, 0 untested.

## Gaps

<details>
<summary>11 gaps: 6 refused, 5 wrong</summary>

Wrong, by cause:

- `use of undeclared identifier '<feature>'` (4): `layer`, `sample-mask-input`, `view-index`, `viewport-index`
- `the translation loses Decoration.Restrict`: `restrict-buffer`

Refused, by diagnostic:

- `project.translate.metal-stage-unsupported: MetalStageUnsupportedError: Metal evaluates tessellated patches in a [[patch]] post-tessellation vertex function that reads its control points and per-patch data through [[stage_in]] (Metal Shading Language Specification N.N.N); a tessellation evaluation stage that reads <feature>, <feature> and per-vertex input arrays, as GLSL` (3): `tessellation-domain-quads`, `tessellation-evaluation`, `tessellation-patch-input`
- `project.translate.metal-lowering-unsupported: MetalLoweringRefused: Metal cannot lower N constructs: function: call to 'beginInvocationInterlockARB', a built-in function of another shading language that Metal does not define and the program does not declare; function: call to 'endInvocationInterlockARB', a built-in function of another shading language that Metal doe` (2): `rasterizer-ordered-buffer`, `rasterizer-ordered-image`
- `project.translate.stage-interface-unsupported: StageInterfaceUnsupportedError: the fragment entry point '<probe>' takes parameters or returns a value as well as reading and writing stage-level interface variables; metal entry points receive inputs and return outputs as structures (target metal) [project.translate.stage-interface-unsupported]`: `stencil-export`

</details>
