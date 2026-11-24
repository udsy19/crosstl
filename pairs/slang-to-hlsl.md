# CrossTL translation matrix: Slang to HLSL

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native Slang probe whose feature HLSL has too straight to HLSL, and dxc checked the result. Its compute probes also ran on a runtime. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 90.8 %: 483 supported, 22 refused, 27 wrong, 0 untested.

## Gaps

<details>
<summary>49 gaps: 22 refused, 27 wrong</summary>

Wrong, by cause:

- `on vulkan-lavapipe as SPIR-V from slangc and dxc, the translation binds other resources than the native probe` (25): `uniform-array`, `uniform-bool`, `uniform-bool-vector`, `uniform-buffer`, `uniform-cbuffer-vector`, `uniform-in-helper`, `uniform-integer`, `uniform-integer-vector`, `uniform-matrix`, `uniform-matrix2`, `uniform-matrix3`, `uniform-members`, `uniform-non-square-matrix`, `uniform-row-major-array`, `uniform-row-major-matrix`, `uniform-row-major-non-square`, `uniform-std140-array`, `uniform-std140-vector`, `uniform-struct`, `uniform-struct-array`, `uniform-struct-copy`, `uniform-unsigned`, `uniform-vector`, `uniform-vector-array`, `uniform-vector-packing`
- `validation errors`: `GetAttributeAtVertex`
- `use of undeclared identifier 'MaybeReorderThread'`: `MaybeReorderThread`

Refused, by diagnostic:

- `project.translate.undeclared-function: UndeclaredFunctionError: function '<feature>' is not declared: it is neither a CrossGL built-in function nor a function, structure method, type or callable value of the program (target directx) [project.translate.undeclared-function]` (9): `ReorderThread`, `ReportHitOptix`, `f32tof16_`, `unpackHalf2x16ToFloat`, `unpackHalf2x16ToHalf`, `unpackInt4x8ToInt16`, `unpackInt4x8ToInt32`, `unpackUint4x8ToUint16`, `unpackUint4x8ToUint32`
- `project.translate.directx-lowering-unsupported: DirectXLoweringRefused: DirectX cannot lower N construct: function: call to '<feature>', a built-in function of another shading language that DirectX does not define and the program does not declare (target directx) [project.translate.directx-lowering-unsupported]` (3): `divide`, `max3`, `min3`
- `project.translate.slang-import-unsupported: SlangImportRefused: CrossGL cannot represent N Slang construct: Slang <feature> has no CrossGL atomic operation (target cgl) [project.translate.slang-import-unsupported]` (2): `InterlockedCompareExchangeFloatBitwise`, `InterlockedCompareStoreFloatBitwise`
- `project.translate.crossgl-function-body-parse-failed: CrossGLFunctionBodyParseError: CrossGL could not parse the body of function '<probe>' at IDENTIFIER 'b': Expected SEMICOLON, got IDENTIFIER 'b'`: `multi-variable-loop`
- `project.translate.crossgl-syntax-error: CrossGLSyntaxError: Expected a structure name after 'struct', got MATCH 'match'`: `reserved-type-name`
- `project.translate.directx-contextual-conversion-unrepresentable: DirectXContextualConversionError: DirectX NonUniformResourceIndex index argument must be scalar int or uint, got float`: `NonUniformResourceIndex`
- `project.translate.directx-refused: DirectXRefusal: DirectX ray_intersection ReportHit hit attribute argument must use a user-defined struct type or BuiltInTriangleIntersectionAttributes, got int`: `ReportHit`
- `project.translate.directx-refused: DirectXRefusal: DirectX wave intrinsic 'WaveActiveAllEqual' requires bool2 result context, got bool`: `WaveActiveAllEqual`
- `project.translate.slang-syntax-error: SlangSyntaxError: Expected SEMICOLON, got LBRACKET`: `array-return`
- `project.translate.undeclared-type: UndeclaredTypeError: type 'T' is not declared: it is neither a CrossGL built-in type nor a structure, enumeration, type alias or generic parameter of the program (target directx) [project.translate.undeclared-type]`: `generic-function`
- `project.translate.workgroup-uniform-load-unsupported: WorkgroupUniformLoadError: workgroupUniformLoad: '<probe>' is not a shared variable declared at program or stage scope for directx (target directx) [project.translate.workgroup-uniform-load-unsupported]`: `workgroupUniformLoad`

</details>
