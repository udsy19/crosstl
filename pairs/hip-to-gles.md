# CrossTL translation matrix: HIP to GLSL ES

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native HIP probe whose feature GLSL ES has too straight to GLSL ES, and glslangValidator checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 92.1 %: 222 supported, 9 refused, 10 wrong, 2 untested.

## Gaps

<details>
<summary>19 gaps: 9 refused, 10 wrong</summary>

Wrong, by cause:

- `'rgba32f' : format requires readonly or writeonly memory qualifier` (3): `storage-image`, `storage-image-3d`, `storage-image-array`
- `'tex' : undeclared identifier` (2): `texture-argument`, `texture-in-helper`
- `'+' : wrong operand types: no operation '+' exists that takes a left-hand operand of type ' temp highp float' and a right operand of type ' const int' (or there is no acceptable conversion)`: `implicit-conversion`
- `'-' : wrong operand types: no operation '-' exists that takes a left-hand operand of type ' temp highp uint' and a right operand of type ' const int' (or there is no acceptable conversion)`: `num-subgroups`
- `'=' : cannot convert from ' global lowp int' to ' temp highp uint'`: `__popc`
- `'mod' : undeclared identifier`: `reserved-global-name`
- `'sampler1D' : Reserved word.`: `texel-buffer`

Refused, by diagnostic:

- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N construct: call to '<feature>', which is neither a GLSL built-in function nor a function the program declares (target opengl) [project.translate.opengl-lowering-unsupported]` (3): `__isinff`, `__isnanf`, `ldexpf`
- `project.translate.hip-surface-byte-offset-unproven: HipSurfaceByteOffsetError: surf2Dwrite cannot scale its x byte offset N: the element type is unknown, so the offset cannot be shown to be a multiple of the element size [project.translate.hip-surface-byte-offset-unproven]`: `read-write-image`
- `project.translate.opengl-fmod-unrepresentable: OpenGLFloatingRemainderError: OpenGL cannot preserve floating remainder for ('f32', 'float'): unsupported-profile`: `float-remainder`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N construct: call to '__lane_id', which is neither a GLSL built-in function nor a function the program declares (target opengl) [project.translate.opengl-lowering-unsupported]`: `subgroup-invocation-id`
- `project.translate.opengl-refused: OpenGLRefusal: OpenGL image store operation 'imageStore' requires float value for image2D images: u32(fin[i]) has type uint`: `integer-storage-image`
- `project.translate.opengl-refused: OpenGLRefusal: OpenGL image store operation 'imageStore' requires float value for image2D images: vec4<u8>(v, v, v, v) has type uint`: `unorm-storage-image`
- `project.translate.opengl-scalar-conversion-unsupported: OpenGLScalarConversionError: OpenGL cannot preserve source conversion from 'f16' to 'f16': half unsupported profile`: `half`

</details>

<details>
<summary>2 untested: type 2</summary>

- `the target's own probe is rejected: ERROR: 0:10: '64-bit integer' : not supported with this profile: es`: `int64`
- `the target's own probe is rejected: ERROR: 0:10: '64-bit unsigned integer' : not supported with this profile: es`: `uint64`

</details>
