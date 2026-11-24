# CrossTL translation matrix: HLSL to CUDA

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native HLSL probe whose feature CUDA has too straight to CUDA, and nvcc checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 95.4 %: 229 supported, 7 refused, 4 wrong, 0 untested.

## Gaps

<details>
<summary>11 gaps: 7 refused, 4 wrong</summary>

Wrong, by cause:

- `identifier "<feature>" is undefined` (2): `int16`, `uint16`
- `"t" has already been declared in the current scope`: `switch-case-scope`
- `no instance of overloaded function "fmod" matches the argument list`: `fmod`

Refused, by diagnostic:

- `project.translate.rule-inexpressible: RuleInexpressibleError: the signed ++ used as a value cannot be rewritten with wrapping arithmetic for cuda, whose code generator passes inout parameters by value; write it as a separate statement (target cuda) [project.translate.rule-inexpressible]` (5): `comma-operator`, `condition-assignment`, `increment-decrement`, `increment-in-index`, `lvalue-increment`
- `project.translate.cuda-lowering-unsupported: CudaLoweringRefused: CUDA cannot lower N construct: function: call to '<feature>', a built-in function of another shading language that CUDA does not define and the program does not declare (target cuda) [project.translate.cuda-lowering-unsupported]` (2): `InterlockedCompareExchangeFloatBitwise`, `InterlockedCompareStoreFloatBitwise`

</details>
