# CrossTL translation matrix: Metal to HIP

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native Metal probe whose feature HIP has too straight to HIP, and hipcc checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 86.6 %: 240 supported, 16 refused, 21 wrong, 0 untested.

## Gaps

<details>
<summary>37 gaps: 16 refused, 21 wrong</summary>

Wrong, by cause:

- `no matching function for call to '<feature>'` (12): `acosh`, `asinh`, `atanh`, `copysign`, `fabs`, `fdim`, `fmax`, `fmin`, `ilogb`, `log10`, `nextafter`, `rint`
- `no matching function for call to 'fmod'` (2): `float-remainder`, `fmod`
- `use of undeclared identifier 'int8'` (2): `int8`, `integer-promotion`
- `no matching function for call to 'make_float4'`: `zero-initializer`
- `no viable conversion from 'HIP_vector_type<unsigned int, [...]>' to 'HIP_vector_type<int, [...]>'`: `popcount`
- `use of undeclared identifier 'uint8'`: `uint8`
- `use of undeclared identifier 'int16'; did you mean 'int1'?`: `int16`
- `use of undeclared identifier 'uint16'; did you mean 'uint1'?`: `uint16`

Refused, by diagnostic:

- `project.translate.hip-lowering-unsupported: HipLoweringRefused: HIP cannot lower N construct: function: call to 'atomicThreadFence', a built-in function of another shading language that HIP does not define and the program does not declare (target hip) [project.translate.hip-lowering-unsupported]` (7): `atomic_exchange`, `atomic_fetch_add`, `atomic_fetch_and`, `atomic_fetch_max`, `atomic_fetch_min`, `atomic_fetch_or`, `atomic_fetch_xor`
- `project.translate.hip-lowering-unsupported: HipLoweringRefused: HIP cannot lower N construct: function: call to '<feature>', a built-in function of another shading language that HIP does not define and the program does not declare (target hip) [project.translate.hip-lowering-unsupported]` (2): `max3`, `min3`
- `project.translate.hip-lowering-unsupported: HipLoweringRefused: HIP cannot lower N construct: sincos: it takes N value and N output operands (target hip) [project.translate.hip-lowering-unsupported]`: `sincos`
- `project.translate.hip-lowering-unsupported: HipLoweringRefused: HIP cannot lower N construct: HIP structured buffer atomic: atomicMax on RWStructuredBuffer<uint64> requires supported scalar int/uint target (target hip) [project.translate.hip-lowering-unsupported]`: `atomic_max_explicit`
- `project.translate.hip-lowering-unsupported: HipLoweringRefused: HIP cannot lower N construct: HIP structured buffer atomic: atomicMin on RWStructuredBuffer<uint64> requires supported scalar int/uint target (target hip) [project.translate.hip-lowering-unsupported]`: `atomic_min_explicit`
- `project.translate.hip-lowering-unsupported: HipLoweringRefused: HIP cannot lower N construct: function: call to 'atomicCompareExchangeWeak', a built-in function of another shading language that HIP does not define and the program does not declare (target hip) [project.translate.hip-lowering-unsupported]`: `atomic_compare_exchange_weak_explicit`
- `project.translate.hip-lowering-unsupported: HipLoweringRefused: HIP cannot lower N constructs: HIP structured buffer atomic: atomicMax on RWStructuredBuffer<uint64> requires supported scalar int/uint target; function: call to 'atomicThreadFence', a built-in function of another shading language that HIP does not define and the program does not declare (target hip`: `atomic_max`
- `project.translate.hip-lowering-unsupported: HipLoweringRefused: HIP cannot lower N constructs: HIP structured buffer atomic: atomicMin on RWStructuredBuffer<uint64> requires supported scalar int/uint target; function: call to 'atomicThreadFence', a built-in function of another shading language that HIP does not define and the program does not declare (target hip`: `atomic_min`
- `project.translate.hip-lowering-unsupported: HipLoweringRefused: HIP cannot lower N constructs: function: call to 'atomicCompareExchangeWeak', a built-in function of another shading language that HIP does not define and the program does not declare; function: call to 'atomicThreadFence', a built-in function of another shading language that HIP does not define and`: `atomic_compare_exchange_weak`

</details>
