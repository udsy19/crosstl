# CrossTL translation matrix: SPIR-V to Metal

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native SPIR-V probe whose feature Metal has too straight to Metal, and metal checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 97.6 %: 401 supported, 8 refused, 2 wrong, 9 untested.

## Gaps

<details>
<summary>10 gaps: 8 refused, 2 wrong</summary>

Wrong, by cause:

- `use of undeclared identifier 'gl_GlobalInvocationID'`: `invocation-id-in-helper`
- `the translation loses Decoration.Volatile`: `volatile-buffer`

Refused, by diagnostic:

- `project.translate.metal-stage-unsupported: MetalStageUnsupportedError: Metal evaluates tessellated patches in a [[patch]] post-tessellation vertex function that reads its control points and per-patch data through [[stage_in]] (Metal Shading Language Specification N.N.N); a tessellation evaluation stage that reads <feature>, <feature> and per-vertex input arrays, as GLSL` (3): `tessellation-domain-quads`, `tessellation-evaluation`, `tessellation-patch-input`
- `project.translate.metal-lowering-unsupported: MetalLoweringRefused: Metal cannot lower N constructs: function: call to 'beginInvocationInterlockARB', a built-in function of another shading language that Metal does not define and the program does not declare; function: call to 'endInvocationInterlockARB', a built-in function of another shading language that Metal doe` (2): `rasterizer-ordered-buffer`, `rasterizer-ordered-image`
- `project.translate.metal-unsized-array-unsupported: UnsizedArrayUnsupportedError: unsized array 'B0.fin' is a struct member: only a storage buffer's last member or an array of resources may omit its element count (HLSL allows unsized arrays only for resources, MSL array bounds are constant expressions, and GLSL and WGSL allow runtime-sized arrays only as the last member of a stor` (2): `OpControlBarrier`, `OpGroupNonUniformElect`
- `project.translate.metal-refused: MetalRefusal: Metal fragment semantic 'gl_SampleMaskIn' maps to 'sample_mask' and requires parameter 'cgl_SampleMaskIn' to have type uint, got int[N]`: `sample-mask-input`

</details>

<details>
<summary>9 untested: control-flow 3, operator 1, type 5</summary>

- `dxc or spirv-dis is not installed` (7): `bool-bitwise`, `default-argument`, `enum-constant`, `generic-function`, `integer-condition`, `struct-method`, `type-alias`
- `slangc or spirv-dis is not installed` (2): `pointer-arithmetic`, `pointer-local`

</details>
