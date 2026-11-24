# CrossTL translation matrix: CUDA to HLSL

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native CUDA probe whose feature HLSL has too straight to HLSL, and dxc checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 94.7 %: 251 supported, 9 refused, 5 wrong, 0 untested.

## Gaps

<details>
<summary>14 gaps: 9 refused, 5 wrong</summary>

Wrong, by cause:

- `use of undeclared identifier '<feature>'` (2): `__isinff`, `__isnanf`
- `use of undeclared identifier 'Low'`: `enum-constant`
- `the translation loses BuiltIn.SubgroupSize`: `subgroup-size`
- `the translation loses Dim.Buffer, Capability.SampledBuffer`: `texel-buffer`

Refused, by diagnostic:

- `project.translate.directx-lowering-unsupported: DirectXLoweringRefused: DirectX cannot lower N construct: type: the built-in type 'cudaTextureObject_t' has no DirectX spelling (target directx) [project.translate.directx-lowering-unsupported]` (2): `texture-argument`, `texture-in-helper`
- `project.translate.rule-inexpressible: RuleInexpressibleError: __cgl_libm_sin on a N-bit floating-point operand has no helper for directx: the helper takes binary32 values only (target directx) [project.translate.rule-inexpressible]` (2): `sin`, `sincos`
- `project.translate.directx-contextual-conversion-unrepresentable: DirectXContextualConversionError: DirectX canonical atan2 requires two matching floating scalar or vector operands`: `atan2`
- `project.translate.directx-refused: DirectXRefusal: DirectX image store operation 'imageStore' requires float value for RWTexture2D<float4> images: u32(fin[i]) has type uint`: `integer-storage-image`
- `project.translate.directx-refused: DirectXRefusal: DirectX image store operation 'imageStore' requires float value for RWTexture2D<float4> images: vec4<u8>(v, v, v, v) has type uint`: `unorm-storage-image`
- `project.translate.rule-inexpressible: RuleInexpressibleError: __cgl_libm_cos on a N-bit floating-point operand has no helper for directx: the helper takes binary32 values only (target directx) [project.translate.rule-inexpressible]`: `cos`
- `project.translate.undeclared-function: UndeclaredFunctionError: function 'surf2Dread' is not declared: it is neither a CrossGL built-in function nor a function, structure method, type or callable value of the program (target directx) [project.translate.undeclared-function]`: `read-write-image`

</details>
