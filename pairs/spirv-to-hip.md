# CrossTL translation matrix: SPIR-V to HIP

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native SPIR-V probe whose feature HIP has too straight to HIP, and hipcc checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 94.0 %: 235 supported, 0 refused, 15 wrong, 2 untested.

## Gaps

<details>
<summary>15 gaps: 0 refused, 15 wrong</summary>

Wrong, by cause:

- `array type 'float[N]' is not assignable` (4): `array-initializer`, `constant-array`, `reserved-global-name`, `zero-initializer`
- `reference to __host__ variable '<feature>' in __global__ function` (4): `num-subgroups`, `subgroup-id`, `subgroup-invocation-id`, `subgroup-size`
- `array type 'float2[N]' (aka 'HIP_vector_type<float, 2>[N]') is not assignable`: `constant-vector-array`
- `no matching function for call to 'acosh'`: `Acosh`
- `no matching function for call to 'asinh'`: `Asinh`
- `no matching function for call to 'atanh'`: `Atanh`
- `no matching function for call to 'fmax'`: `NMax`
- `no matching function for call to 'fmin'`: `NMin`
- `no viable overloaded '='`: `OpBitCount`

</details>

<details>
<summary>2 untested: type 2</summary>

- `slangc or spirv-dis is not installed` (2): `pointer-arithmetic`, `pointer-local`

</details>
