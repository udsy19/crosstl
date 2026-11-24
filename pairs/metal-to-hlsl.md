# CrossTL translation matrix: Metal to HLSL

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native Metal probe whose feature HLSL has too straight to HLSL, and dxc checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 92.0 %: 358 supported, 12 refused, 19 wrong, 0 untested.

## Gaps

<details>
<summary>31 gaps: 12 refused, 19 wrong</summary>

Wrong, by cause:

- `Semantic must be defined for all outputs of an entry function or patch constant function` (3): `tessellation-domain-quads`, `tessellation-evaluation`, `tessellation-patch-input`
- `no member named 'Store' in 'RWStructuredBuffer<Rows>'` (3): `buffer-row-major-array`, `buffer-row-major-matrix`, `buffer-row-major-non-square`
- `no matching function for call to 'WaveActiveBitAnd'`: `simd_and`
- `no matching function for call to 'WaveActiveBitOr'`: `simd_or`
- `no matching function for call to 'WaveActiveBitXor'`: `simd_xor`
- `no member named 'Store' in 'RWStructuredBuffer<matrix<float, 2, 2> >'`: `matrix-buffer`
- `object 'Texture2D' is not allowed in builtin template parameters`: `unsized-array-of-textures`
- `use of undeclared identifier 'sincos'`: `sincos`
- `the translation loses BuiltIn.ViewIndex, Capability.MultiView`: `view-index`
- `the translation loses Capability.ShaderNonUniform`: `array-of-textures-nonuniform-index`
- `the translation loses Decoration.Centroid`: `centroid-interpolation`
- `the translation loses Decoration.NoPerspective`: `noperspective-interpolation`
- `the translation loses Decoration.Sample, Capability.SampleRateShading`: `sample-interpolation`
- `the translation loses ImageFormat.R32ui`: `integer-storage-image`
- `the translation loses ImageFormat.Rgba8`: `unorm-storage-image`

Refused, by diagnostic:

- `project.translate.directx-atomic-fence-unsupported: DirectXAtomicFenceLoweringError: Cannot lower CrossGL atomicThreadFence to HLSL without changing its semantics (flags=mem_device | mem_threadgroup | mem_threadgroup_imageblock | mem_texture | mem_object_data, order=memory_order_seq_cst, scope=thread_scope_device): unsupported thread scope` (6): `atomic_compare_exchange_weak`, `atomic_exchange`, `atomic_fetch_add`, `atomic_fetch_and`, `atomic_fetch_or`, `atomic_fetch_xor`
- `project.translate.directx-lowering-unsupported: DirectXLoweringRefused: DirectX cannot lower N construct: function: call to '<feature>', a built-in function of another shading language that DirectX does not define and the program does not declare (target directx) [project.translate.directx-lowering-unsupported]` (5): `dfdx`, `dfdy`, `max3`, `min3`, `simd_is_first`
- `project.translate.directx-lowering-unsupported: DirectXLoweringRefused: DirectX cannot lower N construct: function: call to 'simd_is_helper_thread', a built-in function of another shading language that DirectX does not define and the program does not declare (target directx) [project.translate.directx-lowering-unsupported]`: `helper-invocation`

</details>
