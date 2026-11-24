# CrossTL translation matrix: Metal to SPIR-V

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native Metal probe whose feature SPIR-V has too straight to SPIR-V, and spirv-val checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 91.3 %: 399 supported, 29 refused, 9 wrong, 0 untested.

## Gaps

<details>
<summary>38 gaps: 29 refused, 9 wrong</summary>

Wrong, by cause:

- `the translation loses ExecutionMode.PixelInterlockOrderedEXT, Capability.FragmentShaderPixelInterlockEXT, OpBeginInvocationInterlockEXT` (2): `rasterizer-ordered-buffer`, `rasterizer-ordered-image`
- `the translation loses BuiltIn.ViewIndex, Capability.MultiView`: `view-index`
- `the translation loses Capability.ShaderNonUniform`: `array-of-textures-nonuniform-index`
- `the translation loses Decoration.Centroid`: `centroid-interpolation`
- `the translation loses Decoration.NoPerspective`: `noperspective-interpolation`
- `the translation loses Decoration.Sample, Capability.SampleRateShading`: `sample-interpolation`
- `the translation loses ImageFormat.R32ui`: `integer-storage-image`
- `the translation loses ImageFormat.Rgba8`: `unorm-storage-image`

Refused, by diagnostic:

- `project.translate.vulkan-atomic-fence-unsupported: SPIRVAtomicFenceLoweringError: Cannot lower CrossGL atomicThreadFence to Vulkan SPIR-V without changing its semantics (flags=mem_device | mem_threadgroup | mem_threadgroup_imageblock | mem_texture | mem_object_data, order=memory_order_seq_cst, scope=thread_scope_device): atomic fence lowering deferred` (10): `atomic_compare_exchange_weak`, `atomic_exchange`, `atomic_fetch_add`, `atomic_fetch_and`, `atomic_fetch_max`, `atomic_fetch_min`, `atomic_fetch_or`, `atomic_fetch_xor`, `atomic_max`, `atomic_min`
- `project.translate.vulkan-builtin-unsupported: SPIRVBuiltinLoweringError: Cannot lower call to '<feature>' to SPIR-V: it is neither a declared function nor a built-in with a SPIR-V lowering` (7): `dfdx`, `dfdy`, `max3`, `min3`, `rint`, `simd_is_first`, `simd_shuffle_rotate_down`
- `project.translate.vulkan-interface-location-conflict: InterfaceLocationConflictError: Duplicate SPIR-V input location N for 'coord': another input variable of the entry point already takes it, and Vulkan requires distinct locations within one interface (target vulkan) [project.translate.vulkan-interface-location-conflict]` (3): `tessellation-domain-quads`, `tessellation-evaluation`, `tessellation-patch-input`
- `project.translate.unsupported-feature: UnsupportedSPIRVFeatureError: SPIR-V requires a concrete fixed-array extent for local variable t; could not resolve 'N'`: `constant-array-size`
- `project.translate.vulkan-builtin-unsupported: SPIRVBuiltinLoweringError: Cannot lower call to 'atomicCompareExchangeWeak' to SPIR-V: it is neither a declared function nor a built-in with a SPIR-V lowering`: `atomic_compare_exchange_weak_explicit`
- `project.translate.vulkan-builtin-unsupported: SPIRVBuiltinLoweringError: Cannot lower call to 'simd_is_helper_thread' to SPIR-V: it is neither a declared function nor a built-in with a SPIR-V lowering`: `helper-invocation`
- `project.translate.vulkan-lowering-unsupported: SpirvLoweringRefused: SPIR-V cannot lower N construct: Constructor mat2 expected N components but got N (target vulkan) [project.translate.vulkan-lowering-unsupported]`: `buffer-row-major-matrix`
- `project.translate.vulkan-lowering-unsupported: SpirvLoweringRefused: SPIR-V cannot lower N construct: Constructor mat3x2 expected N components but got N (target vulkan) [project.translate.vulkan-lowering-unsupported]`: `buffer-row-major-non-square`
- `project.translate.vulkan-lowering-unsupported: SpirvLoweringRefused: SPIR-V cannot lower N construct: atomicMax currently supports only int or uint buffer members (target vulkan) [project.translate.vulkan-lowering-unsupported]`: `atomic_max_explicit`
- `project.translate.vulkan-lowering-unsupported: SpirvLoweringRefused: SPIR-V cannot lower N construct: atomicMin currently supports only int or uint buffer members (target vulkan) [project.translate.vulkan-lowering-unsupported]`: `atomic_min_explicit`
- `project.translate.vulkan-lowering-unsupported: SpirvLoweringRefused: SPIR-V cannot lower N constructs: Constructor mat2 expected N components but got N; Constructor mat2 expected N components but got N (target vulkan) [project.translate.vulkan-lowering-unsupported]`: `buffer-row-major-array`
- `project.translate.vulkan-lowering-unsupported: SpirvLoweringRefused: SPIR-V cannot lower N constructs: Could not find member tex in Slot_std430_9; Failed to evaluate argument for textureLod; textureLod requires a sampled image operand (target vulkan) [project.translate.vulkan-lowering-unsupported]`: `unsized-array-of-textures`

</details>
