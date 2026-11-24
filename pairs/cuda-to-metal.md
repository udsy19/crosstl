# CrossTL translation matrix: CUDA to Metal

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native CUDA probe whose feature Metal has too straight to Metal, and metal checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 89.2 %: 231 supported, 17 refused, 11 wrong, 0 untested.

## Gaps

<details>
<summary>28 gaps: 17 refused, 11 wrong</summary>

Wrong, by cause:

- `use of undeclared identifier '<feature>'` (2): `__isinff`, `__isnanf`
- `use of undeclared identifier 'Low'`: `enum-constant`
- `the translation loses BuiltIn.LocalInvocationIndex`: `local-invocation-index`
- `the translation loses BuiltIn.NumSubgroups`: `num-subgroups`
- `the translation loses BuiltIn.SubgroupId`: `subgroup-id`
- `the translation loses BuiltIn.SubgroupLocalInvocationId`: `subgroup-invocation-id`
- `the translation loses BuiltIn.SubgroupSize`: `subgroup-size`
- `the translation loses Decoration.Restrict`: `restrict-buffer`
- `the translation loses Decoration.Volatile`: `volatile-buffer`
- `the translation loses Dim.Buffer`: `texel-buffer`

Refused, by diagnostic:

- `project.translate.metal-lowering-unsupported: MetalLoweringRefused: Metal cannot lower N construct: function: call to '<feature>', a built-in function of another shading language that Metal does not define and the program does not declare (target metal) [project.translate.metal-lowering-unsupported]` (11): `acoshf`, `asinhf`, `atanhf`, `copysignf`, `cospif`, `exp10f`, `fdimf`, `ldexpf`, `log10f`, `nextafterf`, `sinpif`
- `project.translate.unsupported-feature: UnsupportedMetalFeatureError: Cannot reproduce the std140 layout of cbuffer 'probe_Args' in Metal: type 'cudaTextureObject_t' has no HLSL buffer layout` (2): `texture-argument`, `texture-in-helper`
- `project.translate.metal-refused: MetalRefusal: Metal image store operation 'imageStore' requires float value for texture2d<float, access::read_write> images: u32(fin[i]) has type uint`: `integer-storage-image`
- `project.translate.metal-refused: MetalRefusal: Metal image store operation 'imageStore' requires float value for texture2d<float, access::read_write> images: vec4<u8>(v, v, v, v) has type uint`: `unorm-storage-image`
- `project.translate.undeclared-function: UndeclaredFunctionError: function 'surf2Dread' is not declared: it is neither a CrossGL built-in function nor a function, structure method, type or callable value of the program (target metal) [project.translate.undeclared-function]`: `read-write-image`
- `project.translate.unsupported-feature: UnsupportedMetalFeatureError: Metal codegen cannot reconstruct Metal union 'Bits': source ABI 'cuda' cannot be reconstructed natively`: `union`

</details>
