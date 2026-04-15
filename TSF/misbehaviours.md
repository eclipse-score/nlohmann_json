# Misbehaviours Report

This report lists known misbehaviours or bugs of version 3.12.0 of the nlohmann/json repository.
The misbehaviours are compiled from github issues of the nlohmann/json repository, and link to each corresponding issue.

## Open issues

### [#5135](https://github.com/nlohmann/json/issues/5135)
- **Title:** basic_json destructor allocates memory, violating noexcept semantics
- **State:** OPEN
- **Created At:** 2026-04-13T20:56:36Z



### [#5122](https://github.com/nlohmann/json/issues/5122)
- **Title:** Compilation error occurs when using nlohmann::ordered_map
- **State:** OPEN
- **Created At:** 2026-03-29T05:50:19Z



### [#5103](https://github.com/nlohmann/json/issues/5103)
- **Title:** Build issue when compiling with gcc (any modules-capable version) in a C++ modules project
- **State:** OPEN
- **Created At:** 2026-03-09T13:50:59Z



### [#5074](https://github.com/nlohmann/json/issues/5074)
- **Title:** Copy constructor changes semantics
- **State:** OPEN
- **Created At:** 2026-02-09T10:39:05Z



### [#5068](https://github.com/nlohmann/json/issues/5068)
- **Title:** Using json_pointer causes the warning of deprecated declarations
- **State:** OPEN
- **Created At:** 2026-02-04T04:05:50Z



### [#5066](https://github.com/nlohmann/json/issues/5066)
- **Title:** MSVC: unexpected behaviour converting from json to a rvalue reference of a variant containing a type that can be constructed from a string
- **State:** OPEN
- **Created At:** 2026-01-30T13:18:53Z



### [#5048](https://github.com/nlohmann/json/issues/5048)
- **Title:** function argument safety check silently optimized out in release build by clang
- **State:** OPEN
- **Created At:** 2026-01-07T22:27:57Z



### [#4996](https://github.com/nlohmann/json/issues/4996)
- **Title:** Tests don't build with VS 2026
- **State:** OPEN
- **Created At:** 2025-11-14T16:26:05Z



### [#4974](https://github.com/nlohmann/json/issues/4974)
- **Title:** [MSVC][build] JSON failed with error C2672: 'nlohmann::json_abi_v3_12_0::basic_json<std::map,std::vector,std::string,bool,int64_t,uint64_t,double,
- **State:** OPEN
- **Created At:** 2025-10-30T10:01:39Z



### [#4972](https://github.com/nlohmann/json/issues/4972)
- **Title:** Natvis file for version 3.12.0 does not contain a type definition for detail::json_default_base
- **State:** OPEN
- **Created At:** 2025-10-29T16:05:32Z



### [#4916](https://github.com/nlohmann/json/issues/4916)
- **Title:** Constructing array from C++20 ranges view does not work
- **State:** OPEN
- **Created At:** 2025-09-11T10:13:26Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Version 3.12.0 of nlohmann::json does not contain a constructor accepting std::views.


### [#4864](https://github.com/nlohmann/json/issues/4864)
- **Title:** C++17 std::optional feature not enabled
- **State:** OPEN
- **Created At:** 2025-07-28T16:11:42Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Using std::optional with nlohmann::json is broken in version 3.12.0, but shall be fixed in version 3.12.1.


### [#4813](https://github.com/nlohmann/json/issues/4813)
- **Title:** json::update() with merge_objects==true may trigger JSON_ASSERT for some objects
- **State:** OPEN
- **Created At:** 2025-06-09T14:01:42Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. This issue is observed under specific circumstances only; in particular, basic_json is not affected.


### [#4714](https://github.com/nlohmann/json/issues/4714)
- **Title:** Binary formats invalid encoding for <discarded> values in arrays and objects
- **State:** OPEN
- **Created At:** 2025-04-01T14:14:30Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Binary formats are creating broken outputs when discarded values are included in arrays/objects.


### [#4552](https://github.com/nlohmann/json/issues/4552)
- **Title:** UTF-8 invalid characters are not always ignored when dumping with error_handler_t::ignore
- **State:** OPEN
- **Created At:** 2024-12-17T15:49:31Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Invalid UTF-8 characters are not ignored when passing  error_handler_t::ignore to dump(); this issue is still open in version 3.12.0.


