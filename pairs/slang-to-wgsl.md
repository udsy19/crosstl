# CrossTL translation matrix: Slang to WGSL

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native Slang probe whose feature WGSL has too straight to WGSL, and naga checked the result. Its compute probes also ran on a runtime. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 81.7 %: 309 supported, 34 refused, 35 wrong, 1 untested.

## Gaps

<details>
<summary>69 gaps: 34 refused, 35 wrong</summary>

Wrong, by cause:

- `on vulkan-lavapipe as SPIR-V from slangc and naga, the translation binds other resources than the native probe` (25): `uniform-array`, `uniform-bool`, `uniform-bool-vector`, `uniform-buffer`, `uniform-cbuffer-vector`, `uniform-in-helper`, `uniform-integer`, `uniform-integer-vector`, `uniform-matrix`, `uniform-matrix2`, `uniform-matrix3`, `uniform-members`, `uniform-non-square-matrix`, `uniform-row-major-array`, `uniform-row-major-matrix`, `uniform-row-major-non-square`, `uniform-std140-array`, `uniform-std140-vector`, `uniform-struct`, `uniform-struct-array`, `uniform-struct-copy`, `uniform-unsigned`, `uniform-vector`, `uniform-vector-array`, `uniform-vector-packing`
- `the type of '<probe>' is expected to be 'vec2<u32>', but got 'vec2<i32>'` (3): `countbits`, `firstbithigh`, `firstbitlow`
- `incorrect type passed to workgroupUniformLoad`: `workgroupUniformLoad`
- `the type of '<probe>' is expected to be 'vec2<i32>', but got 'vec2<f32>'`: `sign`
- `on vulkan-lavapipe as SPIR-V from slangc and naga, the translation computes different results from the native probe`: `QuadReadLaneAt`
- `the translation loses Decoration.Centroid`: `centroid-interpolation`
- `the translation loses Decoration.Flat`: `flat-interpolation`
- `the translation loses Decoration.NoPerspective`: `noperspective-interpolation`
- `the translation loses Decoration.Sample, Capability.SampleRateShading`: `sample-interpolation`

Refused, by diagnostic:

- `project.translate.undeclared-function: UndeclaredFunctionError: function '<feature>' is not declared: it is neither a CrossGL built-in function nor a function, structure method, type or callable value of the program (target wgsl) [project.translate.undeclared-function]` (14): `unpackHalf2x16ToFloat`, `unpackHalf2x16ToHalf`, `unpackInt4x8ToInt16`, `unpackInt4x8ToInt32`, `unpackSnorm2x16ToFloat`, `unpackSnorm2x16ToHalf`, `unpackSnorm4x8ToFloat`, `unpackSnorm4x8ToHalf`, `unpackUint4x8ToUint16`, `unpackUint4x8ToUint32`, `unpackUnorm2x16ToFloat`, `unpackUnorm2x16ToHalf`, `unpackUnorm4x8ToFloat`, `unpackUnorm4x8ToHalf`
- `project.translate.wgsl-refused: WGSLRefusal: WGSL target requires storage image resource img to declare a representable image format such as layout(rgba8) or @rgba8` (7): `integer-storage-image`, `read-write-image`, `storage-image`, `storage-image-1d`, `storage-image-3d`, `storage-image-array`, `unorm-storage-image`
- `project.translate.wgsl-foreign-builtin-call: WGSLForeignBuiltinCallError: WGSL target cannot lower the call to <feature>(): <feature> is a built-in function of another language, and WGSL declares no built-in function of that name (target wgsl) [project.translate.wgsl-foreign-builtin-call]` (4): `fabs`, `rint`, `unpack_s8s16`, `unpack_u8u16`
- `project.translate.slang-import-unsupported: SlangImportRefused: CrossGL cannot represent N Slang construct: Slang <feature> has no CrossGL atomic operation (target cgl) [project.translate.slang-import-unsupported]` (2): `InterlockedCompareExchangeFloatBitwise`, `InterlockedCompareStoreFloatBitwise`
- `project.translate.crossgl-function-body-parse-failed: CrossGLFunctionBodyParseError: CrossGL could not parse the body of function '<probe>' at IDENTIFIER 'b': Expected SEMICOLON, got IDENTIFIER 'b'`: `multi-variable-loop`
- `project.translate.crossgl-syntax-error: CrossGLSyntaxError: Expected a structure name after 'struct', got MATCH 'match'`: `reserved-type-name`
- `project.translate.relative-vertex-id-unsupported: RelativeVertexIdUnsupportedError: gl_RelativeVertexID (Direct3D SV_VertexID): vertex entry point '<probe>' reads it, which excludes the draw's base vertex while the target's vertex index includes it, and WGSL has no base vertex built-in value to subtract; declare source_options={'zero_base_vertex': True} if every draw has a zero base v`: `vertex-index`
- `project.translate.slang-import-unsupported: SlangImportRefused: CrossGL cannot represent N Slang construct: numthreads x dimension size depends on specialization constant size; CrossGL fixes the workgroup size at translation time (target cgl) [project.translate.slang-import-unsupported]`: `specialization-workgroup-size`
- `project.translate.slang-syntax-error: SlangSyntaxError: Expected SEMICOLON, got LBRACKET`: `array-return`
- `project.translate.specialization-constant-unsupported: SpecializationConstantError: an array is sized by 'count', which follows a specialization constant; WGSL takes an override-expression element count only for the store type of a var<workgroup> (WGSL, Array Types) (target WGSL) [project.translate.specialization-constant-unsupported]`: `specialization-array-size`
- `project.translate.wgsl-refused: WGSLRefusal: WGSL target does not support storage buffer helper buffer_dimensions yet`: `runtime-array-length`

</details>

<details>
<summary>1 untested: function 1</summary>

- `the target's own probe is rejected: error: no definition in scope for identifier: 'subgroupElect'`: `WaveIsFirstLane`

</details>
