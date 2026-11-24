# CrossTL translation matrix: HLSL to Metal

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native HLSL probe whose feature Metal has too straight to Metal, and metal checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 96.3 %: 368 supported, 8 refused, 6 wrong, 0 untested.

## Gaps

<details>
<summary>14 gaps: 8 refused, 6 wrong</summary>

Wrong, by cause:

- `brackets are not allowed here; to declare an array, place the brackets after the name`: `array-return`
- `cannot initialize a variable of type 'thread int2' (vector of N 'int' values) with an rvalue of type 'metal::float2' (aka 'float2')`: `sign`
- `the translation loses Decoration.Centroid`: `centroid-interpolation`
- `the translation loses Decoration.Flat`: `flat-interpolation`
- `the translation loses Decoration.NoPerspective`: `noperspective-interpolation`
- `the translation loses Decoration.Sample`: `sample-interpolation`

Refused, by diagnostic:

- `project.translate.metal-refused: MetalRefusal: Cannot store to part of HLSL structured-buffer matrix 'm' in Metal: it is held as words` (3): `buffer-row-major-array`, `buffer-row-major-matrix`, `buffer-row-major-non-square`
- `project.translate.metal-lowering-unsupported: MetalLoweringRefused: Metal cannot lower N construct: function: call to '<feature>', a built-in function of another shading language that Metal does not define and the program does not declare (target metal) [project.translate.metal-lowering-unsupported]` (2): `InterlockedCompareExchangeFloatBitwise`, `InterlockedCompareStoreFloatBitwise`
- `project.translate.metal-lowering-unsupported: MetalLoweringRefused: Metal cannot lower N constructs: semantic '<feature>' names no Metal attribute; the Metal compiler ignores an unknown attribute, so the declaration would lose the binding the semantic gives it; semantic '<feature>' names no Metal attribute; the Metal compiler ignores an unknown attri` (2): `tessellation-domain-quads`, `tessellation-evaluation`
- `project.translate.metal-refused: MetalRefusal: Cannot store to part of a matrix element of HLSL structured buffer '<probe>' in Metal: it is held as words`: `matrix-buffer`

</details>
