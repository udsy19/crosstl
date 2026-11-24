# CrossTL translation matrix: CUDA to Rust

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native CUDA probe whose feature Rust has too straight to Rust, and rust-gpu checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 66.8 %: 173 supported, 59 refused, 27 wrong, 2 untested.

## Gaps

<details>
<summary>86 gaps: 59 refused, 27 wrong</summary>

Wrong, by cause:

- `error[E0308]: mismatched types` (5): `constant-expression`, `constant-struct`, `constant-vector-array`, `struct-constructor`, `zero-initializer`
- `GLSL.std.N Exp: expected Result Type to be a N or N-bit scalar or vector float type` (2): `exp`, `expm1`
- `GLSL.std.N Log: expected Result Type to be a N or N-bit scalar or vector float type` (2): `log`, `log1p`
- `error[E0425]: cannot find type 'ptr' in this scope` (2): `buffer-in-helper`, `pointer-local`
- `GLSL.std.N Acos: expected Result Type to be a N or N-bit scalar or vector float type`: `acos`
- `GLSL.std.N Acosh: expected Result Type to be a N or N-bit scalar or vector float type`: `acosh`
- `GLSL.std.N Asin: expected Result Type to be a N or N-bit scalar or vector float type`: `asin`
- `GLSL.std.N Asinh: expected Result Type to be a N or N-bit scalar or vector float type`: `asinh`
- `GLSL.std.N Atan2: expected Result Type to be a N or N-bit scalar or vector float type`: `atan2`
- `GLSL.std.N Atan: expected Result Type to be a N or N-bit scalar or vector float type`: `atan`
- `GLSL.std.N Atanh: expected Result Type to be a N or N-bit scalar or vector float type`: `atanh`
- `GLSL.std.N Cosh: expected Result Type to be a N or N-bit scalar or vector float type`: `cosh`
- `GLSL.std.N Exp2: expected Result Type to be a N or N-bit scalar or vector float type`: `exp2`
- `GLSL.std.N Log2: expected Result Type to be a N or N-bit scalar or vector float type`: `log2`
- `GLSL.std.N Pow: expected Result Type to be a N or N-bit scalar or vector float type`: `pow`
- `GLSL.std.N Sinh: expected Result Type to be a N or N-bit scalar or vector float type`: `sinh`
- `GLSL.std.N Tan: expected Result Type to be a N or N-bit scalar or vector float type`: `tan`
- `GLSL.std.N Tanh: expected Result Type to be a N or N-bit scalar or vector float type`: `tanh`
- `error[E0425]: cannot find value 'Low' in this scope`: `enum-constant`
- `the translation loses BuiltIn.SubgroupSize`: `subgroup-size`

Refused, by diagnostic:

- `project.translate.rust-lowering-unsupported: RustLoweringRefused: Rust cannot lower N construct: resource: constant buffers are not lowered to rust-gpu uniform blocks (target rust) [project.translate.rust-lowering-unsupported]` (17): `uniform-array`, `uniform-bool`, `uniform-buffer`, `uniform-cbuffer-vector`, `uniform-in-helper`, `uniform-integer`, `uniform-integer-vector`, `uniform-members`, `uniform-std140-array`, `uniform-std140-vector`, `uniform-struct`, `uniform-struct-array`, `uniform-struct-copy`, `uniform-unsigned`, `uniform-vector`, `uniform-vector-array`, `uniform-vector-packing`
- `project.translate.rust-refused: RustRefusal: Rust compute stage needs a workgroup size: rust-gpu takes it as literals` (9): `barrier-in-loop`, `local-invocation-id`, `num-workgroups`, `shared-2d-array`, `shared-memory`, `shared-memory-in-helper`, `shared-struct-array`, `shared-vector-array`, `workgroup-id`
- `project.translate.rust-lowering-unsupported: RustLoweringRefused: Rust cannot lower N construct: function: '<feature>' has no rust-gpu lowering for these operands (target rust) [project.translate.rust-lowering-unsupported]` (7): `__isnanf`, `acoshf`, `asinhf`, `atanhf`, `copysignf`, `expm1f`, `log1pf`
- `project.translate.rust-lowering-unsupported: RustLoweringRefused: Rust cannot lower N constructs: stage: compute entry parameter 'tex' is not a compute built-in input; function: 'textureLod' has no rust-gpu lowering for these operands (target rust) [project.translate.rust-lowering-unsupported]` (7): `sampled-texture`, `texture-1d`, `texture-1d-array`, `texture-2d-array`, `texture-3d`, `texture-cube`, `texture-cube-array`
- `project.translate.rust-lowering-unsupported: RustLoweringRefused: Rust cannot lower N constructs: stage: compute entry parameter 'img' is not a compute built-in input; function: 'imageStore' has no rust-gpu lowering for these operands (target rust) [project.translate.rust-lowering-unsupported]` (6): `integer-storage-image`, `storage-image`, `storage-image-1d`, `storage-image-3d`, `storage-image-array`, `unorm-storage-image`
- `project.translate.rust-lowering-unsupported: RustLoweringRefused: Rust cannot lower N constructs: built-in: '<feature>' is used by name, and the rust-gpu output binds no entry-point parameter for it; generation then failed: Rust compute stage needs a workgroup size: rust-gpu takes it as literals (target rust) [project.translate.rust-lowering-unsupported]` (4): `local-invocation-index`, `num-subgroups`, `subgroup-id`, `subgroup-invocation-id`
- `project.translate.rule-inexpressible: RuleInexpressibleError: __cgl_libm_sin on a N-bit floating-point operand has no helper for rust: the helper takes binary32 values only (target rust) [project.translate.rule-inexpressible]` (2): `sin`, `sincos`
- `project.translate.rust-lowering-unsupported: RustLoweringRefused: Rust cannot lower N constructs: function: 'textureLod' has no rust-gpu lowering for these operands; stage: compute entry parameter 'tex' is not a compute built-in input (target rust) [project.translate.rust-lowering-unsupported]` (2): `texture-argument`, `texture-in-helper`
- `project.translate.rule-inexpressible: RuleInexpressibleError: __cgl_libm_cos on a N-bit floating-point operand has no helper for rust: the helper takes binary32 values only (target rust) [project.translate.rule-inexpressible]`: `cos`
- `project.translate.rule-inexpressible: RuleInexpressibleError: __cgl_round_away on a N-bit floating-point operand has no helper for rust: the helper takes binary32 values only (target rust) [project.translate.rule-inexpressible]`: `round`
- `project.translate.rust-lowering-unsupported: RustLoweringRefused: Rust cannot lower N constructs: stage: compute entry parameter 'tex' is not a compute built-in input; function: 'texelFetch' has no rust-gpu lowering for these operands (target rust) [project.translate.rust-lowering-unsupported]`: `texel-buffer`
- `project.translate.rust-refused: RustRefusal: Rust struct 'Bits' has a @union_layout: the Rust generator has no union lowering, and a struct would give its overlapping members separate storage`: `union`
- `project.translate.undeclared-function: UndeclaredFunctionError: function 'surf2Dread' is not declared: it is neither a CrossGL built-in function nor a function, structure method, type or callable value of the program (target rust) [project.translate.undeclared-function]`: `read-write-image`

</details>

<details>
<summary>2 untested: function 2</summary>

- `the target's own probe is rejected: error: Hypot not supported yet` (2): `hypot`, `hypotf`

</details>
