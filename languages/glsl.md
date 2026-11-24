<!-- Written from coverage.json by tools/coverage/docs.py when the Coverage workflow publishes. Do not edit. -->

# GLSL

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z (CrossTL 3.8.0) by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). The Coverage workflow writes this page from `coverage.json` each time it publishes; [COVERAGE.md](../COVERAGE.md) defines each outcome. Score = supported / (supported + refused + wrong).

The [backend guide](https://github.com/CrossGL/crosstl/blob/main/docs/source/backends/glsl.rst) describes how CrossTL translates GLSL.

| Direction | Score | Supported | Refused | Wrong | Untested | Executed | Reference tool |
|---|---:|---:|---:|---:|---:|---|---|
| output | 99.5 % | 601 | 0 | 3 | 0 | 323 on opengl-llvmpipe, 76 on vulkan-lavapipe | glslangValidator (Glslang Version: 11:16.6.0) |
| input | 100.0 % | 604 | 0 | 0 | 0 | 320 on opengl-llvmpipe, 79 on vulkan-lavapipe | glslangValidator (Glslang Version: 11:16.6.0) |

## Feature lists

- [GLSL 4.60 specification, chapter 8 (built-in functions)](https://github.com/KhronosGroup/GLSL/blob/0099bf83b0288469917fc2e2972cb0a2b74d6711/chapters/builtinfunctions.adoc), pinned at `0099bf83b028`
- [GL_EXT_shader_quad_control (quad votes)](https://github.com/KhronosGroup/GLSL/blob/0099bf83b0288469917fc2e2972cb0a2b74d6711/extensions/ext/GLSL_EXT_shader_quad_control.txt), pinned at `0099bf83b028`
- [GL_KHR_shader_subgroup (section 8.18, shader invocation group functions)](https://github.com/KhronosGroup/GLSL/blob/0099bf83b0288469917fc2e2972cb0a2b74d6711/extensions/khr/GL_KHR_shader_subgroup.txt), pinned at `0099bf83b028`
- [GL_NV_shader_subgroup_partitioned (partitioned subgroup operations)](https://github.com/KhronosGroup/GLSL/blob/0099bf83b0288469917fc2e2972cb0a2b74d6711/extensions/nv/GL_NV_shader_subgroup_partitioned.txt), pinned at `0099bf83b028`
- [GL_KHR_shader_subgroup_rotate (subgroup rotations)](https://github.com/KhronosGroup/GLSL/blob/0099bf83b0288469917fc2e2972cb0a2b74d6711/extensions/khr/GL_KHR_shader_subgroup_rotate.txt), pinned at `0099bf83b028`

## By category

Each cell counts the supported features of a category over its supported, refused and wrong ones.

| Category | output | input |
|---|---:|---:|
| compute | 28/28 | 28/28 |
| control-flow | 59/59 | 59/59 |
| function | 248/251 | 251/251 |
| graphics | 69/69 | 69/69 |
| operator | 51/51 | 51/51 |
| resource | 67/67 | 67/67 |
| stage | 14/14 | 14/14 |
| type | 65/65 | 65/65 |

## Translation pairs

The cells of the translation matrix that translate GLSL straight to another language or another language straight to it, measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z. Each cell measures the features of the source's input row that the target has too, and its page lists the gaps.

| Source | Target | Score | Supported | Refused | Wrong | Untested | Executed |
|---|---|---:|---:|---:|---:|---:|---|
| GLSL | CUDA | [95.9 %](../pairs/glsl-to-cuda.md) | 234 | 5 | 5 | 0 | compile-only |
| GLSL | GLSL ES | [96.7 %](../pairs/glsl-to-gles.md) | 520 | 4 | 14 | 9 | compile-only |
| GLSL | HIP | [95.9 %](../pairs/glsl-to-hip.md) | 235 | 5 | 5 | 0 | compile-only |
| GLSL | HLSL | [94.9 %](../pairs/glsl-to-hlsl.md) | 408 | 12 | 10 | 0 | yes |
| GLSL | Metal | [97.3 %](../pairs/glsl-to-metal.md) | 403 | 6 | 5 | 0 | compile-only |
| GLSL | Mojo | [94.7 %](../pairs/glsl-to-mojo.md) | 216 | 11 | 1 | 0 | compile-only |
| GLSL | Rust | [4.8 %](../pairs/glsl-to-rust.md) | 22 | 432 | 1 | 0 | yes |
| GLSL | Slang | [92.7 %](../pairs/glsl-to-slang.md) | 454 | 31 | 5 | 0 | yes |
| GLSL | SPIR-V | [99.2 %](../pairs/glsl-to-spirv.md) | 522 | 4 | 0 | 0 | yes |
| GLSL | WebGL | [68.2 %](../pairs/glsl-to-webgl.md) | 15 | 7 | 0 | 0 | compile-only |
| GLSL | WGSL | [96.7 %](../pairs/glsl-to-wgsl.md) | 354 | 1 | 11 | 1 | yes |
| CUDA | GLSL | [88.0 %](../pairs/cuda-to-glsl.md) | 243 | 25 | 8 | 0 | compile-only |
| HIP | GLSL | [89.5 %](../pairs/hip-to-glsl.md) | 248 | 21 | 8 | 0 | compile-only |
| HLSL | GLSL | [94.8 %](../pairs/hlsl-to-glsl.md) | 421 | 20 | 3 | 0 | yes |
| Metal | GLSL | [93.9 %](../pairs/metal-to-glsl.md) | 402 | 18 | 8 | 0 | compile-only |
| Mojo | GLSL | [0.0 %](../pairs/mojo-to-glsl.md) | 0 | 232 | 0 | 0 | compile-only |
| OpenCL C | GLSL | [91.7 %](../pairs/opencl-to-glsl.md) | 222 | 18 | 2 | 0 | compile-only |
| Rust | GLSL | [52.8 %](../pairs/rust-to-glsl.md) | 254 | 197 | 30 | 0 | yes |
| Slang | GLSL | [90.3 %](../pairs/slang-to-glsl.md) | 457 | 41 | 8 | 0 | yes |
| SPIR-V | GLSL | [98.6 %](../pairs/spirv-to-glsl.md) | 503 | 7 | 0 | 0 | yes |
| WebGL | GLSL | [100.0 %](../pairs/webgl-to-glsl.md) | 298 | 0 | 0 | 0 | compile-only |

## Gaps

A diagnostic drops its line numbers and writes the probe's own variables as `<probe>`, and one that several features share writes each feature's name as `<feature>`.

### Output

Wrong, by cause ([open bug issues](https://github.com/CrossGL/crosstl/issues?q=is:issue%20is:open%20label:coverage%20label:bug%20label:backend:glsl%20label:direction:output)):

- `on opengl-llvmpipe, the translation is rejected by the runtime` (3): `allInvocations`, `allInvocationsEqual`, `anyInvocation`
