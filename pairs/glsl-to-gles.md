# CrossTL translation matrix: GLSL to GLSL ES

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native GLSL probe whose feature GLSL ES has too straight to GLSL ES, and glslangValidator checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 96.7 %: 520 supported, 4 refused, 14 wrong, 9 untested.

## Gaps

<details>
<summary>18 gaps: 4 refused, 14 wrong</summary>

Wrong, by cause:

- `'<feature>' : required extension not requested: GL_OES_sample_variables` (3): `sample-index`, `sample-mask`, `sample-mask-input`
- `'rgba32f' : format requires readonly or writeonly memory qualifier` (3): `imageLoad`, `imageSize`, `imageStore`
- `'<feature>' : required extension not requested: Possible extensions include:` (2): `layer`, `primitive-id`
- `'variable indexing sampler array' : not supported for this version or the enabled extensions` (2): `array-of-textures-loop-index`, `array-of-textures-nonuniform-index`
- `'+' : wrong operand types: no operation '+' exists that takes a left-hand operand of type ' temp highp float' and a right operand of type ' const int' (or there is no acceptable conversion)`: `implicit-conversion`
- `'gl_BaryCoordEXT' : undeclared identifier`: `barycentric-coordinate`
- `'noperspective' : Reserved word.`: `noperspective-interpolation`
- `'sample' : Reserved word.`: `sample-interpolation`

Refused, by diagnostic:

- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N constructs: GLSL version requirement: type 'double' does not exist in GLSL ES; the target is #version N es; GLSL version requirement: type 'dvec2' does not exist in GLSL ES; the target is #version N es; GLSL version requirement: type 'dvec3' does not exist in GLSL ES; the t` (3): `subgroupPartitionNV`, `subgroupPartitionedExclusiveAddNV`, `subgroupPartitionedExclusiveMulNV`
- `project.translate.opengl-scalar-conversion-unsupported: OpenGLScalarConversionError: OpenGL cannot preserve source conversion from 'float16_t' to 'float16_t': half unsupported profile`: `half`

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
