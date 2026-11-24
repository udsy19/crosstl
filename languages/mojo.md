<!-- Written from coverage.json by tools/coverage/docs.py when the Coverage workflow publishes. Do not edit. -->

# Mojo

Measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z (CrossTL 3.8.0) by the [Coverage workflow](https://github.com/CrossGL/crosstl/actions/workflows/coverage.yml). The Coverage workflow writes this page from `coverage.json` each time it publishes; [COVERAGE.md](../COVERAGE.md) defines each outcome. Score = supported / (supported + refused + wrong).

The [backend guide](https://github.com/CrossGL/crosstl/blob/main/docs/source/backends/mojo.rst) describes how CrossTL translates Mojo.

| Direction | Score | Supported | Refused | Wrong | Untested | Executed | Reference tool |
|---|---:|---:|---:|---:|---:|---|---|
| output | 90.7 % | 292 | 30 | 0 | 0 | compile-only | Mojo 1.2.0 (2016d0cd) |
| input | 0.0 % | 0 | 322 | 0 | 0 | compile-only | Mojo 1.2.0 (2016d0cd) |

## Feature lists

- [Mojo 1.2.0 std.atomic functions and Atomic methods](https://github.com/modular/modular/blob/527d069ee11a41ac5320af1f9402db0a66b2b868/Mojo/stdlib/std/atomic/atomic.mojo), pinned at `527d069ee11a`
- [Mojo 1.2.0 std.atomic public API](https://github.com/modular/modular/blob/527d069ee11a41ac5320af1f9402db0a66b2b868/Mojo/stdlib/std/atomic/__init__.mojo), pinned at `527d069ee11a`
- [Mojo 1.2.0 std.bit functions](https://github.com/modular/modular/blob/527d069ee11a41ac5320af1f9402db0a66b2b868/Mojo/stdlib/std/bit/bit.mojo), pinned at `527d069ee11a`
- [Mojo 1.2.0 std.bit public API](https://github.com/modular/modular/blob/527d069ee11a41ac5320af1f9402db0a66b2b868/Mojo/stdlib/std/bit/__init__.mojo), pinned at `527d069ee11a`
- [MAX 26.7.0 max.gpu.primitives.block functions](https://github.com/modular/modular/blob/527d069ee11a41ac5320af1f9402db0a66b2b868/max/mojo/max/gpu/primitives/block.mojo), pinned at `527d069ee11a`
- [MAX 26.7.0 max.gpu.primitives.id functions](https://github.com/modular/modular/blob/527d069ee11a41ac5320af1f9402db0a66b2b868/max/mojo/max/gpu/primitives/id.mojo), pinned at `527d069ee11a`
- [Mojo 1.2.0 GPU index functions max.gpu re-exports](https://github.com/modular/modular/blob/527d069ee11a41ac5320af1f9402db0a66b2b868/Mojo/stdlib/std/_gpu/primitives/id.mojo), pinned at `527d069ee11a`
- [MAX 26.7.0 max.gpu synchronization functions](https://github.com/modular/modular/blob/527d069ee11a41ac5320af1f9402db0a66b2b868/max/mojo/max/gpu/sync/sync.mojo), pinned at `527d069ee11a`
- [MAX 26.7.0 max.gpu.sync public API](https://github.com/modular/modular/blob/527d069ee11a41ac5320af1f9402db0a66b2b868/max/mojo/max/gpu/sync/__init__.mojo), pinned at `527d069ee11a`
- [MAX 26.7.0 max.gpu.primitives.warp functions](https://github.com/modular/modular/blob/527d069ee11a41ac5320af1f9402db0a66b2b868/max/mojo/max/gpu/primitives/warp.mojo), pinned at `527d069ee11a`
- [Mojo 1.2.0 std.math functions](https://github.com/modular/modular/blob/527d069ee11a41ac5320af1f9402db0a66b2b868/Mojo/stdlib/std/math/math.mojo), pinned at `527d069ee11a`
- [Mojo 1.2.0 std.math public API](https://github.com/modular/modular/blob/527d069ee11a41ac5320af1f9402db0a66b2b868/Mojo/stdlib/std/math/__init__.mojo), pinned at `527d069ee11a`
- [Mojo 1.2.0 floating-point predicates std.math re-exports](https://github.com/modular/modular/blob/527d069ee11a41ac5320af1f9402db0a66b2b868/Mojo/stdlib/std/utils/numerics.mojo), pinned at `527d069ee11a`

## By category

Each cell counts the supported features of a category over its supported, refused and wrong ones.

| Category | output | input |
|---|---:|---:|
| compute | 16/16 | 0/16 |
| control-flow | 47/47 | 0/47 |
| function | 105/135 | 0/135 |
| operator | 42/42 | 0/42 |
| resource | 29/29 | 0/29 |
| stage | 1/1 | 0/1 |
| type | 52/52 | 0/52 |

## Translation pairs

The cells of the translation matrix that translate Mojo straight to another language or another language straight to it, measured on commit [`35ed8c7`](https://github.com/CrossGL/crosstl/commit/35ed8c7dc43264b625206cb6bf60d0858d205616) at 2026-11-24T12:11:45Z. Each cell measures the features of the source's input row that the target has too, and its page lists the gaps.

| Source | Target | Score | Supported | Refused | Wrong | Untested | Executed |
|---|---|---:|---:|---:|---:|---:|---|
| Mojo | CUDA | [0.0 %](../pairs/mojo-to-cuda.md) | 0 | 222 | 0 | 0 | compile-only |
| Mojo | GLSL ES | [0.0 %](../pairs/mojo-to-gles.md) | 0 | 229 | 0 | 2 | compile-only |
| Mojo | GLSL | [0.0 %](../pairs/mojo-to-glsl.md) | 0 | 232 | 0 | 0 | compile-only |
| Mojo | HIP | [0.0 %](../pairs/mojo-to-hip.md) | 0 | 224 | 0 | 0 | compile-only |
| Mojo | HLSL | [0.0 %](../pairs/mojo-to-hlsl.md) | 0 | 217 | 0 | 0 | compile-only |
| Mojo | Metal | [0.0 %](../pairs/mojo-to-metal.md) | 0 | 247 | 0 | 0 | compile-only |
| Mojo | Rust | [0.0 %](../pairs/mojo-to-rust.md) | 0 | 232 | 0 | 1 | compile-only |
| Mojo | Slang | [0.0 %](../pairs/mojo-to-slang.md) | 0 | 229 | 0 | 0 | compile-only |
| Mojo | SPIR-V | [0.0 %](../pairs/mojo-to-spirv.md) | 0 | 238 | 0 | 0 | compile-only |
| Mojo | WGSL | [0.0 %](../pairs/mojo-to-wgsl.md) | 0 | 219 | 0 | 0 | compile-only |
| CUDA | Mojo | [85.5 %](../pairs/cuda-to-mojo.md) | 230 | 31 | 8 | 0 | compile-only |
| GLSL | Mojo | [94.7 %](../pairs/glsl-to-mojo.md) | 216 | 11 | 1 | 0 | compile-only |
| HIP | Mojo | [84.9 %](../pairs/hip-to-mojo.md) | 231 | 31 | 10 | 0 | compile-only |
| HLSL | Mojo | [0.0 %](../pairs/hlsl-to-mojo.md) | 0 | 13 | 204 | 0 | compile-only |
| Metal | Mojo | [0.0 %](../pairs/metal-to-mojo.md) | 0 | 33 | 223 | 0 | compile-only |
| OpenCL C | Mojo | [0.0 %](../pairs/opencl-to-mojo.md) | 0 | 25 | 192 | 0 | compile-only |
| Rust | Mojo | [0.0 %](../pairs/rust-to-mojo.md) | 0 | 35 | 216 | 1 | compile-only |
| Slang | Mojo | [0.0 %](../pairs/slang-to-mojo.md) | 0 | 19 | 211 | 0 | compile-only |
| SPIR-V | Mojo | [0.0 %](../pairs/spirv-to-mojo.md) | 0 | 15 | 217 | 2 | compile-only |
| WebGL | Mojo | [97.1 %](../pairs/webgl-to-mojo.md) | 165 | 5 | 0 | 0 | compile-only |

## Gaps

A diagnostic drops its line numbers and writes the probe's own variables as `<probe>`, and one that several features share writes each feature's name as `<feature>`.

### Output

Refused, by diagnostic:

- `project.translate.undeclared-function: UndeclaredFunctionError: function '<feature>' is not declared: it is neither a CrossGL built-in function nor a function, structure method, type or callable value of the program (target mojo) [project.translate.undeclared-function]` (18): `async_copy_arrive`, `cp_async_bulk_commit_group`, `cp_async_bulk_wait_group`, `mbarrier_arrive`, `mbarrier_arrive_expect_tx_relaxed`, `mbarrier_arrive_expect_tx_shared`, `mbarrier_init`, `mbarrier_test_wait`, `mbarrier_try_wait_parity_shared`, `named_barrier`, `named_barrier_arrive`, `s_waitcnt`, `s_waitcnt_barrier`, `scalb`, `schedule_barrier`, `sm_id`, `umma_arrive_leader_cta`, `umma_arrive_peer_cta`
- `CrossGL has no spelling for this operation: CrossGL reduces, scans and broadcasts over a subgroup only, not over a workgroup` (5): `block.broadcast`, `block.max`, `block.min`, `block.prefix_sum`, `block.sum`
- `CrossGL has no spelling for this operation: no CrossGL warp reduction applies a function the kernel passes` (2): `warp.lane_group_reduce`, `warp.reduce`
- `CrossGL has no AMD instruction scheduling groups`: `schedule_group_barrier`
- `CrossGL has no spelling for this operation: CrossGL's compare-and-swap returns the value it found, and compare_exchange returns whether it stored and writes the value it found to its expected argument`: `Atomic.compare_exchange`
- `CrossGL has no spelling for this operation: CrossGL's lane match over the whole warp is CUDA's __match_all_sync, which also returns whether the lanes agree through a pointer`: `warp.match_all`
- `CrossGL has no spelling for this operation: no CrossGL function returns a quotient and a remainder together`: `divmod`
- `project.translate.mojo-refused: MojoRefusal: Mojo has no isinf for operands of type None; its isinf takes floating-point or integer values`: `ulp`

### Input

Refused, by diagnostic:

- `project.translate.undeclared-type: UndeclaredTypeError: type 'MutAnyOrigin' is not declared: it is neither a CrossGL built-in type nor a structure, enumeration, type alias or generic parameter of the program (target mojo) [project.translate.undeclared-type]` (312): `Atomic.compare_exchange`, `Atomic.fetch_add`, `Atomic.load`, `Atomic.max`, `Atomic.min`, `Atomic.store`, `abs`, `acos`, `acosh`, `aggregate-equality`, `aggregate-inout-parameter`, `align_down`, `align_up`, `array`, `array-copy`, `array-initializer`, `array-of-arrays`, `array-of-structs`, `array-parameter`, `array-return`, `asin`, `asinh`, `async_copy_arrive`, `atan`, `atan2`, `atanh`, `barrier`, `barrier-in-loop`, `bit_not`, `bit_reverse`, `bit_width`, `bitwise-logic`, `block-scope`, `block.broadcast`, `block.max`, `block.min`, `block.prefix_sum`, `block.sum`, `bool-array`, `bool-bitwise`, `bool-conversion`, `bool-vector-conversion`, `bool-vector-logic`, `boolean-logic`, `break`, `buffer-in-helper`, `byte_swap`, `call-result-access`, `cbrt`, `ceil`, `ceildiv`, `chained-assignment`, `chained-conditional`, `clamp`, `comb`, `compound-assignment`, `compute`, `condition-assignment`, `conditional-expression`, `conditional-side-effect`, `const-local`, `const-parameter`, `constant-array`, `constant-array-size`, `constant-expression`, `constant-struct`, `constant-vector-array`, `continue`, `control-attribute`, `copysign`, `cos`, `cosh`, `count_leading_zeros`, `count_trailing_zeros`, `cp_async_bulk_commit_group`, `cp_async_bulk_wait_group`, `default-argument`, `deferred-initialization`, `divmod`, `double`, `early-return`, `empty-statement`, `erf`, `erfc`, `exp`, `exp2`, `expm1`, `expression-swizzle`, `factorial`, `fence`, `float-arithmetic`, `float-comparison`, `float-loop-counter`, `float-remainder`, `float-to-integer`, `floor`, `fma`, `for-loop`, `for-loop-variants`, `forward-declaration`, `frexp`, `function-call`, `function-overloading`, `gamma`, `gcd`, `generic-function`, `global-constant`, `global-shadowing`, `half`, `hypot`, `if-else`, `implicit-conversion`, `indexed-compound-assignment`, `inf`, `infinite-loop`, `inout-argument-lvalues`, `inout-parameter`, `int16`, `int64`, `int8`, `integer-arithmetic`, `integer-buffer`, `integer-condition`, `integer-division`, `integer-literal-limits`, `integer-promotion`, `integer-to-float`, `integer-vector-arithmetic`, `integer-vector-comparison`, `intrinsic-name`, `invocation-id-in-helper`, `iota`, `isclose`, `isfinite`, `isinf`, `isnan`, `j0`, `j1`, `lane_id`, `lcm`, `ldexp`, `lgamma`, `local-invocation-id`, `local-invocation-index`, `log`, `log10`, `log1p`, `log2`, `log2_ceil`, `log2_floor`, `logb`, `loop-condition-call`, `loop-counter-write`, `loop-return`, `lvalue-increment`, `max`, `mbarrier_arrive`, `mbarrier_arrive_expect_tx_relaxed`, `mbarrier_arrive_expect_tx_shared`, `mbarrier_init`, `mbarrier_test_wait`, `mbarrier_try_wait_parity_shared`, `min`, `modf`, `mulhi`, `multi-variable-loop`, `multiple-declarators`, `mulwide`, `named_barrier`, `named_barrier_arrive`, `nan`, `negation`, `nested-call`, `nested-loop`, `nested-member-assignment`, `nested-struct`, `nested-struct-buffer`, `nested-unary`, `next_power_of_two`, `nextafter`, `num-subgroups`, `num-workgroups`, `numeric-literals`, `octal-literal`, `operator-precedence`, `out-parameter-forwarding`, `perm`, `pop_count`, `pow`, `prev_power_of_two`, `read-only-buffer`, `recip`, `remainder`, `reserved-global-name`, `reserved-identifier`, `reserved-member-name`, `rotate_bits_left`, `rotate_bits_right`, `round`, `rsqrt`, `s_waitcnt`, `s_waitcnt_barrier`, `scalb`, `schedule_barrier`, `schedule_group_barrier`, `shared-memory`, `shared-struct-array`, `shared-vector-array`, `short-circuit-logic`, `sibling-redeclaration`, `signed-comparison`, `signed-division`, `signed-shift`, `signed-to-unsigned`, `sin`, `sinh`, `sm_id`, `sqrt`, `struct`, `struct-array-buffer`, `struct-array-copy`, `struct-array-member`, `struct-array-parameter`, `struct-buffer`, `struct-buffer-copy`, `struct-buffer-packing`, `struct-conditional`, `struct-constructor`, `struct-copy`, `struct-method`, `struct-parameter`, `struct-return`, `struct-vector-member`, `subgroup-id`, `subgroup-invocation-id`, `subgroup-size`, `swizzle`, `syncwarp`, `tan`, `tanh`, `trunc`, `uint16`, `uint64`, `uint8`, `ulp`, `umma_arrive_leader_cta`, `umma_arrive_peer_cta`, `uniform-array`, `uniform-bool`, `uniform-bool-vector`, `uniform-buffer`, `uniform-cbuffer-vector`, `uniform-in-helper`, `uniform-integer`, `uniform-integer-vector`, `uniform-members`, `uniform-std140-array`, `uniform-std140-vector`, `uniform-struct`, `uniform-struct-array`, `uniform-struct-copy`, `uniform-unsigned`, `uniform-vector`, `uniform-vector-array`, `uniform-vector-packing`, `unreachable-statement`, `unsigned-buffer`, `unsigned-comparison`, `unsigned-countdown`, `unsigned-division`, `unsigned-float-conversion`, `unsigned-negation`, `unsigned-shift`, `unsigned-vector-arithmetic`, `unsigned-wraparound`, `value-parameter-mutation`, `vector-array`, `vector-bitwise`, `vector-buffer`, `vector-comparison`, `vector-compound-assignment`, `vector-conditional`, `vector-constructor`, `vector-conversion`, `vector-dynamic-index`, `vector-scalar-arithmetic`, `vector-scalar-product`, `vector-shift`, `vector-unary-operators`, `void-return`, `warp.broadcast`, `warp.lane_group_max`, `warp.lane_group_min`, `warp.lane_group_sum`, `warp.match_all`, `warp.match_any`, `warp.max`, `warp.min`, `warp.prefix_sum`, `warp.shuffle_down`, `warp.shuffle_idx`, `warp.shuffle_up`, `warp.shuffle_xor`, `warp.sum`, `warp.vote`, `warp_id`, `while-loop`, `workgroup-id`, `workgroup-size`, `y0`, `y1`, `zero-initializer`
- `project.translate.undeclared-type: UndeclaredTypeError: type 'dtype' is not declared: it is neither a CrossGL built-in type nor a structure, enumeration, type alias or generic parameter of the program (target mojo) [project.translate.undeclared-type]` (2): `warp.lane_group_reduce`, `warp.reduce`
- `project.translate.crossgl-function-body-parse-failed: CrossGLFunctionBodyParseError: CrossGL could not parse the body of function '<probe>' at COMMA ',': Expected RBRACKET, got COMMA ','`: `shared-2d-array`
- `project.translate.crossgl-syntax-error: CrossGLSyntaxError: Unexpected IDENTIFIER 'thread' in a shader declaration`: `reserved-type-name`
- `project.translate.mojo-import-unsupported: MojoImportRefused: CrossGL cannot represent N Mojo construct: the empty subscript '(outp + i).bitcast[Atomic[Int32]]()[]' has no CrossGL form: the importer cannot tell a pointer dereference from another type's __getitem__() (target cgl) [project.translate.mojo-import-unsupported]`: `Atomic.fetch_sub`
- `project.translate.mojo-import-unsupported: MojoImportRefused: CrossGL cannot represent N Mojo construct: the empty subscript 'p[]' has no CrossGL form: the importer cannot tell a pointer dereference from another type's __getitem__() (target cgl) [project.translate.mojo-import-unsupported]`: `pointer-local`
- `project.translate.mojo-import-unsupported: MojoImportRefused: CrossGL cannot represent N Mojo construct: the empty subscript 'x[]' has no CrossGL form: the importer cannot tell a pointer dereference from another type's __getitem__() (target cgl) [project.translate.mojo-import-unsupported]`: `buffer-element-argument`
- `project.translate.mojo-import-unsupported: MojoImportRefused: CrossGL cannot represent N Mojo constructs: the empty subscript 'p[]' has no CrossGL form: the importer cannot tell a pointer dereference from another type's __getitem__(); the empty subscript '(q + i)[]' has no CrossGL form: the importer cannot tell a pointer dereference from another type's __getit`: `pointer-arithmetic`
- `project.translate.undeclared-type: UndeclaredTypeError: type 'MutUntrackedOrigin' is not declared: it is neither a CrossGL built-in type nor a structure, enumeration, type alias or generic parameter of the program (target mojo) [project.translate.undeclared-type]`: `shared-memory-in-helper`
- `project.translate.undeclared-type: UndeclaredTypeError: type 'Real' is not declared: it is neither a CrossGL built-in type nor a structure, enumeration, type alias or generic parameter of the program (target mojo) [project.translate.undeclared-type]`: `type-alias`
