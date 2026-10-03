# Misbehaviours Report

This report lists known misbehaviours or bugs of version 3.12.0 of the nlohmann/json repository.
The misbehaviours are compiled from github issues of the nlohmann/json repository, and link to each corresponding issue.

## Open issues

### [#5742](https://github.com/nlohmann/json/issues/5742)
- **Title:** Release build fails when JSON diagnostics enabled
- **State:** OPEN
- **Created At:** 2026-09-30T21:24:40Z



### [#5674](https://github.com/nlohmann/json/issues/5674)
- **Title:** Copy-constructing basic_json now requires an assignable CustomBaseClass (compile regression)
- **State:** OPEN
- **Created At:** 2026-09-29T17:55:26Z



### [#5673](https://github.com/nlohmann/json/issues/5673)
- **Title:** ordered_json::emplace(key, value) does not compile when value is an lvalue
- **State:** OPEN
- **Created At:** 2026-09-29T17:55:20Z



### [#5672](https://github.com/nlohmann/json/issues/5672)
- **Title:** With JSON_NOEXCEPTION, value(json_pointer, default) aborts for some array tokens
- **State:** OPEN
- **Created At:** 2026-09-29T17:55:13Z



### [#5665](https://github.com/nlohmann/json/issues/5665)
- **Title:** Legacy discarded comparison in C++20: scalar <= discarded and scalar >= discarded yield false
- **State:** OPEN
- **Created At:** 2026-09-29T17:54:27Z



### [#5663](https://github.com/nlohmann/json/issues/5663)
- **Title:** Keys convertible to std::string_view break at/find/contains, including keys that worked in 3.12.0
- **State:** OPEN
- **Created At:** 2026-09-29T17:54:14Z



### [#5662](https://github.com/nlohmann/json/issues/5662)
- **Title:** JSON_BRACE_INIT_COPY_SEMANTICS: json j{arr} turns an array like ["key", 42] into an object
- **State:** OPEN
- **Created At:** 2026-09-29T17:54:07Z



### [#5661](https://github.com/nlohmann/json/issues/5661)
- **Title:** BJData ND-array annotations are not parsed back into the same object ("single" precision, ordered_json key order)
- **State:** OPEN
- **Created At:** 2026-09-29T17:54:00Z



### [#5660](https://github.com/nlohmann/json/issues/5660)
- **Title:** Floats are truncated at the decimal point under locales with a multi-byte decimal point (fa_IR.UTF-8)
- **State:** OPEN
- **Created At:** 2026-09-29T17:53:53Z



### [#5659](https://github.com/nlohmann/json/issues/5659)
- **Title:** A NUL byte that ends a // comment does not end the input with the default NUL handling
- **State:** OPEN
- **Created At:** 2026-09-29T17:53:47Z



### [#5654](https://github.com/nlohmann/json/issues/5654)
- **Title:** C++20 operator<=> result depends on nesting depth when binary values differ only in subtype
- **State:** OPEN
- **Created At:** 2026-09-29T17:53:14Z



### [#5651](https://github.com/nlohmann/json/issues/5651)
- **Title:** Binary writers emit strings with ill-formed UTF-8 that the corresponding readers reject
- **State:** OPEN
- **Created At:** 2026-09-29T17:52:54Z



### [#5649](https://github.com/nlohmann/json/issues/5649)
- **Title:** Deep copy (nested 128+ levels) drops the object comparator's state: keys reordered or lost
- **State:** OPEN
- **Created At:** 2026-09-29T17:52:41Z



### [#5648](https://github.com/nlohmann/json/issues/5648)
- **Title:** from_bon8(ptr, len) and from_bjdata(ptr, len) compile without a warning and read ptr as a NUL-terminated string
- **State:** OPEN
- **Created At:** 2026-09-29T17:52:35Z



### [#5645](https://github.com/nlohmann/json/issues/5645)
- **Title:** Wide-string input: lone UTF-16 surrogates and negative wchar_t units are accepted or end the input
- **State:** OPEN
- **Created At:** 2026-09-29T17:52:15Z



### [#5529](https://github.com/nlohmann/json/issues/5529)
- **Title:** from_cbor()/from_msgpack() do not validate UTF-8 in text strings at decode time (only dump() does)
- **State:** OPEN
- **Created At:** 2026-09-15T05:12:35Z



