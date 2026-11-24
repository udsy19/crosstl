# CrossTL translation matrix: HLSL to SPIR-V

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native HLSL probe whose feature SPIR-V has too straight to SPIR-V, and spirv-val checked the result. Its compute probes also ran on a runtime. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 93.8 %: 423 supported, 20 refused, 8 wrong, 0 untested.

## Gaps

<details>
<summary>28 gaps: 20 refused, 8 wrong</summary>

Wrong, by cause:

- `line N: Expected Constituent type to be equal to the corresponding member type of Result Type struct` (3): `tessellation-domain-isolines`, `tessellation-evaluation`, `tessellation-level-input`
- `on vulkan-lavapipe as SPIR-V from dxc, the translation computes different results from the native probe`: `cross`
- `the translation calls no NMax and tests no operand for NaN`: `max`
- `the translation calls no NMin and tests no operand for NaN`: `min`
- `the translation loses ImageFormat.R32ui`: `integer-storage-image`
- `the translation loses ImageFormat.Rgba8`: `unorm-storage-image`

Refused, by diagnostic:

- `project.translate.vulkan-geometry-stream-unsupported: GeometryStreamUnsupportedError: input vertex member 'position' is an array or structure; vulkan geometry shaders write vertices through stage outputs and EmitVertex() (target vulkan) [project.translate.vulkan-geometry-stream-unsupported]` (10): `Stream.Append`, `Stream.RestartStrip`, `geometry-input-lines`, `geometry-input-lines-adjacency`, `geometry-input-triangles`, `geometry-input-triangles-adjacency`, `geometry-invocations`, `geometry-output-line-strip`, `geometry-output-triangle-strip`, `geometry-streams`
- `project.translate.vulkan-builtin-unsupported: SPIRVBuiltinLoweringError: Cannot lower call to '<feature>' to SPIR-V: it is neither a declared function nor a built-in with a SPIR-V lowering` (6): `InterlockedCompareExchangeFloatBitwise`, `InterlockedCompareStoreFloatBitwise`, `f16tof32`, `f32tof16`, `pack_clamp_s8`, `pack_clamp_u8`
- `project.translate.unsupported-feature: UnsupportedSPIRVFeatureError: SPIR-V requires a concrete fixed-array extent for local variable t; could not resolve 'N'`: `constant-array-size`
- `project.translate.vulkan-geometry-stream-unsupported: GeometryStreamUnsupportedError: input vertex member 'position' is an array or structure; vulkan geometry shaders write vertices through stage outputs and EmitVertex() (target vulkan) [project.translate.vulkan-geometry-stream-unsupported]`: `geometry`
- `project.translate.vulkan-interface-location-conflict: InterfaceLocationConflictError: Duplicate SPIR-V input location N for 'extra': another input variable of the entry point already takes it, and Vulkan requires distinct locations within one interface (target vulkan) [project.translate.vulkan-interface-location-conflict]`: `tessellation-patch-input`
- `project.translate.vulkan-lowering-unsupported: SpirvLoweringRefused: SPIR-V cannot lower N construct: atomicExchange currently supports only int or uint buffer members (target vulkan) [project.translate.vulkan-lowering-unsupported]`: `InterlockedExchange`

</details>
