# CrossTL translation matrix: Metal to GLSL

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native Metal probe whose feature GLSL has too straight to GLSL, and glslangValidator checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 93.9 %: 402 supported, 18 refused, 8 wrong, 0 untested.

## Gaps

<details>
<summary>26 gaps: 18 refused, 8 wrong</summary>

Wrong, by cause:

- `'slots' : member of block cannot be or contain a sampler, image, or atomic_uint type`: `unsized-array-of-textures`
- `the translation loses BuiltIn.ViewIndex, Capability.MultiView`: `view-index`
- `the translation loses Capability.ShaderNonUniform`: `array-of-textures-nonuniform-index`
- `the translation loses Decoration.Centroid`: `centroid-interpolation`
- `the translation loses Decoration.NoPerspective`: `noperspective-interpolation`
- `the translation loses Decoration.Sample, Capability.SampleRateShading`: `sample-interpolation`
- `the translation loses ImageFormat.Rgba8`: `unorm-storage-image`
- `the translation loses OpTypeSampler`: `shared-sampler`

Refused, by diagnostic:

- `project.translate.opengl-atomic-fence-unsupported: OpenGLAtomicFenceLoweringError: Cannot lower CrossGL atomicThreadFence to OpenGL GLSL without changing its semantics (flags=mem_device | mem_threadgroup | mem_threadgroup_imageblock | mem_texture | mem_object_data, order=memory_order_seq_cst, scope=thread_scope_device): unsupported thread scope` (10): `atomic_compare_exchange_weak`, `atomic_exchange`, `atomic_fetch_add`, `atomic_fetch_and`, `atomic_fetch_max`, `atomic_fetch_min`, `atomic_fetch_or`, `atomic_fetch_xor`, `atomic_max`, `atomic_min`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N construct: call to '<feature>', which is neither a GLSL built-in function nor a function the program declares (target opengl) [project.translate.opengl-lowering-unsupported]` (2): `dfdx`, `dfdy`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N construct: wave intrinsic: <feature> has no OpenGL subgroup equivalent (target opengl) [project.translate.opengl-lowering-unsupported]` (2): `simd_is_first`, `simd_shuffle_rotate_down`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N constructs: semantic 'SV_DomainLocation' is a Direct3D system value with no GLSL built-in variable; tessellation patch parameter 'patch_points' of type 'OutputPatch<ControlPoint, 3>' has no GLSL stage variable form: GLSL reads control points through <feature>[] and per-vertex input` (2): `tessellation-evaluation`, `tessellation-patch-input`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N constructs: semantic 'SV_DomainLocation' is a Direct3D system value with no GLSL built-in variable; tessellation patch parameter 'patch_points' of type 'OutputPatch<ControlPoint, 4>' has no GLSL stage variable form: GLSL reads control points through gl_in[] and per-vertex input`: `tessellation-domain-quads`
- `project.translate.opengl-scalar-conversion-unsupported: OpenGLScalarConversionError: OpenGL cannot preserve source conversion from '<unresolved>' to 'bool': boolean context source type unresolved`: `helper-invocation`

</details>
