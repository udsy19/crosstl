# CrossTL translation matrix: CUDA to SPIR-V

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native CUDA probe whose feature SPIR-V has too straight to SPIR-V, and spirv-val checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 85.8 %: 247 supported, 31 refused, 10 wrong, 0 untested.

## Gaps

<details>
<summary>41 gaps: 31 refused, 10 wrong</summary>

Wrong, by cause:

- `the translation loses BuiltIn.LocalInvocationIndex`: `local-invocation-index`
- `the translation loses BuiltIn.NumSubgroups`: `num-subgroups`
- `the translation loses BuiltIn.SubgroupId`: `subgroup-id`
- `the translation loses BuiltIn.SubgroupLocalInvocationId`: `subgroup-invocation-id`
- `the translation loses BuiltIn.SubgroupSize`: `subgroup-size`
- `the translation loses Decoration.Restrict`: `restrict-buffer`
- `the translation loses Decoration.Volatile`: `volatile-buffer`
- `the translation loses Dim.Buffer, Capability.SampledBuffer`: `texel-buffer`
- `the translation loses ImageFormat.R32ui`: `integer-storage-image`
- `the translation loses ImageFormat.Rgba8`: `unorm-storage-image`

Refused, by diagnostic:

- `project.translate.vulkan-builtin-unsupported: SPIRVBuiltinLoweringError: Cannot lower call to '<feature>' to SPIR-V: <feature> requires N-bit floating-point scalar or vector operand` (16): `acos`, `acosh`, `asin`, `asinh`, `atan`, `atanh`, `ceil`, `cosh`, `floor`, `rint`, `rsqrt`, `sinh`, `sqrt`, `tan`, `tanh`, `trunc`
- `project.translate.vulkan-builtin-unsupported: SPIRVBuiltinLoweringError: Cannot lower call to '<feature>' to SPIR-V: it is neither a declared function nor a built-in with a SPIR-V lowering` (6): `__isinff`, `__isnanf`, `acoshf`, `asinhf`, `atanhf`, `ldexpf`
- `project.translate.vulkan-lowering-unsupported: SpirvLoweringRefused: SPIR-V cannot lower N construct: Unknown type cudaTextureObject_t, using float as default (target vulkan) [project.translate.vulkan-lowering-unsupported]` (2): `texture-argument`, `texture-in-helper`
- `project.translate.rule-inexpressible: RuleInexpressibleError: __cgl_libm_cos on a N-bit floating-point operand has no helper for vulkan: the helper takes binary32 values only (target vulkan) [project.translate.rule-inexpressible]`: `cos`
- `project.translate.rule-inexpressible: RuleInexpressibleError: __cgl_libm_sin on a N-bit floating-point operand has no helper for vulkan: the helper takes binary32 values only (target vulkan) [project.translate.rule-inexpressible]`: `sin`
- `project.translate.rule-inexpressible: RuleInexpressibleError: __cgl_round_away on a N-bit floating-point operand has no helper for vulkan: the helper takes binary32 values only (target vulkan) [project.translate.rule-inexpressible]`: `round`
- `project.translate.undeclared-function: UndeclaredFunctionError: function 'surf2Dread' is not declared: it is neither a CrossGL built-in function nor a function, structure method, type or callable value of the program (target vulkan) [project.translate.undeclared-function]`: `read-write-image`
- `project.translate.vulkan-builtin-unsupported: SPIRVBuiltinLoweringError: Cannot lower call to 'atan2' to SPIR-V: atan2 requires matching N-bit floating-point scalar or vector operands`: `atan2`
- `project.translate.vulkan-lowering-unsupported: SpirvLoweringRefused: SPIR-V cannot lower N constructs: Unknown type ptr<i32>, using float as default; Unknown type ptr<f32>, using float as default; Unknown type ptr<f32>, using float as default; Unknown type ptr<i32>, using float as default; runtime-array aggregate values cannot be loaded as SPIR-V values; runtime-arra`: `buffer-in-helper`
- `project.translate.vulkan-lowering-unsupported: SpirvLoweringRefused: SPIR-V cannot lower N constructs: Unknown variable Low; Unknown variable High (target vulkan) [project.translate.vulkan-lowering-unsupported]`: `enum-constant`

</details>
