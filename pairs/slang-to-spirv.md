# CrossTL translation matrix: Slang to SPIR-V

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native Slang probe whose feature SPIR-V has too straight to SPIR-V, and spirv-val checked the result. Its compute probes also ran on a runtime. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 84.4 %: 411 supported, 41 refused, 35 wrong, 0 untested.

## Gaps

<details>
<summary>76 gaps: 41 refused, 35 wrong</summary>

Wrong, by cause:

- `on vulkan-lavapipe as SPIR-V from slangc, the translation binds other resources than the native probe` (25): `uniform-array`, `uniform-bool`, `uniform-bool-vector`, `uniform-buffer`, `uniform-cbuffer-vector`, `uniform-in-helper`, `uniform-integer`, `uniform-integer-vector`, `uniform-matrix`, `uniform-matrix2`, `uniform-matrix3`, `uniform-members`, `uniform-non-square-matrix`, `uniform-row-major-array`, `uniform-row-major-matrix`, `uniform-row-major-non-square`, `uniform-std140-array`, `uniform-std140-vector`, `uniform-struct`, `uniform-struct-array`, `uniform-struct-copy`, `uniform-unsigned`, `uniform-vector`, `uniform-vector-array`, `uniform-vector-packing`
- `line N: Expected Constituent type to be equal to the corresponding member type of Result Type struct` (3): `tessellation-domain-isolines`, `tessellation-evaluation`, `tessellation-level-input`
- `on vulkan-lavapipe as SPIR-V from slangc, the translation computes different results from the native probe`: `QuadReadLaneAt`
- `the translation loses Decoration.Centroid`: `centroid-interpolation`
- `the translation loses Decoration.Flat`: `flat-interpolation`
- `the translation loses Decoration.NoPerspective`: `noperspective-interpolation`
- `the translation loses Decoration.Sample, Capability.SampleRateShading`: `sample-interpolation`
- `the translation loses ImageFormat.R32ui`: `integer-storage-image`
- `the translation loses ImageFormat.Rgba8`: `unorm-storage-image`

Refused, by diagnostic:

