# CrossTL translation matrix: SPIR-V to GLSL ES

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native SPIR-V probe whose feature GLSL ES has too straight to GLSL ES, and glslangValidator checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 56.6 %: 257 supported, 8 refused, 189 wrong, 9 untested.

## Gaps

<details>
<summary>197 gaps: 8 refused, 189 wrong</summary>

Wrong, by cause:

- `'+' : wrong operand types: no operation '+' exists that takes a left-hand operand of type ' temp highp uint' and a right operand of type ' const int' (or there is no acceptable conversion)` (109): `Acos`, `Acosh`, `Asin`, `Asinh`, `Atan2`, `Atanh`, `Ceil`, `Cos`, `Cosh`, `Cross`, `Degrees`, `Determinant`, `Distance`, `Exp`, `Exp2`, `FAbs`, `FClamp`, `FMax`, `FMin`, `FMix`, `FSign`, `FaceForward`, `FindILsb`, `FindSMsb`, `Floor`, `Fma`, `Fract`, `FrexpStruct`, `InverseSqrt`, `Ldexp`, `Length`, `Log`, `Log2`, `MatrixInverse`, `ModfStruct`, `Normalize`, `OpAll`, `OpAny`, `OpAtomicAnd`, `OpAtomicCompareExchange`, `OpAtomicExchange`, `OpAtomicIAdd`, `OpAtomicOr`, `OpAtomicUMax`, `OpAtomicUMin`, `OpAtomicXor`, `OpBitCount`, `OpBitFieldInsert`, `OpBitFieldSExtract`, `OpBitReverse`, `OpBitcast`, `OpDot`, `OpFMod`, `OpFOrdEqual`, `OpFOrdGreaterThan`, `OpFOrdGreaterThanEqual`, `OpFOrdLessThan`, `OpFOrdLessThanEqual`, `OpFUnordNotEqual`, `OpGroupNonUniformBroadcast`, `OpGroupNonUniformQuadBroadcast`, `OpGroupNonUniformQuadSwap`, `OpGroupNonUniformRotateKHR`, `OpGroupNonUniformShuffle`, `OpGroupNonUniformShuffleDown`, `OpGroupNonUniformShuffleUp`, `OpGroupNonUniformShuffleXor`, `OpIAddCarry`, `OpISubBorrow`, `OpImageFetch`, `OpImageGather`, `OpImageQuerySizeLod`, `OpImageSampleExplicitLod`, `OpImageSampleProjExplicitLod`, `OpIsInf`, `OpIsNan`, `OpLogicalNot`, `OpOuterProduct`, `OpSMulExtended`, `OpTranspose`, `OpUMulExtended`, `PackHalf2x16`, `PackSnorm2x16`, `PackSnorm4x8`, `PackUnorm2x16`, `PackUnorm4x8`, `Pow`, `Radians`, `Reflect`, `Refract`, `Round`, `RoundEven`, `Sin`, `Sinh`, `SmoothStep`, `Sqrt`, `Step`, `Tan`, `Tanh`, `Trunc`, `UnpackHalf2x16`, `UnpackSnorm2x16`, `UnpackSnorm4x8`, `UnpackUnorm2x16`, `UnpackUnorm4x8`, `unsigned-division`, `unsigned-negation`, `unsigned-wraparound`, `vector-shift`
- `'%' : wrong operand types: no operation '%' exists that takes a left-hand operand of type ' temp highp uint' and a right operand of type ' const int' (or there is no acceptable conversion)` (23): `OpGroupNonUniformAll`, `OpGroupNonUniformAllEqual`, `OpGroupNonUniformAny`, `OpGroupNonUniformBallot`, `OpGroupNonUniformBallotBitCount`, `OpGroupNonUniformBallotBitExtract`, `OpGroupNonUniformBallotFindLSB`, `OpGroupNonUniformBallotFindMSB`, `OpGroupNonUniformBitwiseAnd`, `OpGroupNonUniformBitwiseOr`, `OpGroupNonUniformBitwiseXor`, `OpGroupNonUniformBroadcastFirst`, `OpGroupNonUniformFAdd`, `OpGroupNonUniformFMax`, `OpGroupNonUniformFMin`, `OpGroupNonUniformFMul`, `OpGroupNonUniformInverseBallot`, `OpGroupNonUniformQuadAllKHR`, `OpGroupNonUniformQuadAnyKHR`, `OpSubgroupAllEqualKHR`, `OpSubgroupAllKHR`, `OpSubgroupAnyKHR`, `unsigned-switch`
- `'<feature>' : block redeclaration has extra members` (17): `geometry`, `geometry-input-lines`, `geometry-input-lines-adjacency`, `geometry-input-triangles`, `geometry-input-triangles-adjacency`, `geometry-invocations`, `geometry-output-line-strip`, `geometry-output-triangle-strip`, `tessellation-domain-isolines`, `tessellation-domain-quads`, `tessellation-evaluation`, `tessellation-level-input`, `tessellation-patch-input`, `tessellation-point-mode`, `tessellation-spacing-fractional-even`, `tessellation-spacing-fractional-odd`, `tessellation-winding-cw`
- `'assign' : cannot convert from ' const int' to ' temp highp uint'` (13): `InterpolateAtCentroid`, `InterpolateAtOffset`, `InterpolateAtSample`, `OpDPdx`, `OpDPdy`, `OpEmitVertex`, `OpEndPrimitive`, `OpFwidth`, `OpImageSampleImplicitLod`, `OpImageSampleProjImplicitLod`, `for-loop-variants`, `implicit-conversion`, `sibling-redeclaration`
- `'vertex output block' : not supported for this version or the enabled extensions` (5): `instance-index`, `invariant-position`, `point-size`, `vertex`, `vertex-index`
- `'<feature>' : required extension not requested: GL_OES_sample_variables` (3): `sample-index`, `sample-mask`, `sample-mask-input`
- `'*' : wrong operand types: no operation '*' exists that takes a left-hand operand of type ' temp highp uint' and a right operand of type ' const int' (or there is no acceptable conversion)` (2): `bool-vector-conversion`, `unsigned-buffer`
- `'+' : wrong operand types: no operation '+' exists that takes a left-hand operand of type ' const int' and a right operand of type ' temp highp uint' (or there is no acceptable conversion)` (2): `literal-suffixes`, `octal-literal`
- `'<feature>' : required extension not requested: Possible extensions include:` (2): `layer`, `primitive-id`
- `'rgba32f' : format requires readonly or writeonly memory qualifier` (2): `OpImageRead`, `OpImageWrite`
- `'!=' : wrong operand types: no operation '!=' exists that takes a left-hand operand of type 'layout( column_major std140 offset=N) temp highp uint' and a right operand of type ' const int' (or there is no acceptable conversion)`: `uniform-bool-vector`
- `'!=' : wrong operand types: no operation '!=' exists that takes a left-hand operand of type 'layout( column_major std140 offset=N) uniform highp uint' and a right operand of type ' const int' (or there is no acceptable conversion)`: `uniform-bool`
- `'%' : wrong operand types: no operation '%' exists that takes a left-hand operand of type 'layout( column_major std140 offset=N) uniform highp uint' and a right operand of type ' const int' (or there is no acceptable conversion)`: `uniform-unsigned`
- `'&' : wrong operand types: no operation '&' exists that takes a left-hand operand of type ' const int' and a right operand of type ' temp highp uint' (or there is no acceptable conversion)`: `numeric-literals`
- `'&' : wrong operand types: no operation '&' exists that takes a left-hand operand of type ' temp highp uint' and a right operand of type ' const int' (or there is no acceptable conversion)`: `unsigned-countdown`
- `'<' : wrong operand types: no operation '<' exists that takes a left-hand operand of type ' temp highp uint' and a right operand of type ' const int' (or there is no acceptable conversion)`: `unsigned-comparison`
- `'gl_BaryCoordEXT' : undeclared identifier`: `barycentric-coordinate`
- `'noperspective' : Reserved word.`: `noperspective-interpolation`
- `'sample' : Reserved word.`: `sample-interpolation`
- `'variable indexing sampler array' : not supported for this version or the enabled extensions`: `array-of-textures-loop-index`
- `'|' : wrong operand types: no operation '|' exists that takes a left-hand operand of type ' temp highp uint' and a right operand of type ' const int' (or there is no acceptable conversion)`: `vector-bitwise`

