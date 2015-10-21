## 1.12.1
* Pub

  * Pub will now respect `.gitignore` when validating a package before it's
    published. For example, if a `LICENSE` file exists but is ignored, that is
    now an error.
  * If the package is in a subdirectory of a Git repository and the entire
    subdirectory is ignored with `.gitignore`, pub will act as though nothing
    was ignored instead of uploading an empty package.
  * The heuristics for determining when `pub get` needs to be run before various
    commands have been improved. There should no longer be false positives when
    non-dependency sections of the pubspec have been modified.
## 1.12.0 - 2015-08-31
    * `??`: if null operator. `expr1 ?? expr2` evaluates to `expr1` if
      not `null`, otherwise `expr2`.
    * `??=`: null-aware assignment. `v ??= expr` causes `v` to be assigned
      `expr` only if `v` is `null`.
    * `x?.p`: null-aware access. `x?.p` evaluates to `x.p` if `x` is not
      `null`, otherwise evaluates to `null`.
    * `x?.m()`: null-aware method invocation. `x?.m()` invokes `m` only
      if `x` is not `null`.
* Formatter (`dartfmt`)

  * Over 50 bugs fixed.

  * Optimized line splitter is much faster and produces better output on
    complex code.

  See [dartlang.org/tools](https://www.dartlang.org/tools/]) for alternatives.