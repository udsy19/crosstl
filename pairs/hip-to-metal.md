# CrossTL translation matrix: HIP to Metal

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native HIP probe whose feature Metal has too straight to Metal, and metal checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 90.0 %: 234 supported, 15 refused, 11 wrong, 0 untested.

## Gaps

<details>
<summary>26 gaps: 15 refused, 11 wrong</summary>

Wrong, by cause:

- `use of undeclared identifier '<feature>'` (3): `__isinff`, `__isnanf`, `invocation-id-in-helper`
- `use of undeclared identifier 'Low'`: `enum-constant`
- `use of undeclared identifier '__lane_id'`: `subgroup-invocation-id`
- `the translation loses BuiltIn.LocalInvocationIndex`: `local-invocation-index`
- `the translation loses BuiltIn.NumSubgroups`: `num-subgroups`
- `the translation loses BuiltIn.SubgroupId`: `subgroup-id`
- `the translation loses Decoration.Restrict`: `restrict-buffer`
- `the translation loses Decoration.Volatile`: `volatile-buffer`
- `the translation loses Dim.Buffer`: `texel-buffer`

Refused, by diagnostic:

- `project.translate.metal-lowering-unsupported: MetalLoweringRefused: Metal cannot lower N construct: function: call to '<feature>', a built-in function of another shading language that Metal does not define and the program does not declare (target metal) [project.translate.metal-lowering-unsupported]` (8): `copysignf`, `cospif`, `exp10f`, `fdimf`, `ldexpf`, `log10f`, `nextafterf`, `sinpif`
- `project.translate.metal-refused: MetalRefusal: Metal function call 'lookup' requires resource parameter t of type texture2d<float>: argument tex has sampler` (2): `texture-argument`, `texture-in-helper`
- `project.translate.hip-record-semantics-unsupported: HipRecordSemanticError: HIP record method call 'width' is unsupported for record 'Span' in call expression`: `struct-method`
- `project.translate.hip-surface-byte-offset-unproven: HipSurfaceByteOffsetError: surf2Dwrite cannot scale its x byte offset N: the element type is unknown, so the offset cannot be shown to be a multiple of the element size [project.translate.hip-surface-byte-offset-unproven]`: `read-write-image`
- `project.translate.metal-refused: MetalRefusal: Metal image store operation 'imageStore' requires float value for texture2d<float, access::read_write> images: u32(fin[i]) has type uint`: `integer-storage-image`
- `project.translate.metal-refused: MetalRefusal: Metal image store operation 'imageStore' requires float value for texture2d<float, access::read_write> images: vec4<u8>(v, v, v, v) has type uint`: `unorm-storage-image`
- `project.translate.unsupported-feature: UnsupportedMetalFeatureError: Metal codegen cannot reconstruct Metal union 'Bits': source ABI 'hip' cannot be reconstructed natively`: `union`

</details>
