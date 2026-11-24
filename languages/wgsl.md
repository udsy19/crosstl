<!-- Written from coverage.json by tools/coverage/docs.py when the Coverage workflow publishes. Do not edit. -->

# WGSL

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z (CrossTL 3.8.0) by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). The Coverage workflow writes this page from `coverage.json` each time it publishes; [COVERAGE.md](../COVERAGE.md) defines each outcome. Score = supported / (supported + refused + wrong).

The [backend guide](https://github.com/CrossGL/crosstl/blob/main/docs/source/backends/wgsl.rst) describes how CrossTL translates WGSL.

| Direction | Score | Supported | Refused | Wrong | Untested | Executed | Reference tool |
|---|---:|---:|---:|---:|---:|---|---|
| output | 100.0 % | 403 | 0 | 0 | 1 | 321 on vulkan-lavapipe | naga (30.0.1) |
| input | not offered | | | | | | |

WGSL input is not offered: CrossTL has no WGSL source frontend.

## Feature lists

- [Tint's WGSL built-in function definitions](https://github.com/google/dawn/blob/ff7c6960f62d4249f967a78448918eec21705a86/src/tint/lang/wgsl/wgsl.def), pinned at `ff7c6960f62d`

## By category

Each cell counts the supported features of a category over its supported, refused and wrong ones.

| Category | output |
|---|---:|
| compute | 22/22 |
| control-flow | 56/56 |
| function | 145/145 |
| graphics | 16/16 |
| operator | 48/48 |
| resource | 57/57 |
| stage | 3/3 |
| type | 56/56 |

## Translation pairs

The cells of the translation matrix that translate WGSL straight to another language or another language straight to it, measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z. Each cell measures the features of the source's input row that the target has too, and its page lists the gaps.

| Source | Target | Score | Supported | Refused | Wrong | Untested | Executed |
|---|---|---:|---:|---:|---:|---:|---|
| CUDA | WGSL | [89.1 %](../pairs/cuda-to-wgsl.md) | 197 | 14 | 10 | 0 | compile-only |
| GLSL | WGSL | [96.7 %](../pairs/glsl-to-wgsl.md) | 354 | 1 | 11 | 1 | yes |
| HIP | WGSL | [90.6 %](../pairs/hip-to-wgsl.md) | 202 | 11 | 10 | 0 | compile-only |
| HLSL | WGSL | [87.2 %](../pairs/hlsl-to-wgsl.md) | 395 | 54 | 4 | 1 | yes |
| Metal | WGSL | [87.7 %](../pairs/metal-to-wgsl.md) | 313 | 28 | 16 | 1 | compile-only |
| Mojo | WGSL | [0.0 %](../pairs/mojo-to-wgsl.md) | 0 | 219 | 0 | 0 | compile-only |
| OpenCL C | WGSL | [83.7 %](../pairs/opencl-to-wgsl.md) | 190 | 34 | 3 | 0 | compile-only |
| Rust | WGSL | [52.0 %](../pairs/rust-to-wgsl.md) | 194 | 96 | 83 | 1 | yes |
| Slang | WGSL | [81.7 %](../pairs/slang-to-wgsl.md) | 309 | 34 | 35 | 1 | yes |
| SPIR-V | WGSL | [4.4 %](../pairs/spirv-to-wgsl.md) | 16 | 4 | 344 | 1 | yes |
| WebGL | WGSL | [98.4 %](../pairs/webgl-to-wgsl.md) | 252 | 0 | 4 | 0 | compile-only |

## Gaps

A diagnostic drops its line numbers and writes the probe's own variables as `<probe>`, and one that several features share writes each feature's name as `<feature>`.

### Output

Untested, by reason:

- `the probe itself is rejected: error: no definition in scope for identifier: 'subgroupElect'`: `subgroupElect`
