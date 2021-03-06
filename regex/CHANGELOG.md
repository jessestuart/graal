# TRegex Changelog

This changelog summarizes major changes between TRegex versions relevant to language implementors integrating TRegex into their language. This document will focus on API changes relevant to integrators of TRegex.

## Version 1.0.0 RC15

* Removed properties `regex`, `input`, `start`, and `end` from result objects.
* Introduced methods `getStart(groupNumber)` and `getEnd(groupNumber)` as a replacement for `start` and `end` in result objects.
* Regex syntax exceptions are now to be treated as plain `TruffleException`s - languages using TRegex should not introduce any source code dependency on TRegex.

## Version 1.0.0 RC10

* Added the possibility to log the actions of the compiler.
     * Introduced the `regex` loggers `SwitchToEager`, `TotalCompilationTime`, `Phases`, `BailoutMessages`, `AutomatonSizes`, `CompilerFallback`, `InternalErrors` and `TRegexCompilations`. These can be enabled in your launchers by setting, e.g., `--log.regex.Phases.level=ALL`.