### [#5400](https://github.com/nlohmann/json/issues/5400)
- **Title:** std::hash<basic_json> is inconsistent with operator== for equal cross-type numbers (breaks unordered containers)
- **State:** OPEN
- **Created At:** 2026-08-25T23:00:36Z



### [#5256](https://github.com/nlohmann/json/issues/5256)
- **Title:** Int and uint compare equal but hashes do not
- **State:** OPEN
- **Created At:** 2026-07-09T11:02:19Z



### [#5135](https://github.com/nlohmann/json/issues/5135)
- **Title:** basic_json destructor allocates memory, violating noexcept semantics
- **State:** OPEN
- **Created At:** 2026-04-13T20:56:36Z



### [#5066](https://github.com/nlohmann/json/issues/5066)
- **Title:** MSVC: unexpected behaviour converting from json to a rvalue reference of a variant containing a type that can be constructed from a string
- **State:** OPEN
- **Created At:** 2026-01-30T13:18:53Z



### [#4972](https://github.com/nlohmann/json/issues/4972)
- **Title:** Natvis file for version 3.12.0 does not contain a type definition for detail::json_default_base
- **State:** OPEN
- **Created At:** 2025-10-29T16:05:32Z



### [#4842](https://github.com/nlohmann/json/issues/4842)
- **Title:** json destructor does not use the provided allocator
- **State:** OPEN
- **Created At:** 2025-07-04T10:02:34Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Instead of the provided allocator, the standard allocator is used in the non-recursive destructor.


### [#4714](https://github.com/nlohmann/json/issues/4714)
- **Title:** Binary formats invalid encoding for <discarded> values in arrays and objects
- **State:** OPEN
- **Created At:** 2025-04-01T14:14:30Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Binary formats are creating broken outputs when discarded values are included in arrays/objects.


### [#3885](https://github.com/nlohmann/json/issues/3885)
- **Title:** meson build does not install nlohmann_json*.cmake files
- **State:** OPEN
- **Created At:** 2022-12-17T09:28:11Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Using meson instead of cmake to build the library does not work; use cmake to guarantee the expected outcome.


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


### [#2649](https://github.com/nlohmann/json/issues/2649)
- **Title:** String type change breaks C++ type matching
- **State:** OPEN
- **Created At:** 2021-02-18T12:44:56Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. This issue was observed in version 3.9.1; it appears fixed in version 3.12.0.



## Closed Issues (since version 3.12.0)

### [#5675](https://github.com/nlohmann/json/issues/5675)
- **Title:** to_bson: out_of_range.415 has no JSON_DIAGNOSTICS context and is thrown after part of the document was written
- **State:** CLOSED
- **Created At:** 2026-09-29T17:55:33Z



### [#5671](https://github.com/nlohmann/json/issues/5671)
- **Title:** Default enum conversion: an enum with underlying type bool can be serialized but not deserialized
- **State:** CLOSED
- **Created At:** 2026-09-29T17:55:07Z



### [#5670](https://github.com/nlohmann/json/issues/5670)
- **Title:** basic_json(first, last) ignores the iterator range for binary values
- **State:** CLOSED
- **Created At:** 2026-09-29T17:55:00Z



### [#5669](https://github.com/nlohmann/json/issues/5669)
- **Title:** clear() on a binary value keeps the subtype
- **State:** CLOSED
- **Created At:** 2026-09-29T17:54:54Z



### [#5668](https://github.com/nlohmann/json/issues/5668)
- **Title:** JSON_DIAGNOSTICS: wrong path for std::map/unordered_map with non-string keys (container, not element)
- **State:** CLOSED
- **Created At:** 2026-09-29T17:54:47Z



### [#5667](https://github.com/nlohmann/json/issues/5667)
- **Title:** NLOHMANN_JSON_SERIALIZE_ENUM_STRICT: from_json's message breaks for invalid UTF-8 and custom string_t
- **State:** CLOSED
- **Created At:** 2026-09-29T17:54:41Z



### [#5666](https://github.com/nlohmann/json/issues/5666)
- **Title:** contains(json_pointer) and json_pointer / size_t fail to compile with a conforming custom StringType
- **State:** CLOSED
- **Created At:** 2026-09-29T17:54:34Z



### [#5664](https://github.com/nlohmann/json/issues/5664)
- **Title:** ordered_json::value(json_pointer, default) emits the deprecated json_pointer/string operator== warning
- **State:** CLOSED
- **Created At:** 2026-09-29T17:54:20Z



