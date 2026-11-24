<!-- Written from coverage.json by tools/coverage/docs.py when the Coverage workflow publishes. Do not edit. -->

# Metal

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z (CrossTL 3.8.0) by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). The Coverage workflow writes this page from `coverage.json` each time it publishes; [COVERAGE.md](../COVERAGE.md) defines each outcome. Score = supported / (supported + refused + wrong).

The [backend guide](https://github.com/CrossGL/crosstl/blob/main/docs/source/backends/metal.rst) describes how CrossTL translates Metal.

| Direction | Score | Supported | Refused | Wrong | Untested | Executed | Reference tool |
|---|---:|---:|---:|---:|---:|---|---|
| output | 100.0 % | 545 | 0 | 0 | 0 | 452 on metal-apple | metal (Apple metal version 32023.921 (metalfe-32023.921.6)) |
| input | 100.0 % | 545 | 0 | 0 | 0 | 471 on metal-apple | metal (Apple metal version 32023.921 (metalfe-32023.921.6)) |

## Feature lists

- [Metal Shading Language 4.1 standard library, from Apple metal version 32023.918 (metalfe-32023.918.1)](https://github.com/CrossGL/crosstl/blob/35ed8c7dc43264b625206cb6bf60d0858d205616/tools/coverage/features/metal.txt), kept in this repository

## By category

Each cell counts the supported features of a category over its supported, refused and wrong ones.

| Category | output | input |
|---|---:|---:|
| compute | 25/25 | 25/25 |
| control-flow | 62/62 | 62/62 |
| function | 224/224 | 224/224 |
| graphics | 45/45 | 45/45 |
| operator | 51/51 | 51/51 |
| resource | 64/64 | 64/64 |
| stage | 7/7 | 7/7 |
| type | 67/67 | 67/67 |

## Translation pairs

The cells of the translation matrix that translate Metal straight to another language or another language straight to it, measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z. Each cell measures the features of the source's input row that the target has too, and its page lists the gaps.

| Source | Target | Score | Supported | Refused | Wrong | Untested | Executed |
|---|---|---:|---:|---:|---:|---:|---|
| Metal | CUDA | [86.6 %](../pairs/metal-to-cuda.md) | 239 | 16 | 21 | 0 | compile-only |
| Metal | GLSL ES | [85.0 %](../pairs/metal-to-gles.md) | 339 | 25 | 35 | 8 | compile-only |
| Metal | GLSL | [93.9 %](../pairs/metal-to-glsl.md) | 402 | 18 | 8 | 0 | compile-only |
| Metal | HIP | [86.6 %](../pairs/metal-to-hip.md) | 240 | 16 | 21 | 0 | compile-only |
| Metal | HLSL | [92.0 %](../pairs/metal-to-hlsl.md) | 358 | 12 | 19 | 0 | compile-only |
| Metal | Mojo | [0.0 %](../pairs/metal-to-mojo.md) | 0 | 33 | 223 | 0 | compile-only |
| Metal | Rust | [69.0 %](../pairs/metal-to-rust.md) | 274 | 113 | 10 | 2 | compile-only |
| Metal | Slang | [86.0 %](../pairs/metal-to-slang.md) | 370 | 51 | 9 | 0 | compile-only |
| Metal | SPIR-V | [91.3 %](../pairs/metal-to-spirv.md) | 399 | 29 | 9 | 0 | compile-only |
| Metal | WebGL | [72.2 %](../pairs/metal-to-webgl.md) | 13 | 3 | 2 | 0 | compile-only |
| Metal | WGSL | [87.7 %](../pairs/metal-to-wgsl.md) | 313 | 28 | 16 | 1 | compile-only |
| CUDA | Metal | [89.2 %](../pairs/cuda-to-metal.md) | 231 | 17 | 11 | 0 | compile-only |
| GLSL | Metal | [97.3 %](../pairs/glsl-to-metal.md) | 403 | 6 | 5 | 0 | compile-only |
| HIP | Metal | [90.0 %](../pairs/hip-to-metal.md) | 234 | 15 | 11 | 0 | compile-only |
| HLSL | Metal | [96.3 %](../pairs/hlsl-to-metal.md) | 368 | 8 | 6 | 0 | compile-only |
| Mojo | Metal | [0.0 %](../pairs/mojo-to-metal.md) | 0 | 247 | 0 | 0 | compile-only |
| OpenCL C | Metal | [91.5 %](../pairs/opencl-to-metal.md) | 248 | 19 | 4 | 0 | compile-only |
| Rust | Metal | [59.2 %](../pairs/rust-to-metal.md) | 242 | 106 | 61 | 2 | compile-only |
| Slang | Metal | [93.8 %](../pairs/slang-to-metal.md) | 408 | 21 | 6 | 0 | compile-only |
| SPIR-V | Metal | [97.6 %](../pairs/spirv-to-metal.md) | 401 | 8 | 2 | 9 | compile-only |
| WebGL | Metal | [99.6 %](../pairs/webgl-to-metal.md) | 260 | 0 | 1 | 0 | compile-only |
