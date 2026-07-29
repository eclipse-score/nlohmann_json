# Sample of closed upstream misbehaviours (pre-3.12.0)

This file collects and comments a **sample** of *20 closed* upstream bug issues from the original [`nlohmann/json`](https://github.com/nlohmann/json) repository.

Selection criteria:
- Issue is **closed** and labeled **`kind: bug`** upstream.
- Issue was **closed before** the upstream release of **v3.12.0** (published at `2025-04-11`).
- A **random sample of 20** issues was taken from the upstream query: [closed `kind: bug` before v3.12.0](https://github.com/nlohmann/json/issues?q=is%3Aissue+is%3Aclosed+label%3A%22kind%3A+bug%22+closed%3A%3C2025-04-11)

## sampled closed misbehaviours

issue-id | applies to S-CORE | problem | resolution | closed after
---------|-------------------|---------|------------|-------------
[2147](https://github.com/nlohmann/json/issues/2147) | No | Compilation error report for very old GCC (4.8.5) with `std::bind`/`std::function`. | Was labeled as a compiler bug; closed as stale after no further comment from author after trial of workaround. | 2.5 months
[2574](https://github.com/nlohmann/json/issues/2574) | No | `get<std::array<T,N>>()` fails for non-default-constructible element types. | Was fixed in https://github.com/nlohmann/json/pull/2576 and ticket closed after release in 3.10. | 3.5 months
[2655](https://github.com/nlohmann/json/issues/2655) | No | `std::pair` serialization expectation mismatch, object serialized instead of arrays. | Documentation updated to better explain behaviour. | 5 months
[2676](https://github.com/nlohmann/json/issues/2676) | No | NVCC warnings when instantiating templates under CUDA. | Was fixed in https://github.com/nlohmann/json/pull/3227 after release in 3.10.5. | 10 months
[2725](https://github.com/nlohmann/json/issues/2725) | No | Build with `-fno-exceptions` (and/or `JSON_NOEXCEPTIONS`) still hits `throw`. | Was already fixed in https://github.com/nlohmann/json/pull/2347. | the same day
[3025](https://github.com/nlohmann/json/issues/3025) | No | Brace-initialization in function calls was reported to select a copy path (`func({j});` prints `10` instead of `[10]`). | Was a duplicate of https://github.com/nlohmann/json/issues/2311 and that issue was declared not a bug and solved by referencing to Docu. | next day
[3156](https://github.com/nlohmann/json/issues/3156) | No | `std::filesystem::path` conversions unavailable for older macOS deployment targets even with C++17. | Was already solved in https://github.com/nlohmann/json/pull/3101. | the same day
[3542](https://github.com/nlohmann/json/issues/3542) | No | AddressSanitizer container-overflow report in diagnostics code path on Windows/MSVC test configuration. | Was declared bug of MSSTL outside of nlohmann/json. | 2.5 years
[3704](https://github.com/nlohmann/json/issues/3704) | No | `operator[]`/`.at()` to `std::string const&` binds a temporary; use `get_ref` for a real reference. | Was not a bug but expected behaviour. | the same day
[4019](https://github.com/nlohmann/json/issues/4019) | No | `flatten()` fails to compile when using an alternative string type. | Issue was confirmed and fixed upstream in https://github.com/nlohmann/json/pull/4613. | 21 months
[4066](https://github.com/nlohmann/json/issues/4066) | No | Parsing freeze reported on a constrained platform (Nintendo Switch) with a larger JSON input. | Author identified problem in own code. | within 1 day
[4116](https://github.com/nlohmann/json/issues/4116) | No | GCC `-Wodr` warning about potential ODR violations in the single-header build. | Author identified it as issue of other library tinygltf. | the same day
[4163](https://github.com/nlohmann/json/issues/4163) | No | Deprecation warning about `std::char_traits<unsigned char>` when parsing binary formats from `std::vector<std::uint8_t>`. | Was fixed in https://github.com/nlohmann/json/pull/4179. | 2 months
[4193](https://github.com/nlohmann/json/issues/4193) | No | Exception SIGSEGV reported while parsing a valid JSON file from a stream. | Was declared issue of compiler. | the same day
[4241](https://github.com/nlohmann/json/issues/4241) | No | `#include <version>` was reported to be shadowed by a project-provided header named `version` on the include path. | Declared issue of the calling library not adhering to standard. | the same day
[4284](https://github.com/nlohmann/json/issues/4284) | No | `#pragma pack(push, 1)` was reported to break compilation units and lead to a segfault if packing is not restored. | Was declared not a bug but user error. | within 1 week
[4299](https://github.com/nlohmann/json/issues/4299) | No | Single-element `std::initializer_list` construction was reported to yield an array for strings (e.g., `json{"hello"}`). | Was declared not a bug but user error. | the same day
[4332](https://github.com/nlohmann/json/issues/4332) | No | Hex-like git ref string reported as number overflow. | Author realised themselves that it was user error. | the same day
[4427](https://github.com/nlohmann/json/issues/4427) | No | Misfiled "CVE" report describing a Python `jaraco/zipp` issue for possible DoS Attack. | Was declared not a bug. | the same day
[4467](https://github.com/nlohmann/json/issues/4467) | No | Error C2440 report with little context given. | Author realised themselves that it was user error. | within 1 week

## Conclusion

The analysis of a random sample of 20 closed upstream misbehaviours showed that misbehaviours were addressed appropriately and closed in a reasonable timeframe.