### [#4041](https://github.com/nlohmann/json/issues/4041)
- **Title:** NLOHMANN_DEFINE_TYPE_* fails with zero members
- **State:** OPEN
- **Created At:** 2023-05-23T19:27:59Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. This issue was observed in version 3.11.2; it is fixed in version 3.12.0.


### [#3907](https://github.com/nlohmann/json/issues/3907)
- **Title:** error: expected initializer before ‘<’ token 
- **State:** OPEN
- **Created At:** 2023-01-04T12:28:45Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Using CUDA with gcc as host compiler can lead to compiler errors. This issue still exists in version 3.12.0.


### [#3885](https://github.com/nlohmann/json/issues/3885)
- **Title:** meson build does not install nlohmann_json*.cmake files
- **State:** OPEN
- **Created At:** 2022-12-17T09:28:11Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Using meson instead of cmake to build the library does not work; use cmake to guarantee the expected outcome.


### [#3868](https://github.com/nlohmann/json/issues/3868)
- **Title:** [MSVC][std:c++latest] JSON failed with error C2678: binary '==': no operator found which takes a left-hand operand of type 'nlohmann::json_abi_v3_11_2::json'
- **State:** OPEN
- **Created At:** 2022-12-07T08:01:14Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. This issue regards the compatibility with the latest C++ standard.


### [#3859](https://github.com/nlohmann/json/issues/3859)
- **Title:** .value() with optional default value fails to compile
- **State:** OPEN
- **Created At:** 2022-12-02T12:28:33Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. json.value() with optional fallback value does not compile; this issue is still open in version 3.12.0.


### [#3732](https://github.com/nlohmann/json/issues/3732)
- **Title:** Using iteration_proxy_value with ordered_json fails to compile due to incomplete type
- **State:** OPEN
- **Created At:** 2022-09-08T09:39:38Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Using iteration_proxy_value with ordered_json as shown below fails to compile due to an incomplete type error in iterator set_parents(iterator it, typename iterator::difference_type count_set_parents); this issue still exists in version 3.12.0.


### [#3669](https://github.com/nlohmann/json/issues/3669)
- **Title:** invalid use of incomplete type (boost::optional) / compile error
- **State:** OPEN
- **Created At:** 2022-08-04T10:09:34Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. This issue was observed in version 3.10.3; it appears fixed in version 3.12.0.


### [#3583](https://github.com/nlohmann/json/issues/3583)
- **Title:** json destructor quite slow
- **State:** OPEN
- **Created At:** 2022-07-16T11:21:47Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. The performance of destroy() is quite slow.


### [#3578](https://github.com/nlohmann/json/issues/3578)
- **Title:** Unable to use gnu mpz types for NumberIntegerType
- **State:** OPEN
- **Created At:** 2022-07-11T13:53:24Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Custom number types with non-trivial destructors and move-constructors are not permitted.


### [#3425](https://github.com/nlohmann/json/issues/3425)
- **Title:** Conversion from alt_json to json produces incorrect result
- **State:** OPEN
- **Created At:** 2022-04-06T08:08:14Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. This issue is fixed in version 3.12.0 with the corresponding test in line 323 of unit-alt-string.cpp


### [#3381](https://github.com/nlohmann/json/issues/3381)
- **Title:** msgpack parser failed to parse null as Map key
- **State:** OPEN
- **Created At:** 2022-03-08T10:12:45Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Keys of objects are required to be strings; and the literal null is not a string.


### [#3106](https://github.com/nlohmann/json/issues/3106)
- **Title:** Use of JSON_DIAGNOSTICS through CMake and find_package()
- **State:** OPEN
- **Created At:** 2021-10-26T15:05:21Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Setting JSON_DIAGNOSTICS was broken in version 3.10.4.


### [#2649](https://github.com/nlohmann/json/issues/2649)
- **Title:** String type change breaks C++ type matching
- **State:** OPEN
- **Created At:** 2021-02-18T12:44:56Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. This issue was observed in version 3.9.1; it appears fixed in version 3.12.0.


### [#2226](https://github.com/nlohmann/json/issues/2226)
- **Title:** std::tuple dangling reference - implicit conversion
- **State:** OPEN
- **Created At:** 2020-06-27T12:04:41Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. std::tuple<const nlohmann::json&>::tuple(std::tuple<nlohmann::json&>&&) constructor creates a temporary object and a dangling reference. This issue still exists in version 3.12.0.



