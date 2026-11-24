# CrossTL translation matrix: HIP to Mojo

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native HIP probe whose feature Mojo has too straight to Mojo, and mojo checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 84.9 %: 231 supported, 31 refused, 10 wrong, 0 untested.

## Gaps

<details>
<summary>41 gaps: 31 refused, 10 wrong</summary>

Wrong, by cause:

- `cannot implicitly convert 'StaticTuple[Float32, Int(N)]' value to 'Pair'` (3): `constant-struct`, `struct-constructor`, `zero-initializer`
- `use of unknown declaration '<feature>'` (2): `__isinff`, `__isnanf`
- `cannot implicitly convert 'Int32' value to 'UInt32'`: `__popc`
- `no matching function in call to 'power'`: `pow`
- `no matching function in initialization`: `constant-vector-array`
- `use of unknown declaration '__lane_id'`: `subgroup-invocation-id`
- `use of unknown declaration 'ptr'`: `buffer-in-helper`

Refused, by diagnostic:

- `project.translate.mojo-lowering-unsupported: MojoLoweringRefused: Mojo cannot lower N construct: function: call to '<feature>', a built-in function of another shading language that Mojo does not define and the program does not declare (target mojo) [project.translate.mojo-lowering-unsupported]` (20): `cbrtf`, `copysignf`, `erfcf`, `erff`, `expm1f`, `hypotf`, `j0f`, `j1f`, `ldexpf`, `lgammaf`, `log10f`, `log1pf`, `logbf`, `nan`, `nanf`, `nextafterf`, `remainderf`, `tgammaf`, `y0f`, `y1f`
- `project.translate.mojo-refused: MojoRefusal: Unsupported <feature> for Mojo codegen; scalar integer target required: i32` (3): `atomicAdd`, `atomicMax`, `atomicMin`
- `project.translate.mojo-refused: MojoRefusal: Mojo dereference: operand of type ptr<f32> is not a pointer, and Mojo dereferences only a pointer, with p[]` (2): `pointer-arithmetic`, `pointer-local`
- `project.translate.hip-record-semantics-unsupported: HipRecordSemanticError: HIP record method call 'width' is unsupported for record 'Span' in call expression`: `struct-method`
- `project.translate.mojo-lowering-unsupported: MojoLoweringRefused: Mojo cannot lower N construct: function: call to 'sign', a built-in function of another shading language that Mojo does not define and the program does not declare (target mojo) [project.translate.mojo-lowering-unsupported]`: `roundf`
- `project.translate.mojo-refused: MojoRefusal: Mojo has no global variables, so a variable declared outside a function (tile: f32[N]) has no Mojo spelling; only uniform values and storage buffers of a runtime-sized array, which become kernel arguments, private variables, which become kernel locals, and constants can be declared there`: `shared-memory-in-helper`
- `project.translate.rule-inexpressible: RuleInexpressibleError: __cgl_libm_cos on a N-bit floating-point operand has no helper for mojo: the helper takes binary32 values only (target mojo) [project.translate.rule-inexpressible]`: `cos`
- `project.translate.rule-inexpressible: RuleInexpressibleError: __cgl_libm_sin on a N-bit floating-point operand has no helper for mojo: the helper takes binary32 values only (target mojo) [project.translate.rule-inexpressible]`: `sin`
- `project.translate.rule-inexpressible: RuleInexpressibleError: __cgl_round_away on a N-bit floating-point operand has no helper for mojo: the helper takes binary32 values only (target mojo) [project.translate.rule-inexpressible]`: `round`

</details>
