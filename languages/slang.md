<!-- Written from coverage.json by tools/coverage/docs.py when the Coverage workflow publishes. Do not edit. -->

# Slang

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z (CrossTL 3.8.0) by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). The Coverage workflow writes this page from `coverage.json` each time it publishes; [COVERAGE.md](../COVERAGE.md) defines each outcome. Score = supported / (supported + refused + wrong).

The [backend guide](https://github.com/CrossGL/crosstl/blob/main/docs/source/backends/slang.rst) describes how CrossTL translates Slang.

| Direction | Score | Supported | Refused | Wrong | Untested | Executed | Reference tool |
|---|---:|---:|---:|---:|---:|---|---|
| output | 88.3 % | 616 | 82 | 0 | 9 | 401 on vulkan-lavapipe | slangc (2026.20) |
| input | 86.0 % | 600 | 98 | 0 | 9 | 387 on vulkan-lavapipe | slangc (2026.20) |

## Feature lists

- [Slang v2026.20 core module: HLSL-compatible built-in functions](https://github.com/shader-slang/slang/blob/d9ede2dd5836afc0e9586da18d9236b171d0faa8/source/slang/hlsl.meta.slang), pinned at `d9ede2dd5836`
- [Slang v2026.20 core module: core built-in functions](https://github.com/shader-slang/slang/blob/d9ede2dd5836afc0e9586da18d9236b171d0faa8/source/slang/core.meta.slang), pinned at `d9ede2dd5836`

## By category

Each cell counts the supported features of a category over its supported, refused and wrong ones.

| Category | output | input |
|---|---:|---:|
| compute | 24/24 | 23/24 |
| control-flow | 62/62 | 60/62 |
| function | 267/343 | 255/343 |
| graphics | 65/67 | 65/67 |
| operator | 51/51 | 51/51 |
| resource | 65/67 | 66/67 |
| stage | 14/14 | 14/14 |
| type | 68/70 | 66/70 |

## Translation pairs

The cells of the translation matrix that translate Slang straight to another language or another language straight to it, measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z. Each cell measures the features of the source's input row that the target has too, and its page lists the gaps.

| Source | Target | Score | Supported | Refused | Wrong | Untested | Executed |
|---|---|---:|---:|---:|---:|---:|---|
| Slang | CUDA | [93.7 %](../pairs/slang-to-cuda.md) | 239 | 8 | 8 | 0 | compile-only |
| Slang | GLSL ES | [86.0 %](../pairs/slang-to-gles.md) | 392 | 45 | 19 | 9 | compile-only |
| Slang | GLSL | [90.3 %](../pairs/slang-to-glsl.md) | 457 | 41 | 8 | 0 | yes |
| Slang | HIP | [93.4 %](../pairs/slang-to-hip.md) | 240 | 8 | 9 | 0 | compile-only |
| Slang | HLSL | [90.8 %](../pairs/slang-to-hlsl.md) | 483 | 22 | 27 | 0 | yes |
| Slang | Metal | [93.8 %](../pairs/slang-to-metal.md) | 408 | 21 | 6 | 0 | compile-only |
| Slang | Mojo | [0.0 %](../pairs/slang-to-mojo.md) | 0 | 19 | 211 | 0 | compile-only |
| Slang | Rust | [59.2 %](../pairs/slang-to-rust.md) | 270 | 176 | 10 | 0 | yes |
| Slang | SPIR-V | [84.4 %](../pairs/slang-to-spirv.md) | 411 | 41 | 35 | 0 | yes |
| Slang | WebGL | [64.7 %](../pairs/slang-to-webgl.md) | 11 | 5 | 1 | 0 | compile-only |
| Slang | WGSL | [81.7 %](../pairs/slang-to-wgsl.md) | 309 | 34 | 35 | 1 | yes |
| CUDA | Slang | [83.0 %](../pairs/cuda-to-slang.md) | 239 | 24 | 25 | 0 | compile-only |
| GLSL | Slang | [92.7 %](../pairs/glsl-to-slang.md) | 454 | 31 | 5 | 0 | yes |
| HIP | Slang | [83.7 %](../pairs/hip-to-slang.md) | 242 | 22 | 25 | 0 | compile-only |
| HLSL | Slang | [96.0 %](../pairs/hlsl-to-slang.md) | 499 | 11 | 10 | 0 | yes |
| Metal | Slang | [86.0 %](../pairs/metal-to-slang.md) | 370 | 51 | 9 | 0 | compile-only |
| Mojo | Slang | [0.0 %](../pairs/mojo-to-slang.md) | 0 | 229 | 0 | 0 | compile-only |
| OpenCL C | Slang | [86.3 %](../pairs/opencl-to-slang.md) | 221 | 34 | 1 | 0 | compile-only |
| Rust | Slang | [56.4 %](../pairs/rust-to-slang.md) | 267 | 115 | 91 | 0 | yes |
| SPIR-V | Slang | [19.7 %](../pairs/spirv-to-slang.md) | 93 | 54 | 325 | 0 | yes |
| WebGL | Slang | [97.4 %](../pairs/webgl-to-slang.md) | 259 | 6 | 1 | 0 | compile-only |

## Gaps

A diagnostic drops its line numbers and writes the probe's own variables as `<probe>`, and one that several features share writes each feature's name as `<feature>`.

### Output

Refused, by diagnostic:

- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: call to <feature>: <feature> is a built-in function of another language, and Slang declares no function of that name (target slang) [project.translate.slang-lowering-unsupported]` (35): `EvaluateAttributeAtCentroid`, `bitfieldExtract`, `bitfieldInsert`, `copysign`, `copysign_double`, `copysign_float`, `copysign_half`, `divide`, `fabs`, `fdim`, `fmax`, `fmax3`, `fmedian3`, `fmin`, `fmin3`, `max3`, `median3`, `min3`, `nextafter`, `packHalf2x16`, `packSnorm2x16`, `packSnorm4x8`, `packUnorm2x16`, `packUnorm4x8`, `rint`, `unpackHalf2x16ToFloat`, `unpackHalf2x16ToHalf`, `unpackSnorm2x16ToFloat`, `unpackSnorm2x16ToHalf`, `unpackSnorm4x8ToFloat`, `unpackSnorm4x8ToHalf`, `unpackUnorm2x16ToFloat`, `unpackUnorm2x16ToHalf`, `unpackUnorm4x8ToFloat`, `unpackUnorm4x8ToHalf`
- `project.translate.undeclared-function: UndeclaredFunctionError: function '<feature>' is not declared: it is neither a CrossGL built-in function nor a function, structure method, type or callable value of the program (target slang) [project.translate.undeclared-function]` (30): `GetClusterID`, `GetLssPositionsAndRadii`, `GetSpherePositionAndRadius`, `InterlockedAddF16Emulated`, `InterlockedAddF16x2`, `IsLssHit`, `IsSphereHit`, `RayCurrentTime`, `ReportHitOptix`, `TraceMotionRay`, `bit_cast`, `coopVecLoad`, `coopVecLoadCoherent`, `coopVecLoadGroupshared`, `debugBreak`, `defaultGetDescriptorFromHandle`, `f32tof16_`, `floatCast`, `getDescriptorFromDescriptorHeapEXT`, `getDescriptorFromDynamicResourceHeap`, `getDescriptorFromExplicitHeapIndex`, `getStringHash`, `loadAligned`, `makeTuple`, `nonuniform`, `reinterpret`, `storeAligned`, `unmodified`, `unused`, `usesNativeSpirvDescriptorHandle`
- `project.translate.undeclared-function: UndeclaredFunctionError: function 'CoopVec' is not declared: it is neither a CrossGL built-in function nor a function, structure method, type or callable value of the program (target slang) [project.translate.undeclared-function]` (6): `coopVecMatMul`, `coopVecMatMulAdd`, `coopVecMatMulAddPacked`, `coopVecMatMulPacked`, `coopVecOuterProductAccumulate`, `coopVecReduceSumAccumulate`
- `project.translate.slang-metal-math-function-unsupported: MetalMathFunctionUnsupportedError: <feature> is exact at integers and half-integers, which slang has no function for, and CrossTL does not lower it with an exact range reduction yet (target slang) [project.translate.slang-metal-math-function-unsupported]` (3): `cospi`, `sinpi`, `tanpi`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: Slang image access: imageStore requires an image resource (target slang) [project.translate.slang-lowering-unsupported]`: `storage-texel-buffer`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: Slang sampled texture: texelFetch requires a non-shadow texel-fetchable sampled texture resource (target slang) [project.translate.slang-lowering-unsupported]`: `texel-buffer`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: pointer declaration: 'main.p' points into thread memory, and Slang defines no pointer to a local variable (Slang User's Guide, "Pointers (limited)") (target slang) [project.translate.slang-lowering-unsupported]`: `pointer-local`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N constructs: pointer declaration: 'main.p' points into thread memory, and Slang defines no pointer to a local variable (Slang User's Guide, "Pointers (limited)"); pointer declaration: 'main.q' points into thread memory, and Slang defines no pointer to a local variable (Slang User`: `pointer-arithmetic`
- `project.translate.slang-refused: SlangRefusal: Slang geometry stage must declare at most one stream output parameter`: `geometry-streams`
- `project.translate.slang-shader-record-buffer-unsupported: ShaderRecordBufferUnsupportedError: shader record buffer 'record' (GL_EXT_ray_tracing shaderRecordEXT) cannot be read on slang: the target has no shader binding table (target slang) [project.translate.slang-shader-record-buffer-unsupported]`: `ray-shader-record`
- `project.translate.undeclared-function: UndeclaredFunctionError: function 'Tuple' is not declared: it is neither a CrossGL built-in function nor a function, structure method, type or callable value of the program (target slang) [project.translate.undeclared-function]`: `concat`
- `project.translate.workgroup-uniform-load-unsupported: WorkgroupUniformLoadError: workgroupUniformLoad: '<probe>' is not a shared variable declared at program or stage scope for slang (target slang) [project.translate.workgroup-uniform-load-unsupported]`: `workgroupUniformLoad`

Untested, by reason:

- `needs the OptiX SDK headers, which the CUDA toolkit does not include` (8): `GetInstanceTraversable`, `GetTransformListHandle`, `GetTransformListSize`, `GetTraversableChild`, `GetTraversableInstanceId`, `GetTraversableObjectToWorld`, `GetTraversableTransformType`, `GetTraversableWorldToObject`
- `the probe itself is rejected: error: slangc exited with status -11 and no message`: `createDynamicObject`

### Input

Refused, by diagnostic:

- `project.translate.undeclared-function: UndeclaredFunctionError: function '<feature>' is not declared: it is neither a CrossGL built-in function nor a function, structure method, type or callable value of the program (target slang) [project.translate.undeclared-function]` (52): `EvaluateAttributeAtCentroid`, `GetClusterID`, `GetLssPositionsAndRadii`, `GetSpherePositionAndRadius`, `HitTriangleVertexPosition`, `IsLssHit`, `IsSphereHit`, `RayCurrentTime`, `ReorderThread`, `ReportHitOptix`, `TraceMotionRay`, `bit_cast`, `coopVecLoad`, `coopVecLoadCoherent`, `coopVecLoadGroupshared`, `copysign_double`, `copysign_float`, `copysign_half`, `debugBreak`, `defaultGetDescriptorFromHandle`, `f32tof16_`, `floatCast`, `getDescriptorFromDescriptorHeapEXT`, `getDescriptorFromDynamicResourceHeap`, `getDescriptorFromExplicitHeapIndex`, `getStringHash`, `loadAligned`, `makeTuple`, `nonuniform`, `packInt4x8`, `packInt4x8Clamp`, `packUint4x8`, `packUint4x8Clamp`, `reinterpret`, `storeAligned`, `unmodified`, `unpackHalf2x16ToFloat`, `unpackHalf2x16ToHalf`, `unpackInt4x8ToInt16`, `unpackInt4x8ToInt32`, `unpackSnorm2x16ToFloat`, `unpackSnorm2x16ToHalf`, `unpackSnorm4x8ToFloat`, `unpackSnorm4x8ToHalf`, `unpackUint4x8ToUint16`, `unpackUint4x8ToUint32`, `unpackUnorm2x16ToFloat`, `unpackUnorm2x16ToHalf`, `unpackUnorm4x8ToFloat`, `unpackUnorm4x8ToHalf`, `unused`, `usesNativeSpirvDescriptorHandle`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: call to <feature>: <feature> is a built-in function of another language, and Slang declares no function of that name (target slang) [project.translate.slang-lowering-unsupported]` (21): `bitfieldExtract`, `bitfieldInsert`, `copysign`, `divide`, `fabs`, `fdim`, `fmax`, `fmax3`, `fmedian3`, `fmin`, `fmin3`, `max3`, `median3`, `min3`, `nextafter`, `packHalf2x16`, `packSnorm2x16`, `packSnorm4x8`, `packUnorm2x16`, `packUnorm4x8`, `rint`
- `project.translate.undeclared-function: UndeclaredFunctionError: function 'CoopVec' is not declared: it is neither a CrossGL built-in function nor a function, structure method, type or callable value of the program (target slang) [project.translate.undeclared-function]` (6): `coopVecMatMul`, `coopVecMatMulAdd`, `coopVecMatMulAddPacked`, `coopVecMatMulPacked`, `coopVecOuterProductAccumulate`, `coopVecReduceSumAccumulate`
- `project.translate.slang-import-unsupported: SlangImportRefused: CrossGL cannot represent N Slang construct: Slang <feature> has no CrossGL atomic operation (target cgl) [project.translate.slang-import-unsupported]` (4): `InterlockedAddF16Emulated`, `InterlockedAddF16x2`, `InterlockedCompareExchangeFloatBitwise`, `InterlockedCompareStoreFloatBitwise`
- `project.translate.slang-metal-math-function-unsupported: MetalMathFunctionUnsupportedError: <feature> is exact at integers and half-integers, which slang has no function for, and CrossTL does not lower it with an exact range reduction yet (target slang) [project.translate.slang-metal-math-function-unsupported]` (3): `cospi`, `sinpi`, `tanpi`
- `project.translate.crossgl-function-body-parse-failed: CrossGLFunctionBodyParseError: CrossGL could not parse the body of function '<probe>' at IDENTIFIER 'b': Expected SEMICOLON, got IDENTIFIER 'b'`: `multi-variable-loop`
- `project.translate.crossgl-syntax-error: CrossGLSyntaxError: Expected a structure name after 'struct', got MATCH 'match'`: `reserved-type-name`
- `project.translate.member-placement-unsupported: MemberPlacementError: constant buffer 'pc': the members of struct 'Constants' carry @offset or @align, and Slang declares a push-constant ConstantBuffer<T> with std430 offsets only (target slang) [project.translate.member-placement-unsupported]`: `push-constant-offset`
- `project.translate.slang-import-unsupported: SlangImportRefused: CrossGL cannot represent N Slang construct: numthreads x dimension size depends on specialization constant size; CrossGL fixes the workgroup size at translation time (target cgl) [project.translate.slang-import-unsupported]`: `specialization-workgroup-size`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: pointer declaration: 'main.p' points into thread memory, and Slang defines no pointer to a local variable (Slang User's Guide, "Pointers (limited)") (target slang) [project.translate.slang-lowering-unsupported]`: `pointer-local`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N constructs: pointer declaration: 'main.p' points into thread memory, and Slang defines no pointer to a local variable (Slang User's Guide, "Pointers (limited)"); pointer declaration: 'main.q' points into thread memory, and Slang defines no pointer to a local variable (Slang User`: `pointer-arithmetic`
- `project.translate.slang-refused: SlangRefusal: Slang geometry stage must declare at most one stream output parameter`: `geometry-streams`
- `project.translate.slang-shader-record-buffer-unsupported: ShaderRecordBufferUnsupportedError: shader record buffer 'record' (GL_EXT_ray_tracing shaderRecordEXT) cannot be read on slang: the target has no shader binding table (target slang) [project.translate.slang-shader-record-buffer-unsupported]`: `ray-shader-record`
- `project.translate.slang-syntax-error: SlangSyntaxError: Expected SEMICOLON, got LBRACKET`: `array-return`
- `project.translate.undeclared-function: UndeclaredFunctionError: function 'Tuple' is not declared: it is neither a CrossGL built-in function nor a function, structure method, type or callable value of the program (target slang) [project.translate.undeclared-function]`: `concat`
- `project.translate.undeclared-type: UndeclaredTypeError: type 'T' is not declared: it is neither a CrossGL built-in type nor a structure, enumeration, type alias or generic parameter of the program (target slang) [project.translate.undeclared-type]`: `generic-function`
- `project.translate.workgroup-uniform-load-unsupported: WorkgroupUniformLoadError: workgroupUniformLoad: '<probe>' is not a shared variable declared at program or stage scope for slang (target slang) [project.translate.workgroup-uniform-load-unsupported]`: `workgroupUniformLoad`

Untested, by reason:

- `needs the OptiX SDK headers, which the CUDA toolkit does not include` (8): `GetInstanceTraversable`, `GetTransformListHandle`, `GetTransformListSize`, `GetTraversableChild`, `GetTraversableInstanceId`, `GetTraversableObjectToWorld`, `GetTraversableTransformType`, `GetTraversableWorldToObject`
- `the probe itself is rejected: error: slangc exited with status -11 and no message`: `createDynamicObject`
