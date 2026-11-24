# CrossTL translation matrix: Metal to Slang

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native Metal probe whose feature Slang has too straight to Slang, and slangc checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 86.0 %: 370 supported, 51 refused, 9 wrong, 0 untested.

## Gaps

<details>
<summary>60 gaps: 51 refused, 9 wrong</summary>

Wrong, by cause:

- `error[E31211]: derivative group linear thread count error: compute derivative group linear requires total thread dispatch count to be at a multiple of N` (2): `texture-1d`, `texture-1d-array`
- `error[E39999]: no overload for 'float4' applicable to arguments of type ()`: `zero-initializer`
- `error[E39999]: not enough arguments to call (got N, expected N)`: `sincos`
- `the translation loses Capability.RuntimeDescriptorArray`: `unsized-array-of-textures`
- `the translation loses Capability.ShaderNonUniform`: `array-of-textures-nonuniform-index`
- `the translation loses Decoration.Patch`: `tessellation-patch-input`
- `the translation loses ImageFormat.R32ui`: `integer-storage-image`
- `the translation loses ImageFormat.Rgba8`: `unorm-storage-image`

Refused, by diagnostic:

- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: call to <feature>: <feature> is a built-in function of another language, and Slang declares no function of that name (target slang) [project.translate.slang-lowering-unsupported]` (26): `dfdx`, `dfdy`, `extract_bits`, `fabs`, `fdim`, `fmax`, `fmax3`, `fmedian3`, `fmin`, `fmin3`, `insert_bits`, `max3`, `median3`, `min3`, `nextafter`, `pack_float_to_snorm2x16`, `pack_float_to_snorm4x8`, `pack_float_to_unorm2x16`, `pack_float_to_unorm4x8`, `rint`, `simd_is_first`, `simd_shuffle_rotate_down`, `unpack_snorm2x16_to_float`, `unpack_snorm4x8_to_float`, `unpack_unorm2x16_to_float`, `unpack_unorm4x8_to_float`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: call to atomicThreadFence: atomicThreadFence is a built-in function of another language, and Slang declares no function of that name (target slang) [project.translate.slang-lowering-unsupported]` (5): `atomic_exchange`, `atomic_fetch_add`, `atomic_fetch_and`, `atomic_fetch_or`, `atomic_fetch_xor`
- `project.translate.slang-metal-math-function-unsupported: MetalMathFunctionUnsupportedError: <feature> is exact at integers and half-integers, which slang has no function for, and CrossTL does not lower it with an exact range reduction yet (target slang) [project.translate.slang-metal-math-function-unsupported]` (3): `cospi`, `sinpi`, `tanpi`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: Slang has no system value for the built-in @<feature>; it would become a user varying, not the built-in (target slang) [project.translate.slang-lowering-unsupported]` (2): `num-subgroups`, `subgroup-id`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N constructs: pointer declaration: 'CrossGLMetalVectorIndex_vec2_add_assign_resource_r_index.data' points into device memory, and a bound Slang buffer has no device address (Slang User's Guide, "Pointers (limited)"); Slang structured buffer: buffer_load requires StructuredBuffer o` (2): `buffer-row-major-matrix`, `buffer-row-major-non-square`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: Slang image access: imageStore requires an image resource (target slang) [project.translate.slang-lowering-unsupported]`: `storage-texel-buffer`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: Slang sampled texture: texelFetch requires a non-shadow texel-fetchable sampled texture resource (target slang) [project.translate.slang-lowering-unsupported]`: `texel-buffer`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: call to atomicCompareExchangeWeak: atomicCompareExchangeWeak is a built-in function of another language, and Slang declares no function of that name (target slang) [project.translate.slang-lowering-unsupported]`: `atomic_compare_exchange_weak_explicit`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: call to simd_is_helper_thread: simd_is_helper_thread is a built-in function of another language, and Slang declares no function of that name (target slang) [project.translate.slang-lowering-unsupported]`: `helper-invocation`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: pointer declaration: 'probe.p' points into device memory, and a bound Slang buffer has no device address (Slang User's Guide, "Pointers (limited)") (target slang) [project.translate.slang-lowering-unsupported]`: `pointer-local`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: resource parameter '<probe>' is coherent: slangc allows no coherent or volatile parameter (E31201), so its accesses would lose that behaviour (target slang) [project.translate.slang-lowering-unsupported]`: `coherent-buffer`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N constructs: call to atomicThreadFence: atomicThreadFence is a built-in function of another language, and Slang declares no function of that name; call to atomicCompareExchangeWeak: atomicCompareExchangeWeak is a built-in function of another language, and Slang declares no functi`: `atomic_compare_exchange_weak`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N constructs: pointer declaration: 'CrossGLMetalVectorIndex_vec2_add_assign_resource_index.data' points into device memory, and a bound Slang buffer has no device address (Slang User's Guide, "Pointers (limited)"); Slang structured buffer: buffer_load requires StructuredBuffer or`: `matrix-buffer`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N constructs: pointer declaration: 'CrossGLMetalVectorIndex_vec2_add_assign_resource_r_index_index.data' points into device memory, and a bound Slang buffer has no device address (Slang User's Guide, "Pointers (limited)"); Slang structured buffer: buffer_load requires StructuredBu`: `buffer-row-major-array`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N constructs: pointer declaration: 'fetch.iin' points into device memory, and a bound Slang buffer has no device address (Slang User's Guide, "Pointers (limited)"); pointer declaration: 'put.outp' points into device memory, and a bound Slang buffer has no device address (Slang Use`: `buffer-in-helper`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N constructs: pointer declaration: 'probe.p' points into device memory, and a bound Slang buffer has no device address (Slang User's Guide, "Pointers (limited)"); pointer declaration: 'probe.q' points into device memory, and a bound Slang buffer has no device address (Slang User's`: `pointer-arithmetic`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N constructs: pointer declaration: 'stash.tile' points into threadgroup memory, and Slang's & of groupshared memory gives a device pointer (Slang User's Guide, "Pointers (limited)"); pointer declaration: 'exchange.tile' points into threadgroup memory, and Slang's & of groupshared`: `shared-memory-in-helper`
- `project.translate.slang-refused: SlangRefusal: Unsupported gl_BaseVertex stage parameter semantic for Slang codegen; expected int type`: `base-vertex`

</details>
