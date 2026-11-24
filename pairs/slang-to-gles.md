# CrossTL translation matrix: Slang to GLSL ES

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native Slang probe whose feature GLSL ES has too straight to GLSL ES, and glslangValidator checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 86.0 %: 392 supported, 45 refused, 19 wrong, 9 untested.

## Gaps

<details>
<summary>64 gaps: 45 refused, 19 wrong</summary>

Wrong, by cause:

- `'<feature>' : required extension not requested: GL_OES_sample_variables` (3): `sample-index`, `sample-mask`, `sample-mask-input`
- `'subgroupShuffle' : no matching overloaded function found` (3): `WaveBroadcastLaneAt`, `WaveReadLaneAt`, `WaveShuffle`
- `'<feature>' : required extension not requested: Possible extensions include:` (2): `layer`, `primitive-id`
- `'<feature>' : undeclared identifier` (2): `barycentric-coordinate`, `vertex-index`
- `'image variables not declared 'writeonly' and without a format layout qualifier' : not supported with this profile: es` (2): `array-of-images`, `read-write-image`
- `'variable indexing sampler array' : not supported for this version or the enabled extensions` (2): `array-of-textures-loop-index`, `array-of-textures-nonuniform-index`
- `'' : syntax error, unexpected LEFT_ANGLE, expecting COMMA or SEMICOLON`: `storage-texel-buffer`
- `'+' : wrong operand types: no operation '+' exists that takes a left-hand operand of type ' temp highp float' and a right operand of type ' const int' (or there is no acceptable conversion)`: `implicit-conversion`
- `'assign' : cannot convert from ' temp int' to ' temp highp uint'`: `runtime-array-length`
- `'noperspective' : Reserved word.`: `noperspective-interpolation`
- `'sample' : Reserved word.`: `sample-interpolation`

Refused, by diagnostic:

