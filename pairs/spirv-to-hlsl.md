# CrossTL translation matrix: SPIR-V to HLSL

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native SPIR-V probe whose feature HLSL has too straight to HLSL, and dxc checked the result. Its compute probes also ran on a runtime. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 93.3 %: 404 supported, 19 refused, 10 wrong, 0 untested.

## Gaps

<details>
<summary>29 gaps: 19 refused, 10 wrong</summary>

Wrong, by cause:

- `on vulkan-lavapipe as SPIR-V from dxc, the translation computes different results from the native probe` (4): `Atan2`, `buffer-row-major-array`, `buffer-row-major-matrix`, `buffer-row-major-non-square`
- `validation errors` (2): `layer`, `viewport-index`
- `Semantic must be defined for all parameters of an entry function or patch constant function` (2): `OpEmitVertex`, `OpEndPrimitive`
- `cannot implicitly convert from 'float3' to 'float [N]'`: `array-return`
- `use of undeclared identifier 'gl_GlobalInvocationID'`: `invocation-id-in-helper`

Refused, by diagnostic:

- `project.translate.directx-stage-attributes-missing: DirectXStageAttributesMissingError: DirectX tessellation_evaluation stage requires HLSL attribute(s): domain; HLSL fixes them on the entry point, which carries them as @-attributes, and a GLSL or SPIR-V tessellation stage holds only part of them (target directx) [project.translate.directx-stage-attributes-missing]` (5): `tessellation-domain-isolines`, `tessellation-domain-quads`, `tessellation-evaluation`, `tessellation-level-input`, `tessellation-patch-input`
- `project.translate.directx-refused: DirectXRefusal: DirectX tessellation_control stage cannot call barrier; 'barrier' lowers to GroupMemoryBarrierWithGroupSync, which is only valid in compute, mesh, or amplification/task stages` (4): `tessellation-control-point-mode`, `tessellation-control-spacing-fractional-even`, `tessellation-control-spacing-fractional-odd`, `tessellation-control-winding-ccw`
- `project.translate.directx-unsized-array-unsupported: UnsizedArrayUnsupportedError: unsized array 'B0.fin' is a struct member: only a storage buffer's last member or an array of resources may omit its element count (HLSL allows unsized arrays only for resources, MSL array bounds are constant expressions, and GLSL and WGSL allow runtime-sized arrays only as the last member of a stor` (3): `OpControlBarrier`, `OpGroupNonUniformElect`, `OpImageQuerySize`
- `project.translate.directx-lowering-unsupported: DirectXLoweringRefused: DirectX cannot lower N constructs: function: call to 'beginInvocationInterlockARB', a built-in function of another shading language that DirectX does not define and the program does not declare; function: call to 'endInvocationInterlockARB', a built-in function of another shading language that Direc` (2): `rasterizer-ordered-buffer`, `rasterizer-ordered-image`
- `project.translate.directx-stage-attributes-missing: DirectXStageAttributesMissingError: DirectX tessellation_control stage requires HLSL attribute(s): domain, outputcontrolpoints, outputtopology, partitioning, patchconstantfunc; HLSL fixes them on the entry point, which carries them as @-attributes, and a GLSL or SPIR-V tessellation stage holds only part of them (target directx) [proje` (2): `tessellation-control`, `tessellation-patch-output`
- `project.translate.directx-contextual-conversion-unrepresentable: DirectXContextualConversionError: DirectX NonUniformResourceIndex index argument must be scalar int or uint, got Texture2D`: `array-of-textures-nonuniform-index`
- `project.translate.directx-refused: DirectXRefusal: DirectX fragment stage gl_SampleMask parameter 'cgl_SampleMaskIn' cannot use output-only sample mask semantic`: `sample-mask-input`
- `project.translate.directx-refused: DirectXRefusal: DirectX wave intrinsic 'WaveActiveAllEqual' requires bool3 result context, got bool`: `OpGroupNonUniformAllEqual`

</details>