- `project.translate.undeclared-function: UndeclaredFunctionError: function '<feature>' is not declared: it is neither a CrossGL built-in function nor a function, structure method, type or callable value of the program (target vulkan) [project.translate.undeclared-function]` (11): `EvaluateAttributeAtCentroid`, `unpackHalf2x16ToFloat`, `unpackHalf2x16ToHalf`, `unpackSnorm2x16ToFloat`, `unpackSnorm2x16ToHalf`, `unpackSnorm4x8ToFloat`, `unpackSnorm4x8ToHalf`, `unpackUnorm2x16ToFloat`, `unpackUnorm2x16ToHalf`, `unpackUnorm4x8ToFloat`, `unpackUnorm4x8ToHalf`
- `project.translate.vulkan-geometry-stream-unsupported: GeometryStreamUnsupportedError: input vertex member 'position' is an array or structure; vulkan geometry shaders write vertices through stage outputs and EmitVertex() (target vulkan) [project.translate.vulkan-geometry-stream-unsupported]` (8): `geometry-input-lines`, `geometry-input-lines-adjacency`, `geometry-input-triangles`, `geometry-input-triangles-adjacency`, `geometry-invocations`, `geometry-output-line-strip`, `geometry-output-triangle-strip`, `geometry-streams`
- `project.translate.vulkan-builtin-unsupported: SPIRVBuiltinLoweringError: Cannot lower call to '<feature>' to SPIR-V: it is neither a declared function nor a built-in with a SPIR-V lowering` (5): `EvaluateAttributeAtSample`, `asdouble`, `max3`, `min3`, `rint`
- `project.translate.slang-import-unsupported: SlangImportRefused: CrossGL cannot represent N Slang construct: Slang <feature> has no CrossGL atomic operation (target cgl) [project.translate.slang-import-unsupported]` (2): `InterlockedCompareExchangeFloatBitwise`, `InterlockedCompareStoreFloatBitwise`
- `project.translate.builtin-value-unsupported: BuiltinValueUnsupportedError: @SV_PointCoord is not a Direct3D system value; the HLSL system values are SV_Barycentrics, SV_ClipDistance, SV_Coverage, SV_CullDistance, SV_CullPrimitive, SV_Depth, SV_DepthGreaterEqual, SV_DepthLessEqual, SV_DispatchGrid, SV_DispatchThreadID, SV_DomainLocation, SV_GSInstanceID, SV_GroupID, SV_Grou`: `point-coordinate`
- `project.translate.crossgl-function-body-parse-failed: CrossGLFunctionBodyParseError: CrossGL could not parse the body of function '<probe>' at IDENTIFIER 'b': Expected SEMICOLON, got IDENTIFIER 'b'`: `multi-variable-loop`
- `project.translate.crossgl-syntax-error: CrossGLSyntaxError: Expected a structure name after 'struct', got MATCH 'match'`: `reserved-type-name`
- `project.translate.slang-import-unsupported: SlangImportRefused: CrossGL cannot represent N Slang construct: numthreads x dimension size depends on specialization constant size; CrossGL fixes the workgroup size at translation time (target cgl) [project.translate.slang-import-unsupported]`: `specialization-workgroup-size`
- `project.translate.slang-syntax-error: SlangSyntaxError: Expected SEMICOLON, got LBRACKET`: `array-return`
- `project.translate.undeclared-type: UndeclaredTypeError: type 'T' is not declared: it is neither a CrossGL built-in type nor a structure, enumeration, type alias or generic parameter of the program (target vulkan) [project.translate.undeclared-type]`: `generic-function`
- `project.translate.unsupported-feature: UnsupportedSPIRVFeatureError: SPIR-V requires a concrete fixed-array extent for local variable t; could not resolve 'N'`: `constant-array-size`
- `project.translate.vulkan-geometry-stream-unsupported: GeometryStreamUnsupportedError: input vertex member 'position' is an array or structure; vulkan geometry shaders write vertices through stage outputs and EmitVertex() (target vulkan) [project.translate.vulkan-geometry-stream-unsupported]`: `geometry`
- `project.translate.vulkan-builtin-unsupported: SPIRVBuiltinLoweringError: Cannot lower call to '<expression>' to SPIR-V: Vulkan SPIR-V has no function pointers, so a call through a function table or other callee expression cannot be lowered`: `texel-buffer`
- `project.translate.vulkan-builtin-unsupported: SPIRVBuiltinLoweringError: Cannot lower call to 'IsHelperLane' to SPIR-V: it is neither a declared function nor a built-in with a SPIR-V lowering`: `helper-invocation`
- `project.translate.vulkan-interface-location-conflict: InterfaceLocationConflictError: Duplicate SPIR-V input location N for 'extra': another input variable of the entry point already takes it, and Vulkan requires distinct locations within one interface (target vulkan) [project.translate.vulkan-interface-location-conflict]`: `tessellation-patch-input`
- `project.translate.vulkan-lowering-unsupported: SpirvLoweringRefused: SPIR-V cannot lower N construct: Unknown type RWBuffer<float4>, using float as default (target vulkan) [project.translate.vulkan-lowering-unsupported]`: `storage-texel-buffer`
- `project.translate.vulkan-lowering-unsupported: SpirvLoweringRefused: SPIR-V cannot lower N construct: Unknown type RasterizerOrderedStructuredBuffer<float4>, using float as default (target vulkan) [project.translate.vulkan-lowering-unsupported]`: `rasterizer-ordered-buffer`
- `project.translate.vulkan-lowering-unsupported: SpirvLoweringRefused: SPIR-V cannot lower N constructs: Unknown type RasterizerOrderedTexture2D<float4>, using float as default; OpAccessChain index could not be converted to an integer (target vulkan) [project.translate.vulkan-lowering-unsupported]`: `rasterizer-ordered-image`
- `project.translate.workgroup-uniform-load-unsupported: WorkgroupUniformLoadError: workgroupUniformLoad: '<probe>' is not a shared variable declared at program or stage scope for vulkan (target vulkan) [project.translate.workgroup-uniform-load-unsupported]`: `workgroupUniformLoad`

</details>
