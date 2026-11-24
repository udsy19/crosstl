# CrossTL translation matrix: Slang to CUDA

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native Slang probe whose feature CUDA has too straight to CUDA, and nvcc checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 93.7 %: 239 supported, 8 refused, 8 wrong, 0 untested.

## Gaps

<details>
<summary>16 gaps: 8 refused, 8 wrong</summary>

Wrong, by cause:

- `no instance of overloaded function "<feature>" matches the argument list` (8): `acosh`, `asinh`, `atanh`, `fabs`, `fdim`, `fmod`, `nextafter`, `rint`

Refused, by diagnostic:

- `project.translate.cuda-lowering-unsupported: CudaLoweringRefused: CUDA cannot lower N construct: function: call to '<feature>', a built-in function of another shading language that CUDA does not define and the program does not declare (target cuda) [project.translate.cuda-lowering-unsupported]` (2): `max3`, `min3`
- `project.translate.slang-import-unsupported: SlangImportRefused: CrossGL cannot represent N Slang construct: Slang <feature> has no CrossGL atomic operation (target cgl) [project.translate.slang-import-unsupported]` (2): `InterlockedCompareExchangeFloatBitwise`, `InterlockedCompareStoreFloatBitwise`
- `project.translate.crossgl-function-body-parse-failed: CrossGLFunctionBodyParseError: CrossGL could not parse the body of function '<probe>' at IDENTIFIER 'b': Expected SEMICOLON, got IDENTIFIER 'b'`: `multi-variable-loop`
- `project.translate.crossgl-syntax-error: CrossGLSyntaxError: Expected a structure name after 'struct', got MATCH 'match'`: `reserved-type-name`
- `project.translate.cuda-lowering-unsupported: CudaLoweringRefused: CUDA cannot lower N construct: type: the built-in type 'Buffer' has no CUDA spelling (target cuda) [project.translate.cuda-lowering-unsupported]`: `texel-buffer`
- `project.translate.undeclared-type: UndeclaredTypeError: type 'T' is not declared: it is neither a CrossGL built-in type nor a structure, enumeration, type alias or generic parameter of the program (target cuda) [project.translate.undeclared-type]`: `generic-function`

</details>
