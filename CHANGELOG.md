## 1.14.0

### Core library changes
* `dart:math`
  * `Random` added a `secure` constructor returning a cryptographically secure
    random generator which reads from the entropy source provided by the
    embedder for every generated random value.

## 1.13.0

### Core library changes
* `dart:async`
  * `StreamTransformer` instances created with `fromHandlers` with no
    `handleError` callback now forward stack traces along with errors to the
    resulting streams.

* `dart:core`
  * `Uri` added `removeFragment` method.
  * `String.allMatches` (implementing `Pattern.allMatches`) is now lazy,
    as all `allMatches` implementations are intended to be.
  * `Resource` is deprecated in favor of the resource package.
    See https://pub.dartlang.org/packages/resource to learn more. This is
    the last release to contain the Resource class.

* `dart:io`
  * `HttpClient` no longer sends URI fragments in the request. This is not
    allowed by the HTTP protocol.
    The `HttpServer` still gracefully receives fragments, but discards them
    before delivering the request.
  * Removed server socket references. The use of server socket references
    was deprecated back in 1.9. Use the `shared` flag when creating listening
    sockets and `HttpServer` to distribute accepted sockets between isolates.

* `dart:isolate`
  * `Isolate` added `packageRoot` and `packageMap` getters.
  * `Isolate.spawnUri` added `packageMap` parameter.

### Tool changes

* `docgen` and 'dartdocgen' no longer ship in the sdk. The `docgen` sources have
   been removed from the repository.

* This is the last release to ship the VM's "legacy debug protocol".
  We intend to remove the legacy debug protocol in Dart VM 1.14.

* The VM's Service Protocol has been updated to version 3.0 to take care
  of a number of issues uncovered by the first few non-observatory
  clients.  This is a potentially breaking change for clients.

## 1.12.2 - 2015-10-21

### Core library changes

* `dart:io`

  * A memory leak in creation of Process objects is fixed.

## 1.12.1 - 2015-09-08
    * `??`: if null operator. `expr1 ?? expr2` evaluates to `expr1` if not `null`, otherwise `expr2`.
    * `??=`: null-aware assignment. `v ??= expr` causes `v` to be assigned `expr` only if `v` is `null`.
    * `x?.p`: null-aware access. `x?.p` evaluates to `x.p` if `x` is not `null`, otherwise evaluates to `null`.
    * `x?.m()`: null-aware method invocation. `x?.m()` invokes `m` only if `x` is not `null`.
* `dart:developer`
  * New `log` function to transmit logging events to Observatory.

* `dart:mirrors`
  * `InstanceMirror.delegate` moved up to `ObjectMirror`.
  * Fix InstanceMirror.getField optimization when the selector is an operator.
  * Fix reflective NoSuchMethodErrors to match their non-reflective
    counterparts when due to argument mismatches. (VM only)

* Documentation tools

  * `dartdoc` is now the default tool to generate static HTML for API docs.
    [Learn more](https://pub.dartlang.org/packages/dartdoc).

  * `docgen` and `dartdocgen` have been deprecated. Currently plan is to remove
    them in 1.13.

* Formatter (`dartfmt`)

  * Over 50 bugs fixed.

  * Optimized line splitter is much faster and produces better output on
    complex code.

* Observatory
  * Allocation profiling.

  * New feature to display output from logging.

  * Heap snapshot analysis works for 64-bit VMs.

  * Improved ability to inspect typed data, regex and compiled code.

  * Ability to break on all or uncaught exceptions from Observatory's debugger.

  * Ability to set closure-specific breakpoints.

  * 'anext' - step past await/yield.

  * Preserve when a variable has been expanded/unexpanded in the debugger.

  * Keep focus on debugger input box whenever possible.

  * Echo stdout/stderr in the Observatory debugger.  Standalone-only so far.

  * Minor fixes to service protocol documentation.

## 1.11.2 - 2015-08-03
## 1.11.1 - 2015-07-02
  See [dartlang.org/tools](https://www.dartlang.org/tools/) for alternatives.