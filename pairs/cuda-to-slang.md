# CrossTL translation matrix: CUDA to Slang

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native CUDA probe whose feature Slang has too straight to Slang, and slangc checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 83.0 %: 239 supported, 24 refused, 25 wrong, 0 untested.

## Gaps

<details>
<summary>49 gaps: 24 refused, 25 wrong</summary>

Wrong, by cause:

- `error[E30015]: undefined identifier '<feature>'` (3): `__isinff`, `__isnanf`, `invocation-id-in-helper`
- `error[E30015]: undefined identifier 'cudaTextureObject_t'` (2): `texture-argument`, `texture-in-helper`
- `line N: GLSL.std.N Acos: expected Result Type to be a N or N-bit scalar or vector float type`: `acos`
- `line N: GLSL.std.N Acosh: expected Result Type to be a N or N-bit scalar or vector float type`: `acosh`
- `line N: GLSL.std.N Asin: expected Result Type to be a N or N-bit scalar or vector float type`: `asin`
- `line N: GLSL.std.N Asinh: expected Result Type to be a N or N-bit scalar or vector float type`: `asinh`
- `line N: GLSL.std.N Atan2: expected Result Type to be a N or N-bit scalar or vector float type`: `atan2`
- `line N: GLSL.std.N Atan: expected Result Type to be a N or N-bit scalar or vector float type`: `atan`
- `line N: GLSL.std.N Atanh: expected Result Type to be a N or N-bit scalar or vector float type`: `atanh`
- `line N: GLSL.std.N Cosh: expected Result Type to be a N or N-bit scalar or vector float type`: `cosh`
- `line N: GLSL.std.N Exp: expected Result Type to be a N or N-bit scalar or vector float type`: `exp`
- `line N: GLSL.std.N Log2: expected Result Type to be a N or N-bit scalar or vector float type`: `log2`
- `line N: GLSL.std.N Log: expected Result Type to be a N or N-bit scalar or vector float type`: `log`
- `line N: GLSL.std.N Pow: expected Result Type to be a N or N-bit scalar or vector float type`: `pow`
- `line N: GLSL.std.N Sinh: expected Result Type to be a N or N-bit scalar or vector float type`: `sinh`
- `line N: GLSL.std.N Tan: expected Result Type to be a N or N-bit scalar or vector float type`: `tan`
- `line N: GLSL.std.N Tanh: expected Result Type to be a N or N-bit scalar or vector float type`: `tanh`
- `error[E30015]: undefined identifier 'Low'`: `enum-constant`
- `the translation loses BuiltIn.SubgroupSize`: `subgroup-size`
- `the translation loses Dim.Buffer, Capability.SampledBuffer`: `texel-buffer`
- `the translation loses ImageFormat.R32ui`: `integer-storage-image`
- `the translation loses ImageFormat.Rgba8`: `unorm-storage-image`

Refused, by diagnostic:

- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: call to <feature>: <feature> is a built-in function of another language, and Slang declares no function of that name (target slang) [project.translate.slang-lowering-unsupported]` (12): `acoshf`, `asinhf`, `atanhf`, `cospif`, `exp10f`, `fdim`, `fdimf`, `fmax`, `fmin`, `nextafter`, `nextafterf`, `sinpif`
- `project.translate.rule-inexpressible: RuleInexpressibleError: __cgl_libm_sin on a N-bit floating-point operand has no helper for slang: the helper takes binary32 values only (target slang) [project.translate.rule-inexpressible]` (2): `sin`, `sincos`
- `project.translate.slang-metal-math-function-unsupported: MetalMathFunctionUnsupportedError: <feature> is exact at integers and half-integers, which slang has no function for, and CrossTL does not lower it with an exact range reduction yet (target slang) [project.translate.slang-metal-math-function-unsupported]` (2): `cospi`, `sinpi`
- `project.translate.rule-inexpressible: RuleInexpressibleError: __cgl_libm_cos on a N-bit floating-point operand has no helper for slang: the helper takes binary32 values only (target slang) [project.translate.rule-inexpressible]`: `cos`
- `project.translate.rule-inexpressible: RuleInexpressibleError: __cgl_round_away on a N-bit floating-point operand has no helper for slang: the helper takes binary32 values only (target slang) [project.translate.rule-inexpressible]`: `round`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: call to fmax: fmax is a built-in function of another language, and Slang declares no function of that name (target slang) [project.translate.slang-lowering-unsupported]`: `fmaxf`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: call to fmin: fmin is a built-in function of another language, and Slang declares no function of that name (target slang) [project.translate.slang-lowering-unsupported]`: `fminf`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N construct: pointer declaration: 'probe.p' points into device memory, and a bound Slang buffer has no device address (Slang User's Guide, "Pointers (limited)") (target slang) [project.translate.slang-lowering-unsupported]`: `pointer-local`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N constructs: pointer declaration: 'fetch.iin' points into device memory, and a bound Slang buffer has no device address (Slang User's Guide, "Pointers (limited)"); pointer declaration: 'put.outp' points into device memory, and a bound Slang buffer has no device address (Slang Use`: `buffer-in-helper`
- `project.translate.slang-lowering-unsupported: SlangLoweringRefused: Slang cannot lower N constructs: pointer declaration: 'probe.p' points into device memory, and a bound Slang buffer has no device address (Slang User's Guide, "Pointers (limited)"); pointer declaration: 'probe.q' points into device memory, and a bound Slang buffer has no device address (Slang User's`: `pointer-arithmetic`
- `project.translate.undeclared-function: UndeclaredFunctionError: function 'surf2Dread' is not declared: it is neither a CrossGL built-in function nor a function, structure method, type or callable value of the program (target slang) [project.translate.undeclared-function]`: `read-write-image`

</details>
