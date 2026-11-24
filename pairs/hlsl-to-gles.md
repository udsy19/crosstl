# CrossTL translation matrix: HLSL to GLSL ES

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native HLSL probe whose feature GLSL ES has too straight to GLSL ES, and glslangValidator checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 88.2 %: 352 supported, 24 refused, 23 wrong, 9 untested.

## Gaps

<details>
<summary>47 gaps: 24 refused, 23 wrong</summary>

Wrong, by cause:

- `'image variables not declared 'writeonly' and without a format layout qualifier' : not supported with this profile: es` (6): `RWBuffer.Load`, `RWTexture2D.Load`, `RWTexture2DArray.Load`, `RWTexture3D.Load`, `array-of-images`, `read-write-image`
- `'<feature>' : required extension not requested: GL_OES_sample_variables` (3): `sample-index`, `sample-mask`, `sample-mask-input`
- `'<feature>' : required extension not requested: Possible extensions include:` (2): `layer`, `primitive-id`
- `'<feature>' : undeclared identifier` (2): `barycentric-coordinate`, `vertex-index`
- `'image1D' : Reserved word.` (2): `RWTexture1D.GetDimensions`, `RWTexture1D.Load`
- `'image1DArray' : Reserved word.` (2): `RWTexture1DArray.GetDimensions`, `RWTexture1DArray.Load`
- `'variable indexing sampler array' : not supported for this version or the enabled extensions` (2): `array-of-textures-loop-index`, `array-of-textures-nonuniform-index`
- `'+' : wrong operand types: no operation '+' exists that takes a left-hand operand of type ' temp highp float' and a right operand of type ' const int' (or there is no acceptable conversion)`: `implicit-conversion`
- `'assign' : cannot convert from ' temp int' to ' temp highp uint'`: `runtime-array-length`
- `'noperspective' : Reserved word.`: `noperspective-interpolation`
- `'sample' : Reserved word.`: `sample-interpolation`

Refused, by diagnostic:

- `project.translate.opengl-geometry-stream-unsupported: GeometryStreamUnsupportedError: input vertex member 'position' is an array or structure; opengl geometry shaders write vertices through stage outputs and EmitVertex() (target opengl) [project.translate.opengl-geometry-stream-unsupported]` (9): `Stream.Append`, `Stream.RestartStrip`, `geometry-input-lines`, `geometry-input-lines-adjacency`, `geometry-input-triangles`, `geometry-input-triangles-adjacency`, `geometry-invocations`, `geometry-output-line-strip`, `geometry-output-triangle-strip`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N construct: call to '<feature>', which is neither a GLSL built-in function nor a function the program declares (target opengl) [project.translate.opengl-lowering-unsupported]` (4): `InterlockedCompareExchangeFloatBitwise`, `InterlockedCompareStoreFloatBitwise`, `f16tof32`, `f32tof16`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N constructs: GLSL version requirement: type 'double' does not exist in GLSL ES; the target is #version N es; GLSL version requirement: type 'dvec2' does not exist in GLSL ES; the target is #version N es; GLSL version requirement: type 'dvec3' does not exist in GLSL ES; the t` (3): `WaveMatch`, `WaveMultiPrefixProduct`, `WaveMultiPrefixSum`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N constructs: tessellation patch parameter 'patch' of type 'OutputPatch<ControlPoint, 3>' has no GLSL stage variable form: GLSL reads control points through <feature>[] and per-vertex input arrays; GLSL tessellation_evaluation stage cannot declare HLSL control-point patch parameter '` (3): `tessellation-evaluation`, `tessellation-level-input`, `tessellation-patch-input`
- `project.translate.opengl-geometry-stream-unsupported: GeometryStreamUnsupportedError: input vertex member 'position' is an array or structure; opengl geometry shaders write vertices through stage outputs and EmitVertex() (target opengl) [project.translate.opengl-geometry-stream-unsupported]`: `geometry`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N constructs: GLSL version requirement: type 'dvec2' does not exist in GLSL ES; the target is #version N es; GLSL version requirement: type 'double' does not exist in GLSL ES; the target is #version N es (target opengl) [project.translate.opengl-lowering-unsupported]`: `fma`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N constructs: tessellation patch parameter 'patch' of type 'OutputPatch<ControlPoint, 2>' has no GLSL stage variable form: GLSL reads control points through gl_in[] and per-vertex input arrays; GLSL tessellation_evaluation stage cannot declare HLSL control-point patch parameter '`: `tessellation-domain-isolines`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N constructs: tessellation patch parameter 'patch' of type 'OutputPatch<ControlPoint, 4>' has no GLSL stage variable form: GLSL reads control points through gl_in[] and per-vertex input arrays; GLSL tessellation_evaluation stage cannot declare HLSL control-point patch parameter '`: `tessellation-domain-quads`
- `project.translate.opengl-scalar-conversion-unsupported: OpenGLScalarConversionError: OpenGL cannot preserve source conversion from 'float16' to 'float16': half unsupported profile`: `half`

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