## Closed Issues (since version 3.12.0)

### [#5091](https://github.com/nlohmann/json/issues/5091)
- **Title:** The README section on creating JSON objects from literals contains wording that suggests file I/O but doesn't demonstrate it, and has a minor grammatical error.
- **State:** CLOSED
- **Created At:** 2026-03-03T06:24:30Z



### [#5060](https://github.com/nlohmann/json/issues/5060)
- **Title:** Segfault on x86_64 Android with Chromium libc++ in serializer::~serializer()
- **State:** CLOSED
- **Created At:** 2026-01-24T10:41:51Z



### [#5047](https://github.com/nlohmann/json/issues/5047)
- **Title:** [C++23] Error in json::parse with std::ifstream
- **State:** CLOSED
- **Created At:** 2026-01-07T07:43:37Z



### [#5046](https://github.com/nlohmann/json/issues/5046)
- **Title:** implicit conversion of return json to std::optional no longer implicit
- **State:** CLOSED
- **Created At:** 2026-01-06T16:50:46Z



### [#5036](https://github.com/nlohmann/json/issues/5036)
- **Title:** get enum with default value
- **State:** CLOSED
- **Created At:** 2025-12-20T07:06:56Z



### [#5023](https://github.com/nlohmann/json/issues/5023)
- **Title:** std::map and std::unordered_map serialization broken for keys of type std::u16string
- **State:** CLOSED
- **Created At:** 2025-12-03T12:02:24Z



### [#5013](https://github.com/nlohmann/json/issues/5013)
- **Title:** An object is used after it's moved
- **State:** CLOSED
- **Created At:** 2025-11-24T15:32:02Z



### [#5012](https://github.com/nlohmann/json/issues/5012)
- **Title:** error_handler_t::ignore documentation is incorrect
- **State:** CLOSED
- **Created At:** 2025-11-24T14:21:24Z



### [#5005](https://github.com/nlohmann/json/issues/5005)
- **Title:** Serialization of double type data gets stuck
- **State:** CLOSED
- **Created At:** 2025-11-20T09:28:12Z



### [#5002](https://github.com/nlohmann/json/issues/5002)
- **Title:** VS2026 Insiders, C2678 With C++23 Modules
- **State:** CLOSED
- **Created At:** 2025-11-18T20:45:50Z



