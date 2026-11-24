# CrossTL translation matrix: HLSL to HIP

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native HLSL probe whose feature HIP has too straight to HIP, and hipcc checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 95.4 %: 230 supported, 7 refused, 4 wrong, 0 untested.

## Gaps

<details>
<summary>11 gaps: 7 refused, 4 wrong</summary>

Wrong, by cause:

- `no matching function for call to 'fmod'`: `fmod`
- `redefinition of 't'`: `switch-case-scope`
- `use of undeclared identifier 'int16'; did you mean 'int1'?`: `int16`
- `use of undeclared identifier 'uint16'; did you mean 'uint1'?`: `uint16`

Refused, by diagnostic:

- `project.translate.rule-inexpressible: RuleInexpressibleError: the signed ++ used as a value cannot be rewritten with wrapping arithmetic for hip, whose code generator passes inout parameters by value; write it as a separate statement (target hip) [project.translate.rule-inexpressible]` (5): `comma-operator`, `condition-assignment`, `increment-decrement`, `increment-in-index`, `lvalue-increment`
- `project.translate.hip-lowering-unsupported: HipLoweringRefused: HIP cannot lower N construct: function: call to '<feature>', a built-in function of another shading language that HIP does not define and the program does not declare (target hip) [project.translate.hip-lowering-unsupported]` (2): `InterlockedCompareExchangeFloatBitwise`, `InterlockedCompareStoreFloatBitwise`

</details>
