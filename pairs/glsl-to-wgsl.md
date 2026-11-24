# CrossTL translation matrix: GLSL to WGSL

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native GLSL probe whose feature WGSL has too straight to WGSL, and naga checked the result. Its compute probes also ran on a runtime. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 96.7 %: 354 supported, 1 refused, 11 wrong, 1 untested.

## Gaps

<details>
<summary>12 gaps: 1 refused, 11 wrong</summary>

Wrong, by cause:

- `no definition in scope for identifier: '<feature>'` (8): `fragment-depth`, `front-facing`, `instance-index`, `primitive-id`, `sample-index`, `sample-mask`, `sample-mask-input`, `vertex-index`
- `on vulkan-lavapipe as SPIR-V from glslangValidator and naga, the translation computes different results from the native probe` (3): `buffer-row-major-array`, `buffer-row-major-matrix`, `buffer-row-major-non-square`

Refused, by diagnostic:

- `project.translate.wgsl-refused: WGSLRefusal: WGSL target does not support CrossGL resource type image2DMS yet; split texture/sampler/storage bindings are required`: `imageSamples`

</details>

<details>
<summary>1 untested: function 1</summary>

- `the target's own probe is rejected: error: no definition in scope for identifier: 'subgroupElect'`: `subgroupElect`

</details>
