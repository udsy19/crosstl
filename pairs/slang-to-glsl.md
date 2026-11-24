# CrossTL translation matrix: Slang to GLSL

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native Slang probe whose feature GLSL has too straight to GLSL, and glslangValidator checked the result. Its compute probes also ran on a runtime. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 90.3 %: 457 supported, 41 refused, 8 wrong, 0 untested.

## Gaps

<details>
<summary>49 gaps: 41 refused, 8 wrong</summary>

Wrong, by cause:

- `'' : syntax error, unexpected LEFT_ANGLE, expecting COMMA or SEMICOLON` (2): `rasterizer-ordered-buffer`, `storage-texel-buffer`
- `'=' : cannot convert from ' global double' to ' temp N-component vector of double'`: `asdouble`
- `on vulkan-lavapipe as SPIR-V from slangc and glslangValidator, the translation computes different results from the native probe`: `QuadReadLaneAt`
- `the translation loses Decoration.Flat`: `flat-interpolation`
- `the translation loses ImageFormat.R32ui`: `integer-storage-image`
- `the translation loses ImageFormat.Rgba8`: `unorm-storage-image`
- `the translation loses OpTypeSampler`: `shared-sampler`

Refused, by diagnostic:

- `project.translate.undeclared-function: UndeclaredFunctionError: function '<feature>' is not declared: it is neither a CrossGL built-in function nor a function, structure method, type or callable value of the program (target opengl) [project.translate.undeclared-function]` (11): `EvaluateAttributeAtCentroid`, `unpackHalf2x16ToFloat`, `unpackHalf2x16ToHalf`, `unpackSnorm2x16ToFloat`, `unpackSnorm2x16ToHalf`, `unpackSnorm4x8ToFloat`, `unpackSnorm4x8ToHalf`, `unpackUnorm2x16ToFloat`, `unpackUnorm2x16ToHalf`, `unpackUnorm4x8ToFloat`, `unpackUnorm4x8ToHalf`
- `project.translate.opengl-geometry-stream-unsupported: GeometryStreamUnsupportedError: input vertex member 'position' is an array or structure; opengl geometry shaders write vertices through stage outputs and EmitVertex() (target opengl) [project.translate.opengl-geometry-stream-unsupported]` (8): `geometry-input-lines`, `geometry-input-lines-adjacency`, `geometry-input-triangles`, `geometry-input-triangles-adjacency`, `geometry-invocations`, `geometry-output-line-strip`, `geometry-output-triangle-strip`, `geometry-streams`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N constructs: tessellation patch parameter 'patch' of type 'OutputPatch<ControlPoint, 3>' has no GLSL stage variable form: GLSL reads control points through <feature>[] and per-vertex input arrays; GLSL tessellation_evaluation stage cannot declare HLSL control-point patch parameter '` (3): `tessellation-evaluation`, `tessellation-level-input`, `tessellation-patch-input`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N construct: call to '<feature>', which is neither a GLSL built-in function nor a function the program declares (target opengl) [project.translate.opengl-lowering-unsupported]` (2): `EvaluateAttributeAtSample`, `dst`
- `project.translate.opengl-tessellation-patch-unsupported: TessellationPatchUnsupportedError: member 'ControlPoint.position' (semantic in_Position) has no GLSL location, so it would link by name, and the lowered stage cannot declare an input and an output of the same name; opengl tessellation shaders exchange control points through per-vertex arrays, patch variables and <feature>/gl_` (2): `tessellation-control`, `tessellation-patch-output`
- `project.translate.slang-import-unsupported: SlangImportRefused: CrossGL cannot represent N Slang construct: Slang <feature> has no CrossGL atomic operation (target cgl) [project.translate.slang-import-unsupported]` (2): `InterlockedCompareExchangeFloatBitwise`, `InterlockedCompareStoreFloatBitwise`
- `project.translate.builtin-value-unsupported: BuiltinValueUnsupportedError: @SV_PointCoord is not a Direct3D system value; the HLSL system values are SV_Barycentrics, SV_ClipDistance, SV_Coverage, SV_CullDistance, SV_CullPrimitive, SV_Depth, SV_DepthGreaterEqual, SV_DepthLessEqual, SV_DispatchGrid, SV_DispatchThreadID, SV_DomainLocation, SV_GSInstanceID, SV_GroupID, SV_Grou`: `point-coordinate`
- `project.translate.crossgl-function-body-parse-failed: CrossGLFunctionBodyParseError: CrossGL could not parse the body of function '<probe>' at IDENTIFIER 'b': Expected SEMICOLON, got IDENTIFIER 'b'`: `multi-variable-loop`
- `project.translate.crossgl-syntax-error: CrossGLSyntaxError: Expected a structure name after 'struct', got MATCH 'match'`: `reserved-type-name`
- `project.translate.opengl-geometry-stream-unsupported: GeometryStreamUnsupportedError: input vertex member 'position' is an array or structure; opengl geometry shaders write vertices through stage outputs and EmitVertex() (target opengl) [project.translate.opengl-geometry-stream-unsupported]`: `geometry`
- `project.translate.opengl-index-type-unsupported: OpenGLIndexTypeError: OpenGL cannot preserve subscript index type 'uvec2' for 'accum': vector index unsupported`: `rasterizer-ordered-image`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N construct: call through 'tex.Load': GLSL calls only named functions, constructors and length() (target opengl) [project.translate.opengl-lowering-unsupported]`: `texel-buffer`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N construct: type: the built-in type 'RaytracingAccelerationStructure' has no OpenGL spelling (target opengl) [project.translate.opengl-lowering-unsupported]`: `ray-payload`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N constructs: tessellation patch parameter 'patch' of type 'OutputPatch<ControlPoint, 2>' has no GLSL stage variable form: GLSL reads control points through gl_in[] and per-vertex input arrays; GLSL tessellation_evaluation stage cannot declare HLSL control-point patch parameter '`: `tessellation-domain-isolines`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N constructs: tessellation patch parameter 'patch' of type 'OutputPatch<ControlPoint, 4>' has no GLSL stage variable form: GLSL reads control points through gl_in[] and per-vertex input arrays; GLSL tessellation_evaluation stage cannot declare HLSL control-point patch parameter '`: `tessellation-domain-quads`
- `project.translate.opengl-scalar-conversion-unsupported: OpenGLScalarConversionError: OpenGL cannot preserve source conversion from '<unresolved>' to 'bool': boolean context source type unresolved`: `helper-invocation`
- `project.translate.slang-import-unsupported: SlangImportRefused: CrossGL cannot represent N Slang construct: numthreads x dimension size depends on specialization constant size; CrossGL fixes the workgroup size at translation time (target cgl) [project.translate.slang-import-unsupported]`: `specialization-workgroup-size`
- `project.translate.slang-syntax-error: SlangSyntaxError: Expected SEMICOLON, got LBRACKET`: `array-return`
- `project.translate.workgroup-uniform-load-unsupported: WorkgroupUniformLoadError: workgroupUniformLoad: '<probe>' is not a shared variable declared at program or stage scope for opengl (target opengl) [project.translate.workgroup-uniform-load-unsupported]`: `workgroupUniformLoad`

</details>
