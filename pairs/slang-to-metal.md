# CrossTL translation matrix: Slang to Metal

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native Slang probe whose feature Metal has too straight to Metal, and metal checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 93.8 %: 408 supported, 21 refused, 6 wrong, 0 untested.

## Gaps

<details>
<summary>27 gaps: 21 refused, 6 wrong</summary>

Wrong, by cause:

- `cannot initialize a variable of type 'thread int2' (vector of N 'int' values) with an rvalue of type 'metal::float2' (aka 'float2')`: `sign`
- `no member named 'Load' in 'metal::texture_buffer<float, metal::access::read, metal::memory_coherence_threadgroup>'`: `texel-buffer`
- `the translation loses Decoration.Centroid`: `centroid-interpolation`
- `the translation loses Decoration.Flat`: `flat-interpolation`
- `the translation loses Decoration.NoPerspective`: `noperspective-interpolation`
- `the translation loses Decoration.Sample`: `sample-interpolation`

Refused, by diagnostic:

- `project.translate.undeclared-function: UndeclaredFunctionError: function '<feature>' is not declared: it is neither a CrossGL built-in function nor a function, structure method, type or callable value of the program (target metal) [project.translate.undeclared-function]` (8): `unpackSnorm2x16ToFloat`, `unpackSnorm2x16ToHalf`, `unpackSnorm4x8ToFloat`, `unpackSnorm4x8ToHalf`, `unpackUnorm2x16ToFloat`, `unpackUnorm2x16ToHalf`, `unpackUnorm4x8ToFloat`, `unpackUnorm4x8ToHalf`
- `project.translate.metal-lowering-unsupported: MetalLoweringRefused: Metal cannot lower N construct: program-scope global store: global 'accum' is emitted in the constant address space (target metal) [project.translate.metal-lowering-unsupported]` (2): `rasterizer-ordered-buffer`, `rasterizer-ordered-image`
- `project.translate.metal-lowering-unsupported: MetalLoweringRefused: Metal cannot lower N constructs: semantic '<feature>' names no Metal attribute; the Metal compiler ignores an unknown attribute, so the declaration would lose the binding the semantic gives it; semantic '<feature>' names no Metal attribute; the Metal compiler ignores an unknown attri` (2): `tessellation-domain-quads`, `tessellation-evaluation`
- `project.translate.slang-import-unsupported: SlangImportRefused: CrossGL cannot represent N Slang construct: Slang <feature> has no CrossGL atomic operation (target cgl) [project.translate.slang-import-unsupported]` (2): `InterlockedCompareExchangeFloatBitwise`, `InterlockedCompareStoreFloatBitwise`
- `project.translate.builtin-value-unsupported: BuiltinValueUnsupportedError: @SV_PointCoord is not a Direct3D system value; the HLSL system values are SV_Barycentrics, SV_ClipDistance, SV_Coverage, SV_CullDistance, SV_CullPrimitive, SV_Depth, SV_DepthGreaterEqual, SV_DepthLessEqual, SV_DispatchGrid, SV_DispatchThreadID, SV_DomainLocation, SV_GSInstanceID, SV_GroupID, SV_Grou`: `point-coordinate`
- `project.translate.crossgl-function-body-parse-failed: CrossGLFunctionBodyParseError: CrossGL could not parse the body of function '<probe>' at IDENTIFIER 'b': Expected SEMICOLON, got IDENTIFIER 'b'`: `multi-variable-loop`
- `project.translate.crossgl-syntax-error: CrossGLSyntaxError: Expected a structure name after 'struct', got MATCH 'match'`: `reserved-type-name`
- `project.translate.metal-lowering-unsupported: MetalLoweringRefused: Metal cannot lower N construct: function: call to 'IsHelperLane', a built-in function of another shading language that Metal does not define and the program does not declare (target metal) [project.translate.metal-lowering-unsupported]`: `helper-invocation`
- `project.translate.slang-syntax-error: SlangSyntaxError: Expected SEMICOLON, got LBRACKET`: `array-return`
- `project.translate.undeclared-type: UndeclaredTypeError: type 'T' is not declared: it is neither a CrossGL built-in type nor a structure, enumeration, type alias or generic parameter of the program (target metal) [project.translate.undeclared-type]`: `generic-function`
- `project.translate.workgroup-uniform-load-unsupported: WorkgroupUniformLoadError: workgroupUniformLoad: '<probe>' is not a shared variable declared at program or stage scope for metal (target metal) [project.translate.workgroup-uniform-load-unsupported]`: `workgroupUniformLoad`

</details>
