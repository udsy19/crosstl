<!-- Written from coverage.json by tools/coverage/docs.py when the Coverage workflow publishes. Do not edit. -->

# HIP

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z (CrossTL 3.8.0) by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). The Coverage workflow writes this page from `coverage.json` each time it publishes; [COVERAGE.md](../COVERAGE.md) defines each outcome. Score = supported / (supported + refused + wrong).

The [backend guide](https://github.com/CrossGL/crosstl/blob/main/docs/source/backends/hip.rst) describes how CrossTL translates HIP.

| Direction | Score | Supported | Refused | Wrong | Untested | Executed | Reference tool |
|---|---:|---:|---:|---:|---:|---|---|
| output | 100.0 % | 567 | 0 | 0 | 0 | compile-only | hipcc (HIP version: 5.7.31921-0) |
| input | 99.6 % | 565 | 2 | 0 | 0 | compile-only | hipcc (HIP version: 5.7.31921-0) |

## Feature lists

- [LLVM 17.0.6 device-side HIP math functions and intrinsics](https://github.com/llvm/llvm-project/blob/6009708b4367171ccdbf4b5905cb6a803753fe18/clang/lib/Headers/__clang_hip_math.h), pinned at `6009708b4367`
- [ROCm 5.7.1 HIP atomic functions](https://github.com/ROCm/clr/blob/1949b1621a802ffb1492616adbae6154bfbe64ef/hipamd/include/hip/amd_detail/amd_hip_atomic.h), pinned at `1949b1621a80`
- [ROCm 5.7.1 HIP device functions (integer intrinsics, conversions, barriers)](https://github.com/ROCm/clr/blob/1949b1621a802ffb1492616adbae6154bfbe64ef/hipamd/include/hip/amd_detail/amd_device_functions.h), pinned at `1949b1621a80`
- [ROCm 5.7.1 HIP warp shuffles and lane permutes](https://github.com/ROCm/clr/blob/1949b1621a802ffb1492616adbae6154bfbe64ef/hipamd/include/hip/amd_detail/amd_warp_functions.h), pinned at `1949b1621a80`

## By category

Each cell counts the supported features of a category over its supported, refused and wrong ones.

| Category | output | input |
|---|---:|---:|
| compute | 18/18 | 18/18 |
| control-flow | 60/60 | 60/60 |
| function | 361/361 | 361/361 |
| operator | 34/34 | 34/34 |
| resource | 45/45 | 44/45 |
| stage | 1/1 | 1/1 |
| type | 48/48 | 47/48 |

## Translation pairs

The cells of the translation matrix that translate HIP straight to another language or another language straight to it, measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z. Each cell measures the features of the source's input row that the target has too, and its page lists the gaps.

| Source | Target | Score | Supported | Refused | Wrong | Untested | Executed |
|---|---|---:|---:|---:|---:|---:|---|
| HIP | CUDA | [99.4 %](../pairs/hip-to-cuda.md) | 529 | 2 | 1 | 0 | compile-only |
| HIP | GLSL ES | [92.1 %](../pairs/hip-to-gles.md) | 222 | 9 | 10 | 2 | compile-only |
| HIP | GLSL | [89.5 %](../pairs/hip-to-glsl.md) | 248 | 21 | 8 | 0 | compile-only |
| HIP | HLSL | [94.4 %](../pairs/hip-to-hlsl.md) | 251 | 8 | 7 | 0 | compile-only |
| HIP | Metal | [90.0 %](../pairs/hip-to-metal.md) | 234 | 15 | 11 | 0 | compile-only |
| HIP | Mojo | [84.9 %](../pairs/hip-to-mojo.md) | 231 | 31 | 10 | 0 | compile-only |
| HIP | Rust | [66.5 %](../pairs/hip-to-rust.md) | 175 | 62 | 26 | 2 | compile-only |
| HIP | Slang | [83.7 %](../pairs/hip-to-slang.md) | 242 | 22 | 25 | 0 | compile-only |
| HIP | SPIR-V | [86.9 %](../pairs/hip-to-spirv.md) | 251 | 28 | 10 | 0 | compile-only |
| HIP | WGSL | [90.6 %](../pairs/hip-to-wgsl.md) | 202 | 11 | 10 | 0 | compile-only |
| CUDA | HIP | [99.4 %](../pairs/cuda-to-hip.md) | 529 | 3 | 0 | 0 | compile-only |
| GLSL | HIP | [95.9 %](../pairs/glsl-to-hip.md) | 235 | 5 | 5 | 0 | compile-only |
| HLSL | HIP | [95.4 %](../pairs/hlsl-to-hip.md) | 230 | 7 | 4 | 0 | compile-only |
| Metal | HIP | [86.6 %](../pairs/metal-to-hip.md) | 240 | 16 | 21 | 0 | compile-only |
| Mojo | HIP | [0.0 %](../pairs/mojo-to-hip.md) | 0 | 224 | 0 | 0 | compile-only |
| OpenCL C | HIP | [87.3 %](../pairs/opencl-to-hip.md) | 214 | 27 | 4 | 0 | compile-only |
| Rust | HIP | [80.0 %](../pairs/rust-to-hip.md) | 204 | 30 | 21 | 1 | compile-only |
| Slang | HIP | [93.4 %](../pairs/slang-to-hip.md) | 240 | 8 | 9 | 0 | compile-only |
| SPIR-V | HIP | [94.0 %](../pairs/spirv-to-hip.md) | 235 | 0 | 15 | 2 | compile-only |
| WebGL | HIP | [0.0 %](../pairs/webgl-to-hip.md) | 0 | 177 | 0 | 0 | compile-only |

## Gaps

A diagnostic drops its line numbers and writes the probe's own variables as `<probe>`, and one that several features share writes each feature's name as `<feature>`.

### Input

Refused, by diagnostic:

- `project.translate.hip-record-semantics-unsupported: HipRecordSemanticError: HIP record method call 'width' is unsupported for record 'Span' in call expression`: `struct-method`
- `project.translate.hip-surface-byte-offset-unproven: HipSurfaceByteOffsetError: surf2Dwrite cannot scale its x byte offset N: the element type is unknown, so the offset cannot be shown to be a multiple of the element size [project.translate.hip-surface-byte-offset-unproven]`: `read-write-image`
