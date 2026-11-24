# CrossTL translation matrix: GLSL to HIP

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native GLSL probe whose feature HIP has too straight to HIP, and hipcc checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 95.9 %: 235 supported, 5 refused, 5 wrong, 0 untested.

## Gaps

<details>
<summary>10 gaps: 5 refused, 5 wrong</summary>

Wrong, by cause:

- `no matching function for call to '<feature>'` (3): `acosh`, `asinh`, `atanh`
- `no viable conversion from 'HIP_vector_type<unsigned int, [...]>' to 'HIP_vector_type<int, [...]>'`: `bitCount`
- `use of undeclared identifier 'float16_t'; did you mean 'float_t'?`: `half`

Refused, by diagnostic:

- `project.translate.rule-inexpressible: RuleInexpressibleError: the signed ++ used as a value cannot be rewritten with wrapping arithmetic for hip, whose code generator passes inout parameters by value; write it as a separate statement (target hip) [project.translate.rule-inexpressible]` (5): `comma-operator`, `condition-assignment`, `increment-decrement`, `increment-in-index`, `lvalue-increment`

</details>
