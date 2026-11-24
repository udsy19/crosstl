# CrossTL translation matrix: HIP to SPIR-V

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native HIP probe whose feature SPIR-V has too straight to SPIR-V, and spirv-val checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 86.9 %: 251 supported, 28 refused, 10 wrong, 0 untested.

## Gaps

<details>
<summary>38 gaps: 28 refused, 10 wrong</summary>

Wrong, by cause:

- `line N: OpFunctionCall Argument <id> 'N[%N]'s type does not match Function <id> 'N[%N]'s parameter type.` (2): `texture-argument`, `texture-in-helper`
- `the translation loses BuiltIn.LocalInvocationIndex`: `local-invocation-index`
- `the translation loses BuiltIn.NumSubgroups`: `num-subgroups`
- `the translation loses BuiltIn.SubgroupId`: `subgroup-id`
- `the translation loses Decoration.Restrict`: `restrict-buffer`
- `the translation loses Decoration.Volatile`: `volatile-buffer`
- `the translation loses Dim.Buffer, Capability.SampledBuffer`: `texel-buffer`
- `the translation loses ImageFormat.R32ui`: `integer-storage-image`
- `the translation loses ImageFormat.Rgba8`: `unorm-storage-image`

Refused, by diagnostic:

- `project.translate.vulkan-builtin-unsupported: SPIRVBuiltinLoweringError: Cannot lower call to '<feature>' to SPIR-V: <feature> requires N-bit floating-point scalar or vector operand` (16): `acos`, `acosh`, `asin`, `asinh`, `atan`, `atanh`, `ceil`, `cosh`, `floor`, `rint`, `rsqrt`, `sinh`, `sqrt`, `tan`, `tanh`, `trunc`
- `project.translate.vulkan-builtin-unsupported: SPIRVBuiltinLoweringError: Cannot lower call to '<feature>' to SPIR-V: it is neither a declared function nor a built-in with a SPIR-V lowering` (3): `__isinff`, `__isnanf`, `ldexpf`
- `project.translate.hip-record-semantics-unsupported: HipRecordSemanticError: HIP record method call 'width' is unsupported for record 'Span' in call expression`: `struct-method`
- `project.translate.hip-surface-byte-offset-unproven: HipSurfaceByteOffsetError: surf2Dwrite cannot scale its x byte offset N: the element type is unknown, so the offset cannot be shown to be a multiple of the element size [project.translate.hip-surface-byte-offset-unproven]`: `read-write-image`
- `project.translate.rule-inexpressible: RuleInexpressibleError: __cgl_libm_cos on a N-bit floating-point operand has no helper for vulkan: the helper takes binary32 values only (target vulkan) [project.translate.rule-inexpressible]`: `cos`
- `project.translate.rule-inexpressible: RuleInexpressibleError: __cgl_libm_sin on a N-bit floating-point operand has no helper for vulkan: the helper takes binary32 values only (target vulkan) [project.translate.rule-inexpressible]`: `sin`
- `project.translate.rule-inexpressible: RuleInexpressibleError: __cgl_round_away on a N-bit floating-point operand has no helper for vulkan: the helper takes binary32 values only (target vulkan) [project.translate.rule-inexpressible]`: `round`
- `project.translate.vulkan-builtin-unsupported: SPIRVBuiltinLoweringError: Cannot lower call to 'atan2' to SPIR-V: atan2 requires matching N-bit floating-point scalar or vector operands`: `atan2`
- `project.translate.vulkan-builtin-unsupported: SPIRVBuiltinLoweringError: Cannot lower call to '__lane_id' to SPIR-V: it is neither a declared function nor a built-in with a SPIR-V lowering`: `subgroup-invocation-id`
- `project.translate.vulkan-lowering-unsupported: SpirvLoweringRefused: SPIR-V cannot lower N constructs: Unknown type ptr<i32>, using float as default; Unknown type ptr<f32>, using float as default; Unknown type ptr<f32>, using float as default; Unknown type ptr<i32>, using float as default; runtime-array aggregate values cannot be loaded as SPIR-V values; runtime-arra`: `buffer-in-helper`
- `project.translate.vulkan-lowering-unsupported: SpirvLoweringRefused: SPIR-V cannot lower N constructs: Unknown variable Low; Unknown variable High (target vulkan) [project.translate.vulkan-lowering-unsupported]`: `enum-constant`

</details>
