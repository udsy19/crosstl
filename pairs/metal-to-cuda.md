# CrossTL translation matrix: Metal to CUDA

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native Metal probe whose feature CUDA has too straight to CUDA, and nvcc checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 86.6 %: 239 supported, 16 refused, 21 wrong, 0 untested.

## Gaps

<details>
<summary>37 gaps: 16 refused, 21 wrong</summary>

Wrong, by cause:

- `no instance of overloaded function "<feature>" matches the argument list` (12): `acosh`, `asinh`, `atanh`, `copysign`, `fabs`, `fdim`, `fmax`, `fmin`, `ilogb`, `log10`, `nextafter`, `rint`
- `identifier "<feature>" is undefined` (3): `int16`, `uint16`, `uint8`
- `identifier "int8" is undefined` (2): `int8`, `integer-promotion`
- `no instance of overloaded function "fmod" matches the argument list` (2): `float-remainder`, `fmod`
- `no suitable user-defined conversion from "uint3" to "int3" exists`: `popcount`
- `too few arguments in function call`: `zero-initializer`

Refused, by diagnostic:

- `project.translate.cuda-lowering-unsupported: CudaLoweringRefused: CUDA cannot lower N construct: function: call to 'atomicThreadFence', a built-in function of another shading language that CUDA does not define and the program does not declare (target cuda) [project.translate.cuda-lowering-unsupported]` (7): `atomic_exchange`, `atomic_fetch_add`, `atomic_fetch_and`, `atomic_fetch_max`, `atomic_fetch_min`, `atomic_fetch_or`, `atomic_fetch_xor`
- `project.translate.cuda-lowering-unsupported: CudaLoweringRefused: CUDA cannot lower N construct: function: call to '<feature>', a built-in function of another shading language that CUDA does not define and the program does not declare (target cuda) [project.translate.cuda-lowering-unsupported]` (2): `max3`, `min3`
- `project.translate.cuda-lowering-unsupported: CudaLoweringRefused: CUDA cannot lower N construct: sincos: it takes N value and N output operands (target cuda) [project.translate.cuda-lowering-unsupported]`: `sincos`
- `project.translate.cuda-lowering-unsupported: CudaLoweringRefused: CUDA cannot lower N construct: CUDA structured buffer atomic: atomicMax on RWStructuredBuffer<uint64> requires supported scalar int/uint target (target cuda) [project.translate.cuda-lowering-unsupported]`: `atomic_max_explicit`
- `project.translate.cuda-lowering-unsupported: CudaLoweringRefused: CUDA cannot lower N construct: CUDA structured buffer atomic: atomicMin on RWStructuredBuffer<uint64> requires supported scalar int/uint target (target cuda) [project.translate.cuda-lowering-unsupported]`: `atomic_min_explicit`
- `project.translate.cuda-lowering-unsupported: CudaLoweringRefused: CUDA cannot lower N construct: function: call to 'atomicCompareExchangeWeak', a built-in function of another shading language that CUDA does not define and the program does not declare (target cuda) [project.translate.cuda-lowering-unsupported]`: `atomic_compare_exchange_weak_explicit`
- `project.translate.cuda-lowering-unsupported: CudaLoweringRefused: CUDA cannot lower N constructs: CUDA structured buffer atomic: atomicMax on RWStructuredBuffer<uint64> requires supported scalar int/uint target; function: call to 'atomicThreadFence', a built-in function of another shading language that CUDA does not define and the program does not declare (target`: `atomic_max`
- `project.translate.cuda-lowering-unsupported: CudaLoweringRefused: CUDA cannot lower N constructs: CUDA structured buffer atomic: atomicMin on RWStructuredBuffer<uint64> requires supported scalar int/uint target; function: call to 'atomicThreadFence', a built-in function of another shading language that CUDA does not define and the program does not declare (target`: `atomic_min`
- `project.translate.cuda-lowering-unsupported: CudaLoweringRefused: CUDA cannot lower N constructs: function: call to 'atomicCompareExchangeWeak', a built-in function of another shading language that CUDA does not define and the program does not declare; function: call to 'atomicThreadFence', a built-in function of another shading language that CUDA does not define`: `atomic_compare_exchange_weak`

</details>