### [#5658](https://github.com/nlohmann/json/issues/5658)
- **Title:** JSON_STRICT_NUL_HANDLING rejects wide, UTF-16, UTF-32, and UTF-8 string literals such as L"[1]"
- **State:** CLOSED
- **Created At:** 2026-09-29T17:53:40Z



### [#5657](https://github.com/nlohmann/json/issues/5657)
- **Title:** contains(0), find(0), and count(0) compile and crash by constructing the key from a null pointer
- **State:** CLOSED
- **Created At:** 2026-09-29T17:53:33Z



### [#5656](https://github.com/nlohmann/json/issues/5656)
- **Title:** insert(pos, initializer_list) inserts wrong values if the list refers to the array's own elements
- **State:** CLOSED
- **Created At:** 2026-09-29T17:53:27Z



### [#5655](https://github.com/nlohmann/json/issues/5655)
- **Title:** operator== depends on nesting depth for object types whose comparator treats unequal keys as equivalent
- **State:** CLOSED
- **Created At:** 2026-09-29T17:53:21Z



### [#5653](https://github.com/nlohmann/json/issues/5653)
- **Title:** swap() does not exchange the CustomBaseClass subobject, unlike copy and assignment
- **State:** CLOSED
- **Created At:** 2026-09-29T17:53:07Z



### [#5652](https://github.com/nlohmann/json/issues/5652)
- **Title:** Failed operator>> leaves a partial value in its target, which breaks the JSON_DIAGNOSTICS invariant
- **State:** CLOSED
- **Created At:** 2026-09-29T17:53:01Z



### [#5650](https://github.com/nlohmann/json/issues/5650)
- **Title:** Converting between basic_json specializations (e.g. json to ordered_json) overflows the stack on deep input
- **State:** CLOSED
- **Created At:** 2026-09-29T17:52:48Z



### [#5647](https://github.com/nlohmann/json/issues/5647)
- **Title:** operator[](size_type) with SIZE_MAX empties the array and writes out of bounds
- **State:** CLOSED
- **Created At:** 2026-09-29T17:52:28Z



### [#5646](https://github.com/nlohmann/json/issues/5646)
- **Title:** Parsing an istream: std::terminate with exceptions(eofbit), null dereference without a streambuf
- **State:** CLOSED
- **Created At:** 2026-09-29T17:52:22Z



### [#5644](https://github.com/nlohmann/json/issues/5644)
- **Title:** to_msgpack writes wrong integers when number_integer_t is narrower than number_unsigned_t
- **State:** CLOSED
- **Created At:** 2026-09-29T17:52:08Z



### [#5643](https://github.com/nlohmann/json/issues/5643)
- **Title:** Parser callback is still called inside a discarded container, and that container's keys are kept in memory
- **State:** CLOSED
- **Created At:** 2026-09-29T17:52:02Z



### [#5642](https://github.com/nlohmann/json/issues/5642)
- **Title:** to_json(std::optional<T>) is noexcept: an exception from the contained value calls std::terminate
- **State:** CLOSED
- **Created At:** 2026-09-29T17:51:55Z



### [#5641](https://github.com/nlohmann/json/issues/5641)
- **Title:** update() and merge_patch() use freed memory when the argument is the value itself or a descendant
- **State:** CLOSED
- **Created At:** 2026-09-29T17:51:49Z



### [#5640](https://github.com/nlohmann/json/issues/5640)
- **Title:** Deep copy of a value nested more than 128 levels crashes when an allocation fails
- **State:** CLOSED
- **Created At:** 2026-09-29T17:51:42Z



### [#5639](https://github.com/nlohmann/json/issues/5639)
- **Title:** diff() removes and re-adds every member of a json object when a new key sorts before an existing one
- **State:** CLOSED
- **Created At:** 2026-09-29T17:51:36Z



### [#5530](https://github.com/nlohmann/json/issues/5530)
- **Title:** A trailing NUL byte after a complete JSON value silently truncates parsing instead of raising a trailing-data error
- **State:** CLOSED
- **Created At:** 2026-09-15T05:12:50Z



### [#5453](https://github.com/nlohmann/json/issues/5453)
- **Title:** BSON parser stack overflow on deeply nested documents (no recursion depth limit)
- **State:** CLOSED
- **Created At:** 2026-09-01T07:02:17Z



