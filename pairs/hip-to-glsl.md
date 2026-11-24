# CrossTL translation matrix: HIP to GLSL

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native HIP probe whose feature GLSL has too straight to GLSL, and glslangValidator checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 89.5 %: 248 supported, 21 refused, 8 wrong, 0 untested.

## Gaps

<details>
<summary>29 gaps: 21 refused, 8 wrong</summary>

Wrong, by cause:

- `'tex' : undeclared identifier` (2): `texture-argument`, `texture-in-helper`
- `the translation loses BuiltIn.LocalInvocationIndex`: `local-invocation-index`
- `the translation loses BuiltIn.NumSubgroups`: `num-subgroups`
- `the translation loses BuiltIn.SubgroupId`: `subgroup-id`
- `the translation loses Decoration.Restrict`: `restrict-buffer`
- `the translation loses Decoration.Volatile`: `volatile-buffer`
- `the translation loses Dim.Buffer, Capability.SampledBuffer`: `texel-buffer`

Refused, by diagnostic:

- `project.translate.opengl-builtin-operand-unsupported: OpenGLBuiltinOperandError: OpenGL cannot translate '<feature>' of double: GLSL declares it for N-bit floating-point operands only (GLSL N.N sections N.N and N.N), and converting a N-bit operand would change its range and precision` (10): `acos`, `acosh`, `asin`, `asinh`, `atan`, `atanh`, `cosh`, `sinh`, `tan`, `tanh`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N construct: call to '<feature>', which is neither a GLSL built-in function nor a function the program declares (target opengl) [project.translate.opengl-lowering-unsupported]` (3): `__isinff`, `__isnanf`, `ldexpf`
- `project.translate.hip-surface-byte-offset-unproven: HipSurfaceByteOffsetError: surf2Dwrite cannot scale its x byte offset N: the element type is unknown, so the offset cannot be shown to be a multiple of the element size [project.translate.hip-surface-byte-offset-unproven]`: `read-write-image`
- `project.translate.opengl-builtin-operand-unsupported: OpenGLBuiltinOperandError: OpenGL cannot translate 'atan2' of double, double: GLSL declares it for N-bit floating-point operands only (GLSL N.N sections N.N and N.N), and converting a N-bit operand would change its range and precision`: `atan2`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N construct: call to '__lane_id', which is neither a GLSL built-in function nor a function the program declares (target opengl) [project.translate.opengl-lowering-unsupported]`: `subgroup-invocation-id`
- `project.translate.opengl-refused: OpenGLRefusal: OpenGL image store operation 'imageStore' requires float value for image2D images: u32(fin[i]) has type uint`: `integer-storage-image`
- `project.translate.opengl-refused: OpenGLRefusal: OpenGL image store operation 'imageStore' requires float value for image2D images: vec4<u8>(v, v, v, v) has type uint`: `unorm-storage-image`
- `project.translate.rule-inexpressible: RuleInexpressibleError: __cgl_libm_cos on a N-bit floating-point operand has no helper for opengl: the helper takes binary32 values only (target opengl) [project.translate.rule-inexpressible]`: `cos`
- `project.translate.rule-inexpressible: RuleInexpressibleError: __cgl_libm_sin on a N-bit floating-point operand has no helper for opengl: the helper takes binary32 values only (target opengl) [project.translate.rule-inexpressible]`: `sin`
- `project.translate.rule-inexpressible: RuleInexpressibleError: __cgl_round_away on a N-bit floating-point operand has no helper for opengl: the helper takes binary32 values only (target opengl) [project.translate.rule-inexpressible]`: `round`

</details>
