# CrossTL translation matrix: GLSL to HLSL

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native GLSL probe whose feature HLSL has too straight to HLSL, and dxc checked the result. Its compute probes also ran on a runtime. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 94.9 %: 408 supported, 12 refused, 10 wrong, 0 untested.

## Gaps

<details>
<summary>22 gaps: 12 refused, 10 wrong</summary>

Wrong, by cause:

- `use of undeclared identifier '<feature>'` (4): `layer`, `sample-mask-input`, `view-index`, `viewport-index`
- `Semantic must be defined for all parameters of an entry function or patch constant function` (2): `EmitVertex`, `EndPrimitive`
- `no matching function for call to 'WaveActiveBitAnd'`: `subgroupAnd`
- `no matching function for call to 'WaveActiveBitOr'`: `subgroupOr`
- `no matching function for call to 'WaveActiveBitXor'`: `subgroupXor`
- `no matching function for call to 'grow'`: `buffer-element-argument`

Refused, by diagnostic:

- `project.translate.directx-unsized-array-unsupported: UnsizedArrayUnsupportedError: unsized array 'position' is declared at module scope: only a storage buffer's last member or an array of resources may omit its element count (HLSL allows unsized arrays only for resources, MSL array bounds are constant expressions, and GLSL and WGSL allow runtime-sized arrays only as the last membe` (7): `tessellation-control`, `tessellation-domain-isolines`, `tessellation-domain-quads`, `tessellation-evaluation`, `tessellation-level-input`, `tessellation-patch-input`, `tessellation-patch-output`
- `project.translate.directx-lowering-unsupported: DirectXLoweringRefused: DirectX cannot lower N constructs: function: call to 'beginInvocationInterlockARB', a built-in function of another shading language that DirectX does not define and the program does not declare; function: call to 'endInvocationInterlockARB', a built-in function of another shading language that Direc` (2): `rasterizer-ordered-buffer`, `rasterizer-ordered-image`
- `project.translate.directx-lowering-unsupported: DirectXLoweringRefused: DirectX cannot lower N construct: function: call to 'interpolate_at_sample', a built-in function of another shading language that DirectX does not define and the program does not declare (target directx) [project.translate.directx-lowering-unsupported]`: `interpolateAtSample`
- `project.translate.directx-refused: DirectXRefusal: DirectX wave intrinsic 'WaveActiveAllEqual' requires bool3 result context, got bool`: `subgroupAllEqual`
- `project.translate.stage-interface-unsupported: StageInterfaceUnsupportedError: the fragment entry point '<probe>' takes parameters or returns a value as well as reading and writing stage-level interface variables; directx entry points receive inputs and return outputs as structures (target directx) [project.translate.stage-interface-unsupported]`: `stencil-export`

</details>
