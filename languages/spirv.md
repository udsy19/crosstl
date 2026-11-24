<!-- Written from coverage.json by tools/coverage/docs.py when the Coverage workflow publishes. Do not edit. -->

# SPIR-V

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z (CrossTL 3.8.0) by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). The Coverage workflow writes this page from `coverage.json` each time it publishes; [COVERAGE.md](../COVERAGE.md) defines each outcome. Score = supported / (supported + refused + wrong).

The [backend guide](https://github.com/CrossGL/crosstl/blob/main/docs/source/backends/spirv.rst) describes how CrossTL translates SPIR-V.

| Direction | Score | Supported | Refused | Wrong | Untested | Executed | Reference tool |
|---|---:|---:|---:|---:|---:|---|---|
| output | 100.0 % | 565 | 0 | 0 | 3 | 403 on vulkan-lavapipe | spirv-val (SPIRV-Tools v2026.4 ef96ed763b43b59b33b31b362f09a02b729fa1c9) |
| input | 100.0 % | 567 | 0 | 0 | 1 | 403 on vulkan-lavapipe | spirv-val (SPIRV-Tools v2026.4 ef96ed763b43b59b33b31b362f09a02b729fa1c9) |

## Feature lists

- [SPIR-V GLSL.std.450 extended instruction grammar](https://github.com/KhronosGroup/SPIRV-Headers/blob/496543121ce6419f23d6fa5d7194ba66c36212d2/include/spirv/unified1/extinst.glsl.std.450.grammar.json), pinned at `496543121ce6`
- [SPIR-V core grammar (execution models, capabilities, storage classes, instructions)](https://github.com/KhronosGroup/SPIRV-Headers/blob/496543121ce6419f23d6fa5d7194ba66c36212d2/include/spirv/unified1/spirv.core.grammar.json), pinned at `496543121ce6`

## By category

Each cell counts the supported features of a category over its supported, refused and wrong ones.

| Category | output | input |
|---|---:|---:|
| compute | 28/28 | 28/28 |
| control-flow | 62/62 | 62/62 |
| function | 199/199 | 201/201 |
| graphics | 73/73 | 73/73 |
| operator | 52/52 | 52/52 |
| resource | 67/67 | 67/67 |
| stage | 14/14 | 14/14 |
| type | 70/70 | 70/70 |

## Translation pairs

The cells of the translation matrix that translate SPIR-V straight to another language or another language straight to it, measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z. Each cell measures the features of the source's input row that the target has too, and its page lists the gaps.

| Source | Target | Score | Supported | Refused | Wrong | Untested | Executed |
|---|---|---:|---:|---:|---:|---:|---|
| SPIR-V | CUDA | [5.2 %](../pairs/spirv-to-cuda.md) | 13 | 0 | 236 | 2 | compile-only |
| SPIR-V | GLSL ES | [56.6 %](../pairs/spirv-to-gles.md) | 257 | 8 | 189 | 9 | compile-only |
| SPIR-V | GLSL | [98.6 %](../pairs/spirv-to-glsl.md) | 503 | 7 | 0 | 0 | yes |
| SPIR-V | HIP | [94.0 %](../pairs/spirv-to-hip.md) | 235 | 0 | 15 | 2 | compile-only |
| SPIR-V | HLSL | [93.3 %](../pairs/spirv-to-hlsl.md) | 404 | 19 | 10 | 0 | yes |
| SPIR-V | Metal | [97.6 %](../pairs/spirv-to-metal.md) | 401 | 8 | 2 | 9 | compile-only |
| SPIR-V | Mojo | [0.0 %](../pairs/spirv-to-mojo.md) | 0 | 15 | 217 | 2 | compile-only |
| SPIR-V | Rust | [3.2 %](../pairs/spirv-to-rust.md) | 14 | 211 | 213 | 10 | yes |
| SPIR-V | Slang | [19.7 %](../pairs/spirv-to-slang.md) | 93 | 54 | 325 | 0 | yes |
| SPIR-V | WebGL | [75.0 %](../pairs/spirv-to-webgl.md) | 15 | 5 | 0 | 0 | compile-only |
| SPIR-V | WGSL | [4.4 %](../pairs/spirv-to-wgsl.md) | 16 | 4 | 344 | 1 | yes |
| CUDA | SPIR-V | [85.8 %](../pairs/cuda-to-spirv.md) | 247 | 31 | 10 | 0 | compile-only |
| GLSL | SPIR-V | [99.2 %](../pairs/glsl-to-spirv.md) | 522 | 4 | 0 | 0 | yes |
| HIP | SPIR-V | [86.9 %](../pairs/hip-to-spirv.md) | 251 | 28 | 10 | 0 | compile-only |
| HLSL | SPIR-V | [93.8 %](../pairs/hlsl-to-spirv.md) | 423 | 20 | 8 | 0 | yes |
| Metal | SPIR-V | [91.3 %](../pairs/metal-to-spirv.md) | 399 | 29 | 9 | 0 | compile-only |
| Mojo | SPIR-V | [0.0 %](../pairs/mojo-to-spirv.md) | 0 | 238 | 0 | 0 | compile-only |
| OpenCL C | SPIR-V | [91.9 %](../pairs/opencl-to-spirv.md) | 228 | 18 | 2 | 0 | compile-only |
| Rust | SPIR-V | [55.2 %](../pairs/rust-to-spirv.md) | 262 | 203 | 10 | 0 | yes |
| Slang | SPIR-V | [84.4 %](../pairs/slang-to-spirv.md) | 411 | 41 | 35 | 0 | yes |
| WebGL | SPIR-V | [99.7 %](../pairs/webgl-to-spirv.md) | 296 | 1 | 0 | 0 | compile-only |

## Gaps

A diagnostic drops its line numbers and writes the probe's own variables as `<probe>`, and one that several features share writes each feature's name as `<feature>`.

### Output

Untested, by reason:

- `alternative encoding of Frexp, chosen by the compiler`: `FrexpStruct`
- `alternative encoding of Modf, chosen by the compiler`: `ModfStruct`
- `reserved by the GLSL.std.450 specification, not a valid instruction`: `IMix`

### Input

Untested, by reason:

- `reserved by the GLSL.std.450 specification, not a valid instruction`: `IMix`
