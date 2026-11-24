# CrossTL translation matrix: WebGL to Mojo

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native WebGL probe whose feature Mojo has too straight to Mojo, and mojo checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 97.1 %: 165 supported, 5 refused, 0 wrong, 0 untested.

## Gaps

<details>
<summary>5 gaps: 5 refused, 0 wrong</summary>

Refused, by diagnostic:

- `project.translate.mojo-lowering-unsupported: MojoLoweringRefused: Mojo cannot lower N construct: function: call to 'equal', a built-in function of another shading language that Mojo does not define and the program does not declare (target mojo) [project.translate.mojo-lowering-unsupported]` (3): `bool-vector-logic`, `integer-vector-comparison`, `vector-comparison`
- `project.translate.rule-inexpressible: RuleInexpressibleError: the signed ++ used as a value cannot be rewritten with wrapping arithmetic for mojo, whose code generator passes inout parameters by value; write it as a separate statement (target mojo) [project.translate.rule-inexpressible]` (2): `condition-assignment`, `lvalue-increment`

</details>
