# CrossTL translation matrix: Metal to GLSL ES

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native Metal probe whose feature GLSL ES has too straight to GLSL ES, and glslangValidator checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 85.0 %: 339 supported, 25 refused, 35 wrong, 8 untested.

## Gaps

<details>
<summary>60 gaps: 25 refused, 35 wrong</summary>

Wrong, by cause:

- `'CrossGLMetalVectorIndex_vec2_get' : no matching overloaded function found` (13): `constant-matrix`, `diagonal-matrix`, `matrix-arithmetic`, `matrix-column-assignment`, `matrix-compound-assignment`, `matrix-from-vectors`, `matrix-indexing`, `matrix-negation`, `matrix-parameter`, `matrix-resize`, `struct-matrix-member`, `uniform-matrix2`, `uniform-row-major-array`
- `'<feature>' : undeclared identifier` (6): `barycentric-coordinate`, `layer`, `primitive-id`, `sample-index`, `sample-mask`, `sample-mask-input`
- `'CrossGLMetalVectorIndex_vec3_get' : no matching overloaded function found` (4): `uniform-matrix3`, `uniform-non-square-matrix`, `uniform-row-major-matrix`, `uniform-row-major-non-square`
- `'CrossGLMetalVectorIndex_vec2_add_assign_resource_r_index_glsl_data_outp_Rows' : no matching overloaded function found` (2): `buffer-row-major-matrix`, `buffer-row-major-non-square`
- `'rgba32f' : format requires readonly or writeonly memory qualifier` (2): `array-of-images`, `read-write-image`
- `'variable indexing sampler array' : not supported for this version or the enabled extensions` (2): `array-of-textures-loop-index`, `array-of-textures-nonuniform-index`
- `'+' : wrong operand types: no operation '+' exists that takes a left-hand operand of type ' temp highp float' and a right operand of type ' const int' (or there is no acceptable conversion)`: `implicit-conversion`
- `'CrossGLMetalVectorIndex_vec2_add_assign_resource_index_glsl_data_outp_mat2' : no matching overloaded function found`: `matrix-buffer`
- `'CrossGLMetalVectorIndex_vec2_add_assign_resource_r_index_index_glsl_data_outp_Rows' : no matching overloaded function found`: `buffer-row-major-array`
- `'CrossGLMetalVectorIndex_vec2_set' : no matching overloaded function found`: `matrix-array`
- `'CrossGLMetalVectorIndex_vec4_get' : no matching overloaded function found`: `uniform-matrix`
- `'early_fragment_tests' : not supported for this version or the enabled extensions`: `early-fragment-tests`

Refused, by diagnostic:

- `project.translate.opengl-atomic-fence-unsupported: OpenGLAtomicFenceLoweringError: Cannot lower CrossGL atomicThreadFence to OpenGL GLSL without changing its semantics (flags=mem_device | mem_threadgroup | mem_threadgroup_imageblock | mem_texture | mem_object_data, order=memory_order_seq_cst, scope=thread_scope_device): unsupported thread scope` (10): `atomic_compare_exchange_weak`, `atomic_exchange`, `atomic_fetch_add`, `atomic_fetch_and`, `atomic_fetch_max`, `atomic_fetch_min`, `atomic_fetch_or`, `atomic_fetch_xor`, `atomic_max`, `atomic_min`
- `project.translate.opengl-refused: OpenGLRefusal: OpenGL target profile '#version N es' does not support GL_ARB_gpu_shader_int64; select a desktop GLSL profile for N-bit integer values` (3): `atomic_max_explicit`, `atomic_min_explicit`, `simd_ballot`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N construct: call to '<feature>', which is neither a GLSL built-in function nor a function the program declares (target opengl) [project.translate.opengl-lowering-unsupported]` (2): `dfdx`, `dfdy`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N construct: wave intrinsic: <feature> has no OpenGL subgroup equivalent (target opengl) [project.translate.opengl-lowering-unsupported]` (2): `simd_is_first`, `simd_shuffle_rotate_down`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N constructs: semantic 'SV_DomainLocation' is a Direct3D system value with no GLSL built-in variable; tessellation patch parameter 'patch_points' of type 'OutputPatch<ControlPoint, 3>' has no GLSL stage variable form: GLSL reads control points through <feature>[] and per-vertex input` (2): `tessellation-evaluation`, `tessellation-patch-input`
- `project.translate.opengl-fmod-unrepresentable: OpenGLFloatingRemainderError: OpenGL cannot preserve floating remainder for ('float', 'float'): unsupported-profile`: `float-remainder`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N constructs: semantic 'SV_DomainLocation' is a Direct3D system value with no GLSL built-in variable; tessellation patch parameter 'patch_points' of type 'OutputPatch<ControlPoint, 4>' has no GLSL stage variable form: GLSL reads control points through gl_in[] and per-vertex input`: `tessellation-domain-quads`
- `project.translate.opengl-metal-math-unrepresentable: OpenGLMetalMathError: OpenGL cannot preserve 'select' for operand types ('vec3', 'vec3', 'bvec3'): unsupported-profile`: `select`
- `project.translate.opengl-metal-math-unrepresentable: OpenGLMetalMathError: OpenGL cannot preserve 'fabs' for operand types ('vec3',): unsupported-profile`: `fabs`
- `project.translate.opengl-scalar-conversion-unsupported: OpenGLScalarConversionError: OpenGL cannot preserve source conversion from '<unresolved>' to 'bool': boolean context source type unresolved`: `helper-invocation`
- `project.translate.opengl-scalar-conversion-unsupported: OpenGLScalarConversionError: OpenGL cannot preserve source conversion from 'float16' to 'float16': half unsupported profile`: `half`

</details>

<details>
<summary>8 untested: graphics 5, resource 1, type 2</summary>

- `the target's own probe is rejected: ERROR: 0:10: '64-bit integer' : not supported with this profile: es`: `int64`
- `the target's own probe is rejected: ERROR: 0:10: '64-bit unsigned integer' : not supported with this profile: es`: `uint64`
- `the target's own probe is rejected: ERROR: 0:2: '#extension' : extension not supported: GL_EXT_clip_cull_distance`: `clip-distance`
- `the target's own probe is rejected: ERROR: 0:2: '#extension' : extension not supported: GL_OES_viewport_array`: `viewport-index`
- `the target's own probe is rejected: ERROR: 0:5: 'fragment shader interlock layout qualifier' : not supported with this profile: es`: `rasterizer-ordered-buffer`
- `the target's own probe is rejected: ERROR: 0:6: 'fragment shader interlock layout qualifier' : not supported with this profile: es`: `rasterizer-ordered-image`
- `the target's own probe is rejected: ERROR: 0:9: '' : array size required`: `unsized-array-of-textures`
- `the target's own probe is rejected: ERROR: 0:9: 'gl_FragStencilRefARB' : undeclared identifier`: `stencil-export`

</details>
