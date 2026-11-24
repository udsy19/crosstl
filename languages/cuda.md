<!-- Written from coverage.json by tools/coverage/docs.py when the Coverage workflow publishes. Do not edit. -->

# CUDA

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z (CrossTL 3.8.0) by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). The Coverage workflow writes this page from `coverage.json` each time it publishes; [COVERAGE.md](../COVERAGE.md) defines each outcome. Score = supported / (supported + refused + wrong).

The [backend guide](https://github.com/CrossGL/crosstl/blob/main/docs/source/backends/cuda.rst) describes how CrossTL translates CUDA.

| Direction | Score | Supported | Refused | Wrong | Untested | Executed | Reference tool |
|---|---:|---:|---:|---:|---:|---|---|
| output | 100.0 % | 718 | 0 | 0 | 0 | compile-only | nvcc: NVIDIA (R) Cuda compiler driver |
| input | 99.9 % | 717 | 1 | 0 | 0 | compile-only | nvcc: NVIDIA (R) Cuda compiler driver |

## Feature lists

- [LLVM 23.1.3 device-side CUDA Math API wrappers](https://github.com/llvm/llvm-project/blob/0d261d1ca552c95a8f007e061c787ac7132fbcbc/clang/lib/Headers/__clang_cuda_math.h), pinned at `0d261d1ca552`
- [LLVM 23.1.3 CUDA intrinsic and atomic wrappers](https://github.com/llvm/llvm-project/blob/0d261d1ca552c95a8f007e061c787ac7132fbcbc/clang/lib/Headers/__clang_cuda_device_functions.h), pinned at `0d261d1ca552`
- [LLVM 23.1.3 CUDA warp, cache-hinted load and store, and funnel shift intrinsics](https://github.com/llvm/llvm-project/blob/0d261d1ca552c95a8f007e061c787ac7132fbcbc/clang/lib/Headers/__clang_cuda_intrinsics.h), pinned at `0d261d1ca552`

## By category

Each cell counts the supported features of a category over its supported, refused and wrong ones.

| Category | output | input |
|---|---:|---:|
| compute | 18/18 | 18/18 |
| control-flow | 60/60 | 60/60 |
| function | 512/512 | 512/512 |
| operator | 34/34 | 34/34 |
| resource | 45/45 | 44/45 |
| stage | 1/1 | 1/1 |
| type | 48/48 | 48/48 |

## Translation pairs

The cells of the translation matrix that translate CUDA straight to another language or another language straight to it, measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z. Each cell measures the features of the source's input row that the target has too, and its page lists the gaps.

| Source | Target | Score | Supported | Refused | Wrong | Untested | Executed |
|---|---|---:|---:|---:|---:|---:|---|
| CUDA | GLSL ES | [90.8 %](../pairs/cuda-to-gles.md) | 218 | 13 | 9 | 2 | compile-only |
| CUDA | GLSL | [88.0 %](../pairs/cuda-to-glsl.md) | 243 | 25 | 8 | 0 | compile-only |
| CUDA | HIP | [99.4 %](../pairs/cuda-to-hip.md) | 529 | 3 | 0 | 0 | compile-only |
| CUDA | HLSL | [94.7 %](../pairs/cuda-to-hlsl.md) | 251 | 9 | 5 | 0 | compile-only |
| CUDA | Metal | [89.2 %](../pairs/cuda-to-metal.md) | 231 | 17 | 11 | 0 | compile-only |
| CUDA | Mojo | [85.5 %](../pairs/cuda-to-mojo.md) | 230 | 31 | 8 | 0 | compile-only |
| CUDA | Rust | [66.8 %](../pairs/cuda-to-rust.md) | 173 | 59 | 27 | 2 | compile-only |
| CUDA | Slang | [83.0 %](../pairs/cuda-to-slang.md) | 239 | 24 | 25 | 0 | compile-only |
| CUDA | SPIR-V | [85.8 %](../pairs/cuda-to-spirv.md) | 247 | 31 | 10 | 0 | compile-only |
| CUDA | WGSL | [89.1 %](../pairs/cuda-to-wgsl.md) | 197 | 14 | 10 | 0 | compile-only |
| GLSL | CUDA | [95.9 %](../pairs/glsl-to-cuda.md) | 234 | 5 | 5 | 0 | compile-only |
| HIP | CUDA | [99.4 %](../pairs/hip-to-cuda.md) | 529 | 2 | 1 | 0 | compile-only |
| HLSL | CUDA | [95.4 %](../pairs/hlsl-to-cuda.md) | 229 | 7 | 4 | 0 | compile-only |
| Metal | CUDA | [86.6 %](../pairs/metal-to-cuda.md) | 239 | 16 | 21 | 0 | compile-only |
| Mojo | CUDA | [0.0 %](../pairs/mojo-to-cuda.md) | 0 | 222 | 0 | 0 | compile-only |
| OpenCL C | CUDA | [87.7 %](../pairs/opencl-to-cuda.md) | 213 | 27 | 3 | 0 | compile-only |
| Rust | CUDA | [81.0 %](../pairs/rust-to-cuda.md) | 204 | 28 | 20 | 1 | compile-only |
| Slang | CUDA | [93.7 %](../pairs/slang-to-cuda.md) | 239 | 8 | 8 | 0 | compile-only |
| SPIR-V | CUDA | [5.2 %](../pairs/spirv-to-cuda.md) | 13 | 0 | 236 | 2 | compile-only |
| WebGL | CUDA | [0.0 %](../pairs/webgl-to-cuda.md) | 0 | 177 | 0 | 0 | compile-only |

## Gaps

A diagnostic drops its line numbers and writes the probe's own variables as `<probe>`, and one that several features share writes each feature's name as `<feature>`.

### Input

Refused, by diagnostic:

- `project.translate.undeclared-function: UndeclaredFunctionError: function 'surf2Dread' is not declared: it is neither a CrossGL built-in function nor a function, structure method, type or callable value of the program (target cuda) [project.translate.undeclared-function]`: `read-write-image`
