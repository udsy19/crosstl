# CrossTL translation matrix: CUDA to WGSL

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). CrossTL translated each native CUDA probe whose feature WGSL has too straight to WGSL, and naga checked the result. It is compile-only. [COVERAGE.md](../COVERAGE.md#translation-matrix) describes the matrix and has every other cell.

Score 89.1 %: 197 supported, 14 refused, 10 wrong, 0 untested.

## Gaps

<details>
<summary>24 gaps: 14 refused, 10 wrong</summary>

Wrong, by cause:

- `Entry point compute_main at Compute is invalid` (6): `sampled-texture`, `texture-1d`, `texture-2d-array`, `texture-3d`, `texture-cube`, `texture-cube-array`
- `no definition in scope for identifier: 'cudaTextureObject_t'` (2): `texture-argument`, `texture-in-helper`
- `type can't be inferred`: `zero-initializer`
- `the translation loses BuiltIn.SubgroupSize`: `subgroup-size`

Refused, by diagnostic:

- `project.translate.wgsl-foreign-builtin-call: WGSLForeignBuiltinCallError: WGSL target cannot lower the call to <feature>(): <feature> is a built-in function of another language, and WGSL declares no built-in function of that name (target wgsl) [project.translate.wgsl-foreign-builtin-call]` (4): `acoshf`, `asinhf`, `atanhf`, `ldexpf`
- `project.translate.wgsl-refused: WGSLRefusal: WGSL target does not support CrossGL resource type image2D yet; split texture/sampler/storage bindings are required` (3): `integer-storage-image`, `storage-image`, `unorm-storage-image`
- `project.translate.undeclared-function: UndeclaredFunctionError: function 'surf2Dread' is not declared: it is neither a CrossGL built-in function nor a function, structure method, type or callable value of the program (target wgsl) [project.translate.undeclared-function]`: `read-write-image`
- `project.translate.wgsl-pointer-type-unsupported: WGSLPointerTypeUnsupportedError: WGSL target cannot represent CrossGL pointer type 'ptr<f32>': the spelling carries no address space, and WGSL pointers must name one (ptr<address-space, T>) (target wgsl) [project.translate.wgsl-pointer-type-unsupported]`: `pointer-local`
- `project.translate.wgsl-pointer-type-unsupported: WGSLPointerTypeUnsupportedError: WGSL target cannot represent CrossGL pointer type 'ptr<i32>': the spelling carries no address space, and WGSL pointers must name one (ptr<address-space, T>) (target wgsl) [project.translate.wgsl-pointer-type-unsupported]`: `buffer-in-helper`
- `project.translate.wgsl-refused: WGSLRefusal: WGSL target does not support CrossGL resource type image1D yet; split texture/sampler/storage bindings are required`: `storage-image-1d`
- `project.translate.wgsl-refused: WGSLRefusal: WGSL target does not support CrossGL resource type image2DArray yet; split texture/sampler/storage bindings are required`: `storage-image-array`
- `project.translate.wgsl-refused: WGSLRefusal: WGSL target does not support CrossGL resource type image3D yet; split texture/sampler/storage bindings are required`: `storage-image-3d`
- `project.translate.wgsl-refused: WGSLRefusal: WGSL target does not support direct builtin identifier(s) in helper function invocation: gl_GlobalInvocationID; pass builtin values through entry-point parameters instead`: `invocation-id-in-helper`

</details>