- `project.translate.undeclared-function: UndeclaredFunctionError: function '<feature>' is not declared: it is neither a CrossGL built-in function nor a function, structure method, type or callable value of the program (target opengl) [project.translate.undeclared-function]` (11): `EvaluateAttributeAtCentroid`, `unpackHalf2x16ToFloat`, `unpackHalf2x16ToHalf`, `unpackSnorm2x16ToFloat`, `unpackSnorm2x16ToHalf`, `unpackSnorm4x8ToFloat`, `unpackSnorm4x8ToHalf`, `unpackUnorm2x16ToFloat`, `unpackUnorm2x16ToHalf`, `unpackUnorm4x8ToFloat`, `unpackUnorm4x8ToHalf`
- `project.translate.opengl-geometry-stream-unsupported: GeometryStreamUnsupportedError: input vertex member 'position' is an array or structure; opengl geometry shaders write vertices through stage outputs and EmitVertex() (target opengl) [project.translate.opengl-geometry-stream-unsupported]` (7): `geometry-input-lines`, `geometry-input-lines-adjacency`, `geometry-input-triangles`, `geometry-input-triangles-adjacency`, `geometry-invocations`, `geometry-output-line-strip`, `geometry-output-triangle-strip`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N constructs: GLSL version requirement: type 'double' does not exist in GLSL ES; the target is #version N es; GLSL version requirement: type 'dvec2' does not exist in GLSL ES; the target is #version N es; GLSL version requirement: type 'dvec3' does not exist in GLSL ES; the t` (5): `WaveMatch`, `WaveMultiPrefixExclusiveProduct`, `WaveMultiPrefixExclusiveSum`, `WaveMultiPrefixProduct`, `WaveMultiPrefixSum`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N constructs: tessellation patch parameter 'patch' of type 'OutputPatch<ControlPoint, 3>' has no GLSL stage variable form: GLSL reads control points through <feature>[] and per-vertex input arrays; GLSL tessellation_evaluation stage cannot declare HLSL control-point patch parameter '` (3): `tessellation-evaluation`, `tessellation-level-input`, `tessellation-patch-input`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N construct: call to '<feature>', which is neither a GLSL built-in function nor a function the program declares (target opengl) [project.translate.opengl-lowering-unsupported]` (2): `EvaluateAttributeAtSample`, `dst`
- `project.translate.opengl-tessellation-patch-unsupported: TessellationPatchUnsupportedError: member 'ControlPoint.position' (semantic in_Position) has no GLSL location, so it would link by name, and the lowered stage cannot declare an input and an output of the same name; opengl tessellation shaders exchange control points through per-vertex arrays, patch variables and <feature>/gl_` (2): `tessellation-control`, `tessellation-patch-output`
- `project.translate.slang-import-unsupported: SlangImportRefused: CrossGL cannot represent N Slang construct: Slang <feature> has no CrossGL atomic operation (target cgl) [project.translate.slang-import-unsupported]` (2): `InterlockedCompareExchangeFloatBitwise`, `InterlockedCompareStoreFloatBitwise`
- `project.translate.builtin-value-unsupported: BuiltinValueUnsupportedError: @SV_PointCoord is not a Direct3D system value; the HLSL system values are SV_Barycentrics, SV_ClipDistance, SV_Coverage, SV_CullDistance, SV_CullPrimitive, SV_Depth, SV_DepthGreaterEqual, SV_DepthLessEqual, SV_DispatchGrid, SV_DispatchThreadID, SV_DomainLocation, SV_GSInstanceID, SV_GroupID, SV_Grou`: `point-coordinate`
- `project.translate.crossgl-function-body-parse-failed: CrossGLFunctionBodyParseError: CrossGL could not parse the body of function '<probe>' at IDENTIFIER 'b': Expected SEMICOLON, got IDENTIFIER 'b'`: `multi-variable-loop`
- `project.translate.crossgl-syntax-error: CrossGLSyntaxError: Expected a structure name after 'struct', got MATCH 'match'`: `reserved-type-name`
- `project.translate.opengl-geometry-stream-unsupported: GeometryStreamUnsupportedError: input vertex member 'position' is an array or structure; opengl geometry shaders write vertices through stage outputs and EmitVertex() (target opengl) [project.translate.opengl-geometry-stream-unsupported]`: `geometry`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N construct: call through 'tex.Load': GLSL calls only named functions, constructors and length() (target opengl) [project.translate.opengl-lowering-unsupported]`: `texel-buffer`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N constructs: tessellation patch parameter 'patch' of type 'OutputPatch<ControlPoint, 2>' has no GLSL stage variable form: GLSL reads control points through gl_in[] and per-vertex input arrays; GLSL tessellation_evaluation stage cannot declare HLSL control-point patch parameter '`: `tessellation-domain-isolines`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N constructs: tessellation patch parameter 'patch' of type 'OutputPatch<ControlPoint, 4>' has no GLSL stage variable form: GLSL reads control points through gl_in[] and per-vertex input arrays; GLSL tessellation_evaluation stage cannot declare HLSL control-point patch parameter '`: `tessellation-domain-quads`
- `project.translate.opengl-metal-math-unrepresentable: OpenGLMetalMathError: OpenGL cannot preserve 'fabs' for operand types ('vec2',): unsupported-profile`: `fabs`
- `project.translate.opengl-scalar-conversion-unsupported: OpenGLScalarConversionError: OpenGL cannot preserve source conversion from 'half' to 'half': half unsupported profile`: `half`
- `project.translate.opengl-scalar-conversion-unsupported: OpenGLScalarConversionError: OpenGL cannot preserve source conversion from '<unresolved>' to 'bool': boolean context source type unresolved`: `helper-invocation`
- `project.translate.slang-import-unsupported: SlangImportRefused: CrossGL cannot represent N Slang construct: numthreads x dimension size depends on specialization constant size; CrossGL fixes the workgroup size at translation time (target cgl) [project.translate.slang-import-unsupported]`: `specialization-workgroup-size`
- `project.translate.slang-syntax-error: SlangSyntaxError: Expected SEMICOLON, got LBRACKET`: `array-return`
- `project.translate.workgroup-uniform-load-unsupported: WorkgroupUniformLoadError: workgroupUniformLoad: '<probe>' is not a shared variable declared at program or stage scope for opengl (target opengl) [project.translate.workgroup-uniform-load-unsupported]`: `workgroupUniformLoad`

</details>

<details>
<summary>9 untested: graphics 6, resource 1, type 2</summary>

- `the target's own probe is rejected: ERROR: 0:2: '#extension' : extension not supported: GL_EXT_clip_cull_distance` (2): `clip-distance`, `cull-distance`
- `the target's own probe is rejected: ERROR: 0:10: '64-bit integer' : not supported with this profile: es`: `int64`
- `the target's own probe is rejected: ERROR: 0:10: '64-bit unsigned integer' : not supported with this profile: es`: `uint64`
- `the target's own probe is rejected: ERROR: 0:2: '#extension' : extension not supported: GL_OES_viewport_array`: `viewport-index`
- `the target's own probe is rejected: ERROR: 0:5: 'fragment shader interlock layout qualifier' : not supported with this profile: es`: `rasterizer-ordered-buffer`
- `the target's own probe is rejected: ERROR: 0:6: 'fragment shader interlock layout qualifier' : not supported with this profile: es`: `rasterizer-ordered-image`
- `the target's own probe is rejected: ERROR: 0:9: '' : array size required`: `unsized-array-of-textures`
- `the target's own probe is rejected: ERROR: 0:9: 'gl_FragStencilRefARB' : undeclared identifier`: `stencil-export`

</details>