### [#5452](https://github.com/nlohmann/json/issues/5452)
- **Title:** UBJSON parser stack overflow on deeply nested arrays (no recursion depth limit)
- **State:** CLOSED
- **Created At:** 2026-09-01T06:59:33Z



### [#5451](https://github.com/nlohmann/json/issues/5451)
- **Title:** CBOR parser stack overflow on deeply nested arrays (no recursion depth limit)
- **State:** CLOSED
- **Created At:** 2026-09-01T06:56:33Z



### [#5408](https://github.com/nlohmann/json/issues/5408)
- **Title:** Four JSON_HEDLEY_* macros leak into user code (PRAGMA, PREDICT_TRUE, PREDICT_FALSE, CLANG_HAS_DECLSPEC_ATTRIBUTE) — not undefined by hedley_undef.hpp
- **State:** CLOSED
- **Created At:** 2026-08-26T10:32:25Z



### [#5407](https://github.com/nlohmann/json/issues/5407)
- **Title:** accept()'s current overloads are missing JSON_HEDLEY_WARN_UNUSED_RESULT (present on parse() and on the deprecated accept() overload)
- **State:** CLOSED
- **Created At:** 2026-08-26T10:32:02Z



### [#5404](https://github.com/nlohmann/json/issues/5404)
- **Title:** to_bjdata() emits the Draft-3-only 'B' (byte) marker for _ArrayType_:"byte" even in default Draft-2 mode, and the value does not round-trip
- **State:** CLOSED
- **Created At:** 2026-08-25T23:01:40Z



### [#5403](https://github.com/nlohmann/json/issues/5403)
- **Title:** to_bjdata() silently truncates out-of-range _ArrayData_ elements (e.g. 256 as uint8 becomes 0)
- **State:** CLOSED
- **Created At:** 2026-08-25T23:01:23Z



### [#5402](https://github.com/nlohmann/json/issues/5402)
- **Title:** update(src, merge_objects=true) throws type_error.312 when a shared key is a primitive in the target and an object in the source
- **State:** CLOSED
- **Created At:** 2026-08-25T23:01:08Z



### [#5401](https://github.com/nlohmann/json/issues/5401)
- **Title:** Mixed integer/float comparison near 2^63 is intransitive, violating strict-weak-ordering (std::sort/std::set on such values is UB)
- **State:** CLOSED
- **Created At:** 2026-08-25T23:00:54Z



### [#5399](https://github.com/nlohmann/json/issues/5399)
- **Title:** to_bjdata() emits output it cannot itself parse when _ArraySize_ is null or an object (round-trip guarantee violated)
- **State:** CLOSED
- **Created At:** 2026-08-25T23:00:16Z



### [#5398](https://github.com/nlohmann/json/issues/5398)
- **Title:** to_bjdata() throws type_error.302 on a non-string _ArrayType_ instead of falling back to a plain object encoding
- **State:** CLOSED
- **Created At:** 2026-08-25T22:59:55Z



### [#5397](https://github.com/nlohmann/json/issues/5397)
- **Title:** JSON Patch "move" where "from" is a proper prefix of "path" succeeds with a wrong result (RFC 6902 §4.4 violation)
- **State:** CLOSED
- **Created At:** 2026-08-25T22:59:38Z



### [#5396](https://github.com/nlohmann/json/issues/5396)
- **Title:** JSON Patch "remove" silently succeeds (no-op) when the target's parent is a primitive or null (RFC 6902 §4.2 violation)
- **State:** CLOSED
- **Created At:** 2026-08-25T22:59:25Z



### [#5395](https://github.com/nlohmann/json/issues/5395)
- **Title:** contains(json_pointer) throws on out-of-range numeric array tokens, contradicting its documented "does not throw exceptions"
- **State:** CLOSED
- **Created At:** 2026-08-25T22:59:09Z