Refused, by diagnostic:

- `project.translate.opengl-unsized-array-unsupported: UnsizedArrayUnsupportedError: unsized array 'B0.fin' is a struct member: only a storage buffer's last member or an array of resources may omit its element count (HLSL allows unsized arrays only for resources, MSL array bounds are constant expressions, and GLSL and WGSL allow runtime-sized arrays only as the last member of a stor` (4): `OpControlBarrier`, `OpGroupNonUniformElect`, `OpImageQuerySize`, `OpMemoryBarrier`
- `project.translate.opengl-lowering-unsupported: OpenGLLoweringRefused: OpenGL cannot lower N constructs: GLSL version requirement: type 'double' does not exist in GLSL ES; the target is #version N es; GLSL version requirement: type 'dvec2' does not exist in GLSL ES; the target is #version N es; GLSL version requirement: type 'dvec3' does not exist in GLSL ES; the t`: `OpGroupNonUniformPartitionEXT`
- `project.translate.opengl-refused: OpenGLRefusal: OpenGL target profile '#version N es' does not support GL_ARB_gpu_shader_int64; select a desktop GLSL profile for N-bit integer values`: `integer-literal-limits`
- `project.translate.opengl-refused: OpenGLRefusal: OpenGL texture operation 'textureLod' requires a declared texture or image resource argument: FunctionCallNode(function=IdentifierNode(name=nonuniformEXT), arguments=N)`: `array-of-textures-nonuniform-index`
- `project.translate.opengl-scalar-conversion-unsupported: OpenGLScalarConversionError: OpenGL cannot preserve source conversion from 'half' to 'half': half unsupported profile`: `half`

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
