<!-- Written from coverage.json by tools/coverage/docs.py when the Coverage workflow publishes. Do not edit. -->

# GLSL ES

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z (CrossTL 3.8.0) by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). The Coverage workflow writes this page from `coverage.json` each time it publishes; [COVERAGE.md](../COVERAGE.md) defines each outcome. Score = supported / (supported + refused + wrong).

| Direction | Score | Supported | Refused | Wrong | Untested | Executed | Reference tool |
|---|---:|---:|---:|---:|---:|---|---|
| output | 95.9 % | 513 | 4 | 18 | 9 | compile-only | glslangValidator (Glslang Version: 11:16.6.0) |
| input | not offered | | | | | | |

GLSL ES input is not offered: GLSL ES sources are read as GLSL, which the GLSL and WebGL input rows measure.

## By category

Each cell counts the supported features of a category over its supported, refused and wrong ones.

| Category | output |
|---|---:|
| compute | 28/28 |
| control-flow | 59/59 |
| function | 219/225 |
| graphics | 30/41 |
| operator | 50/51 |
| resource | 60/63 |
| stage | 6/6 |
| type | 61/62 |

## Translation pairs

The cells of the translation matrix that translate GLSL ES straight to another language or another language straight to it, measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z. Each cell measures the features of the source's input row that the target has too, and its page lists the gaps.

| Source | Target | Score | Supported | Refused | Wrong | Untested | Executed |
|---|---|---:|---:|---:|---:|---:|---|
| CUDA | GLSL ES | [90.8 %](../pairs/cuda-to-gles.md) | 218 | 13 | 9 | 2 | compile-only |
| GLSL | GLSL ES | [96.7 %](../pairs/glsl-to-gles.md) | 520 | 4 | 14 | 9 | compile-only |
| HIP | GLSL ES | [92.1 %](../pairs/hip-to-gles.md) | 222 | 9 | 10 | 2 | compile-only |
| HLSL | GLSL ES | [88.2 %](../pairs/hlsl-to-gles.md) | 352 | 24 | 23 | 9 | compile-only |
| Metal | GLSL ES | [85.0 %](../pairs/metal-to-gles.md) | 339 | 25 | 35 | 8 | compile-only |
| Mojo | GLSL ES | [0.0 %](../pairs/mojo-to-gles.md) | 0 | 229 | 0 | 2 | compile-only |
| OpenCL C | GLSL ES | [86.0 %](../pairs/opencl-to-gles.md) | 203 | 20 | 13 | 2 | compile-only |
| Rust | GLSL ES | [35.6 %](../pairs/rust-to-gles.md) | 154 | 173 | 105 | 7 | compile-only |
| Slang | GLSL ES | [86.0 %](../pairs/slang-to-gles.md) | 392 | 45 | 19 | 9 | compile-only |
| SPIR-V | GLSL ES | [56.6 %](../pairs/spirv-to-gles.md) | 257 | 8 | 189 | 9 | compile-only |
| WebGL | GLSL ES | [100.0 %](../pairs/webgl-to-gles.md) | 298 | 0 | 0 | 0 | compile-only |

## Gaps

A diagnostic drops its line numbers and writes the probe's own variables as `<probe>`, and one that several features share writes each feature's name as `<feature>`.

### Output

Wrong, by cause ([open bug issues](https://github.com/CrossGL/crosstl/issues?q=is:issue%20is:open%20label:coverage%20label:bug%20label:backend:gles%20label:direction:output)):

- `'<feature>' : undeclared identifier` (8): `barycentric-coordinate`, `helper-invocation`, `layer`, `primitive-id`, `sample-index`, `sample-mask`, `sample-mask-input`, `shading-rate`
- `'rgba32f' : format requires readonly or writeonly memory qualifier` (4): `imageLoad`, `imageSize`, `imageStore`, `storage-image`
- `'variable indexing sampler array' : not supported for this version or the enabled extensions` (2): `array-of-textures-loop-index`, `array-of-textures-nonuniform-index`
- `'+' : wrong operand types: no operation '+' exists that takes a left-hand operand of type ' temp highp float' and a right operand of type ' const int' (or there is no acceptable conversion)`: `implicit-conversion`
- `'early_fragment_tests' : not supported for this version or the enabled extensions`: `early-fragment-tests`
- `'noperspective' : Reserved word.`: `noperspective-interpolation`
- `'sample' : Reserved word.`: `sample-interpolation`

Refused, by diagnostic:

- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N constructs: GLSL version requirement: type 'double' does not exist in GLSL ES; the target is #version N es; GLSL version requirement: type 'dvec2' does not exist in GLSL ES; the target is #version N es; GLSL version requirement: type 'dvec3' does not exist in GLSL ES; the t` (3): `subgroupPartitionNV`, `subgroupPartitionedExclusiveAddNV`, `subgroupPartitionedExclusiveMulNV`
- `project.translate.opengl-scalar-conversion-unsupported: OpenGLScalarConversionError: OpenGL cannot preserve source conversion from 'half' to 'half': half unsupported profile`: `half`

Untested, by reason:

- `the probe itself is rejected: ERROR: 0:2: '#extension' : extension not supported: GL_EXT_clip_cull_distance` (2): `clip-distance`, `cull-distance`
- `the probe itself is rejected: ERROR: 0:10: '64-bit integer' : not supported with this profile: es`: `int64`
- `the probe itself is rejected: ERROR: 0:10: '64-bit unsigned integer' : not supported with this profile: es`: `uint64`
- `the probe itself is rejected: ERROR: 0:2: '#extension' : extension not supported: GL_OES_viewport_array`: `viewport-index`
- `the probe itself is rejected: ERROR: 0:5: 'fragment shader interlock layout qualifier' : not supported with this profile: es`: `rasterizer-ordered-buffer`
- `the probe itself is rejected: ERROR: 0:6: 'fragment shader interlock layout qualifier' : not supported with this profile: es`: `rasterizer-ordered-image`
- `the probe itself is rejected: ERROR: 0:9: '' : array size required`: `unsized-array-of-textures`
- `the probe itself is rejected: ERROR: 0:9: 'gl_FragStencilRefARB' : undeclared identifier`: `stencil-export`