### [#5387](https://github.com/nlohmann/json/issues/5387)
- **Title:** Stack overflow in copy constructor and dump() on deeply nested json (destructor was fixed in #1436)
- **State:** CLOSED
- **Created At:** 2026-08-20T12:19:14Z



### [#5371](https://github.com/nlohmann/json/issues/5371)
- **Title:** C28619 warning in lexer.hpp with Visual Studio 2022 / C++20
- **State:** CLOSED
- **Created At:** 2026-08-10T08:38:48Z



### [#5288](https://github.com/nlohmann/json/issues/5288)
- **Title:** Deprecation warning for operator== when using ordered_json when building with clang
- **State:** CLOSED
- **Created At:** 2026-07-22T10:06:53Z



### [#5210](https://github.com/nlohmann/json/issues/5210)
- **Title:** Mixed comparison bug: number_unsigned (INT64_MAX+1~UINT64_MAX) vs number_integer
- **State:** CLOSED
- **Created At:** 2026-06-17T16:49:21Z



### [#5198](https://github.com/nlohmann/json/issues/5198)
- **Title:** TOCTOU race between lexer construction and locale changes causes float truncation
- **State:** CLOSED
- **Created At:** 2026-05-30T17:11:17Z



### [#5197](https://github.com/nlohmann/json/issues/5197)
- **Title:** MSVC std c++23 u8string can not be correctly stored in json
- **State:** CLOSED
- **Created At:** 2026-05-30T05:00:23Z



### [#5175](https://github.com/nlohmann/json/issues/5175)
- **Title:** Test "dump for basic_json with long double number_float_t" fails when run with Valgrind
- **State:** CLOSED
- **Created At:** 2026-05-16T08:01:07Z



### [#5122](https://github.com/nlohmann/json/issues/5122)
- **Title:** Compilation error occurs when using nlohmann::ordered_map
- **State:** CLOSED
- **Created At:** 2026-03-29T05:50:19Z



### [#5103](https://github.com/nlohmann/json/issues/5103)
- **Title:** Build issue when compiling with gcc (any modules-capable version) in a C++ modules project
- **State:** CLOSED
- **Created At:** 2026-03-09T13:50:59Z



### [#5091](https://github.com/nlohmann/json/issues/5091)
- **Title:** The README section on creating JSON objects from literals contains wording that suggests file I/O but doesn't demonstrate it, and has a minor grammatical error.
- **State:** CLOSED
- **Created At:** 2026-03-03T06:24:30Z



### [#5074](https://github.com/nlohmann/json/issues/5074)
- **Title:** Copy constructor changes semantics
- **State:** CLOSED
- **Created At:** 2026-02-09T10:39:05Z



### [#5068](https://github.com/nlohmann/json/issues/5068)
- **Title:** Using json_pointer causes the warning of deprecated declarations
- **State:** CLOSED
- **Created At:** 2026-02-04T04:05:50Z



### [#5060](https://github.com/nlohmann/json/issues/5060)
- **Title:** Segfault on x86_64 Android with Chromium libc++ in serializer::~serializer()
- **State:** CLOSED
- **Created At:** 2026-01-24T10:41:51Z



### [#5048](https://github.com/nlohmann/json/issues/5048)
- **Title:** function argument safety check silently optimized out in release build by clang
- **State:** CLOSED
- **Created At:** 2026-01-07T22:27:57Z



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



### [#4996](https://github.com/nlohmann/json/issues/4996)
- **Title:** Tests don't build with VS 2026
- **State:** CLOSED
- **Created At:** 2025-11-14T16:26:05Z



### [#4974](https://github.com/nlohmann/json/issues/4974)
- **Title:** [MSVC][build] JSON failed with error C2672: 'nlohmann::json_abi_v3_12_0::basic_json<std::map,std::vector,std::string,bool,int64_t,uint64_t,double,
- **State:** CLOSED
- **Created At:** 2025-10-30T10:01:39Z



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


### [#4916](https://github.com/nlohmann/json/issues/4916)
- **Title:** Constructing array from C++20 ranges view does not work
- **State:** CLOSED
- **Created At:** 2025-09-11T10:13:26Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Version 3.12.0 of nlohmann::json does not contain a constructor accepting std::views.


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


### [#4864](https://github.com/nlohmann/json/issues/4864)
- **Title:** C++17 std::optional feature not enabled
- **State:** CLOSED
- **Created At:** 2025-07-28T16:11:42Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. Using std::optional with nlohmann::json is broken in version 3.12.0, but shall be fixed in version 3.12.1.


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


### [#4813](https://github.com/nlohmann/json/issues/4813)
- **Title:** json::update() with merge_objects==true may trigger JSON_ASSERT for some objects
- **State:** CLOSED
- **Created At:** 2025-06-09T14:01:42Z

- **Comment:** This issue does not apply to the use of nlohmann/json in Eclipse S-CORE. This issue is observed under specific circumstances only; in particular, basic_json is not affected.


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