### [#4946](https://github.com/nlohmann/json/issues/4946)
- **Title:** Failure with cmake 4.1
- **State:** CLOSED
- **Created At:** 2025-10-08T13:54:22Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Compatibility with CMake < 3.5 has been removed from CMake as of [CMake 4.0+](https://cmake.org/cmake/help/latest/command/cmake_minimum_required.html)


### [#4925](https://github.com/nlohmann/json/issues/4925)
- **Title:** Assertion error when converting to and from BJdata
- **State:** CLOSED
- **Created At:** 2025-09-19T18:41:56Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Optimized binary arrays have to be explicitly enabled when parsing from BJdata; otherwise an exception is thrown.


### [#4903](https://github.com/nlohmann/json/issues/4903)
- **Title:** LNK2005
- **State:** CLOSED
- **Created At:** 2025-08-24T08:50:37Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Defining the namespace "nlohmann" multiple times within the same project leads to an error.


### [#4901](https://github.com/nlohmann/json/issues/4901)
- **Title:** stack overflow
- **State:** CLOSED
- **Created At:** 2025-08-22T01:03:03Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Using json::from_ubjson() (cf. [here](https://json.nlohmann.me/api/basic_json/from_ubjson/)) on long nested inputs can lead to stack overflow.


### [#4898](https://github.com/nlohmann/json/issues/4898)
- **Title:** Different results on Linux vs Windows when using json["str"].push_back({json::object})
- **State:** CLOSED
- **Created At:** 2025-08-20T19:19:24Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Brace initialisation yields array, cf. [here](https://json.nlohmann.me/home/faq/#brace-initialization-yields-arrays).


### [#4892](https://github.com/nlohmann/json/issues/4892)
- **Title:** Feature request: please add separate "declaration" and "implementation" macros for enum serialization
- **State:** CLOSED
- **Created At:** 2025-08-18T12:47:43Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. This feature request is obsolete.


### [#4890](https://github.com/nlohmann/json/issues/4890)
- **Title:** Add fail-on-error: false for Coveralls CI step
- **State:** CLOSED
- **Created At:** 2025-08-15T11:12:40Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. If the coveralls service website is down, then the CI-pipeline fails by default.


### [#4882](https://github.com/nlohmann/json/issues/4882)
- **Title:** Tag 3.11.3 not poiting to right file
- **State:** CLOSED
- **Created At:** 2025-08-08T07:15:26Z



### [#4869](https://github.com/nlohmann/json/issues/4869)
- **Title:** CI fails on develop branch
- **State:** CLOSED
- **Created At:** 2025-07-29T05:52:07Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. The linkage of this [link](https://raw.githubusercontent.com/nlohmann/json/v3.11.3/single_include/nlohmann/json.hpp) pointed erroneously to version 3.12.0 for some time.


### [#4863](https://github.com/nlohmann/json/issues/4863)
- **Title:** LIBCPP_VERSION_OUTPUT breaks cross-compilation and is not used anywhere
- **State:** CLOSED
- **Created At:** 2025-07-28T13:24:02Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Shall be fixed in 3.12.1.


### [#4854](https://github.com/nlohmann/json/issues/4854)
- **Title:** `sax_parse` segfaults when given a null handler
- **State:** CLOSED
- **Created At:** 2025-07-24T06:27:18Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. nullptr as SAX handler is not explicitly handled, shall be fixed in 3.12.1.


### [#4852](https://github.com/nlohmann/json/issues/4852)
- **Title:** CONTRIBUTING.md does not mention required coding style or AStyle for contributors/reviewers
- **State:** CLOSED
- **Created At:** 2025-07-23T02:12:06Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. CONTRIBUTING.md does not mention the code style that is enforced for this project.


### [#4842](https://github.com/nlohmann/json/issues/4842)
- **Title:** json destructor does not use the provided allocator
- **State:** CLOSED
- **Created At:** 2025-07-04T10:02:34Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Instead of the provided allocator, the standard allocator is used in the non-recursive destructor.


### [#4834](https://github.com/nlohmann/json/issues/4834)
- **Title:** Problems with std::optional
- **State:** CLOSED
- **Created At:** 2025-06-27T18:57:10Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Using std::optional with nlohmann::json is broken in version 3.12.0, but shall be fixed in version 3.12.1.


### [#4828](https://github.com/nlohmann/json/issues/4828)
- **Title:** merge json : arrays not appended?
- **State:** CLOSED
- **Created At:** 2025-06-22T12:34:48Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Cryptic issue with joining objects on keys, no minimal working example provided.


### [#4826](https://github.com/nlohmann/json/issues/4826)
- **Title:** MSVC: warning C5260: for constexpr variables defined in to_chars.hpp
- **State:** CLOSED
- **Created At:** 2025-06-18T10:19:55Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Issue closed due to inactivity.


### [#4825](https://github.com/nlohmann/json/issues/4825)
- **Title:** Template instantiation of nlohmann::basic_json<> fails on C++17
- **State:** CLOSED
- **Created At:** 2025-06-18T08:45:26Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. template class nlohmann::basic_json<>; leads to a compilation error "ambigious static_caststd::string" inside binary_writer::write_bjdata_ndarray.


### [#4821](https://github.com/nlohmann/json/issues/4821)
- **Title:** open parse adds extra array
- **State:** CLOSED
- **Created At:** 2025-06-17T08:45:02Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Cf. https://json.nlohmann.me/home/faq/#brace-initialization-yields-arrays


### [#4819](https://github.com/nlohmann/json/issues/4819)
- **Title:** gcc 14.2 bug: array subscript out of bounds with `JSON_DIAGNOSTICS`
- **State:** CLOSED
- **Created At:** 2025-06-16T11:20:55Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. This is a bug in gcc 14.2, which will not be suppressed by the library.


### [#4812](https://github.com/nlohmann/json/issues/4812)
- **Title:** BUG：A string containing binary data that is converted to a json variable
- **State:** CLOSED
- **Created At:** 2025-06-06T10:41:15Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Only binary formats like CBOR or MessagePack allow writing and reading binary values; no misbehaviour.


### [#4810](https://github.com/nlohmann/json/issues/4810)
- **Title:** Allocator Propagation Issues with std::pmr in nlohmann::json: Limitations
- **State:** CLOSED
- **Created At:** 2025-06-05T10:27:20Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. nlohmann::json currently does not allow selecting a custom allocator.


### [#4804](https://github.com/nlohmann/json/issues/4804)
- **Title:** `from_cbor` incompatible with `std::vector<std::byte>` as `binary_t`
- **State:** CLOSED
- **Created At:** 2025-06-01T12:22:09Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Trying to use json::from_cbor with a binary_t set to std::vector\<std::byte> will fail.


### [#4798](https://github.com/nlohmann/json/issues/4798)
- **Title:** nlohmann::json::to_msgpack() encode float NaN as double
- **State:** CLOSED
- **Created At:** 2025-05-28T13:44:49Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. The float value is encoded to msgpack as double if it contains float NaN or infinity.


### [#4792](https://github.com/nlohmann/json/issues/4792)
- **Title:** Compilation failure with nvc++
- **State:** CLOSED
- **Created At:** 2025-05-22T16:04:21Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. C++20 support of NVHPC 25.5 is broken.


### [#4780](https://github.com/nlohmann/json/issues/4780)
- **Title:** `j.get_to(my_struct)` fails to compile for types with `std::optional`
- **State:** CLOSED
- **Created At:** 2025-05-10T01:53:53Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. The conversion from JSON to std::optional does not work.


### [#4778](https://github.com/nlohmann/json/issues/4778)
- **Title:** Deprecation warning with gcc 15.1.1: struct std::is_trivial’ is deprecated
- **State:** CLOSED
- **Created At:** 2025-05-09T10:54:58Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. std::is_trivial is deprecated in C++26, using GCC 15.1.1 produces a deprecation warning.


### [#4762](https://github.com/nlohmann/json/issues/4762)
- **Title:** json exception 302 with unhelpful explanation : type must be number, but is number
- **State:** CLOSED
- **Created At:** 2025-04-27T12:52:45Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Default return value for type_name() is number, which makes some error messages more than cryptic.


### [#4759](https://github.com/nlohmann/json/issues/4759)
- **Title:** Compiler error `exposes TU-local entity` on gcc-trunk while compiling the library as a module
- **State:** CLOSED
- **Created At:** 2025-04-25T13:10:11Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Wrapping the library into a module fails due to `static` in lines 9832 and 3132.


### [#4756](https://github.com/nlohmann/json/issues/4756)
- **Title:** Incompatibility of std::char_traits and std::byte in Xcode 16.3
- **State:** CLOSED
- **Created At:** 2025-04-23T14:44:07Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. nlohmann::ordered_json::from_msgpack() does not work with buffer of type std::vector\<std::byte\> using Xcode 16.3 and C++20.


### [#4755](https://github.com/nlohmann/json/issues/4755)
- **Title:** Fix cppcheck 1.5.1 warning
- **State:** CLOSED
- **Created At:** 2025-04-23T12:52:31Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. The serialization of floating-point numbers is handled in two code paths. If number_float_t is double or long_double, then no issue arises.


### [#4746](https://github.com/nlohmann/json/issues/4746)
- **Title:** Scope/Unscope should not include #pragma once
- **State:** CLOSED
- **Created At:** 2025-04-16T07:18:37Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. If you do not use the single_include json.hpp as intended, then the library may not quite work as intended.


### [#4745](https://github.com/nlohmann/json/issues/4745)
- **Title:** [MSVC] [std:c++latest] Warning C4702 after updating to json 3.12.0 with Visual Studio 2022 17.12.7
- **State:** CLOSED
- **Created At:** 2025-04-15T14:10:37Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Compiling version 3.12.0 with /std:c++ latest in Visual Studio 2022 17.12.7 raises compiler errors.


### [#4740](https://github.com/nlohmann/json/issues/4740)
- **Title:** Build issue with std::optional
- **State:** CLOSED
- **Created At:** 2025-04-13T16:36:58Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Using std::optional with nlohmann::json is broken in version 3.12.0, but shall be fixed in version 3.12.1.


### [#4733](https://github.com/nlohmann/json/issues/4733)
- **Title:** Clang 11.0.x compilation error
- **State:** CLOSED
- **Created At:** 2025-04-11T13:25:53Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Clang 11.0.x with libc++ fails to compile tests in C++20 mode due to incomplete char8_t support in std::filesystem::path.


