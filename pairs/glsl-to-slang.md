# CrossTL translation matrix: GLSL to Slang

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native GLSL probe whose feature Slang has too straight to Slang, and slangc checked the result. Its compute probes also ran on a runtime. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 92.7 %: 454 supported, 31 refused, 5 wrong, 0 untested.

## Gaps

<details>
<summary>36 gaps: 31 refused, 5 wrong</summary>

Wrong, by cause:

- `error[E30015]: undefined identifier '<feature>'` (3): `barycentric-coordinate`, `shading-rate`, `view-index`
- `error[E30013]: invalid subscript expression: no subscript declarations found for type 'uint'`: `sample-mask-input`
- `error[E30047]: argument must be l-value: argument passed to parameter 'N' must be l-value`: `buffer-element-argument`

Refused, by diagnostic:

- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: call to <feature>: <feature> is a built-in function of another language, and Slang declares no function of that name (target slang) [project.translate.slang-lowering-unsupported]` (13): `bitfieldExtract`, `bitfieldInsert`, `packDouble2x32`, `packHalf2x16`, `packSnorm2x16`, `packSnorm4x8`, `packUnorm2x16`, `packUnorm4x8`, `unpackHalf2x16`, `unpackSnorm2x16`, `unpackSnorm4x8`, `unpackUnorm2x16`, `unpackUnorm4x8`
- `project.translate.slang-unsized-array-unsupported: UnsizedArrayUnsupportedError: unsized array 'position' is not a resource array: only a storage buffer's last member or an array of resources may omit its element count (HLSL allows unsized arrays only for resources, MSL array bounds are constant expressions, and GLSL and WGSL allow runtime-sized arrays only as the last member of` (7): `tessellation-control`, `tessellation-domain-isolines`, `tessellation-domain-quads`, `tessellation-evaluation`, `tessellation-level-input`, `tessellation-patch-input`, `tessellation-patch-output`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N constructs: call to beginInvocationInterlockARB: beginInvocationInterlockARB is a built-in function of another language, and Slang declares no function of that name; call to endInvocationInterlockARB: endInvocationInterlockARB is a built-in function of another language, and Slan` (2): `rasterizer-ordered-buffer`, `rasterizer-ordered-image`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: Slang image access: imageStore requires an image resource (target slang) [project.translate.slang-lowering-unsupported]`: `storage-texel-buffer`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: Slang sampled texture: texelFetch requires a non-shadow texel-fetchable sampled texture resource (target slang) [project.translate.slang-lowering-unsupported]`: `texel-buffer`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: call to fwidth_coarse: fwidth_coarse is a built-in function of another language, and Slang declares no function of that name (target slang) [project.translate.slang-lowering-unsupported]`: `fwidthCoarse`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: call to fwidth_fine: fwidth_fine is a built-in function of another language, and Slang declares no function of that name (target slang) [project.translate.slang-lowering-unsupported]`: `fwidthFine`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: call to interpolate_at_centroid: interpolate_at_centroid is a built-in function of another language, and Slang declares no function of that name (target slang) [project.translate.slang-lowering-unsupported]`: `interpolateAtCentroid`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: call to interpolate_at_sample: interpolate_at_sample is a built-in function of another language, and Slang declares no function of that name (target slang) [project.translate.slang-lowering-unsupported]`: `interpolateAtSample`
- `project.translate.slang-refused: SlangRefusal: Slang geometry stage must declare at most one stream output parameter`: `geometry-streams`
- `project.translate.slang-shader-record-buffer-unsupported: ShaderRecordBufferUnsupportedError: shader record buffer 'record' (GL_EXT_ray_tracing shaderRecordEXT) cannot be read on slang: the target has no shader binding table (target slang) [project.translate.slang-shader-record-buffer-unsupported]`: `ray-shader-record`
- `project.translate.stage-interface-unsupported: StageInterfaceUnsupportedError: the fragment entry point '<probe>' takes parameters or returns a value as well as reading and writing stage-level interface variables; slang entry points receive inputs and return outputs as structures (target slang) [project.translate.stage-interface-unsupported]`: `stencil-export`

</details>
