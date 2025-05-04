# CPAN problem caused by changes in GNU gcc defaults

## Problem description

As of GNU gcc version 14, some issues that used to be reported as warnings
are now promoted to errors, causing building C and XS files to fail with no
changes to the code at all.

Some of these warnings might indeed indicate serious problems that might
eventually cause vulnerabilities and some can be safely ignored, but most
end-users installing from CPAN will not be able to tell without tedious
analysis of the code at hand.

## Issues

GNU gcc warning that now promote to errors in any mode higher than C90:

### -Wdeclaration-missing-parameter-type

### -Wimplicit-function-declaration

Functions can no longer be called without be declaring first.  Fixing this may
need additional prototypes in package header files, or inclusion of additional
header files (both package-specific and system headers).

### -Wimplicit-int

`int` types can no longer be omitted in old-style function definitions,
function return types, or variable declarations or definitions.  Fixing that
involves adding the `int` type (or the correct type if it is not actually
`int`).  If there is already a matching declaration in scope that has a
different type, that needs to be resolved somehow, too.

### -Wincompatible-pointer-types

`gcc` will no longer automatically convert between pointer values of unrelated
pointer types (except when one of them is void * or its qualified versions).
The fallout from this could be quite large.  Clang does this for function
pointer types only (probably based on their ABI issues).

### -Wint-conversion

Conversion between pointer and integer types without an explicit cast is now
a compiler error.

### -Wnarrowing

A narrowing conversion from a constant produces an error, and a narrowing
conversion from a non-constant produces a warning, but `-Wno-narrowing`
suppresses the diagnostic.  Note that this does not affect the meaning of
well-formed code; narrowing conversions are still considered ill-formed in
SFINAE contexts. (C++ only)

### -Wreturn-mismatch

Warn about return statements without an expressions in functions which do not
return `void`.  Also warn about a `return` statement with an expression in a
function whose return type is `void`, unless the expression type is also `void`.

As a GNU extension, the latter case is accepted without a warning.

Attempting to use the return value of a non-`void` function other than `main`
that flows off the end by reaching the closing curly brace that terminates the
function is undefined.

### -Wdiscarded-qualifies

Using const pointers as non-const is forbidden.

### -Wpointer-sign

Using `char *` as `unsigned char *` and vice versa.

## Workarounds

### Fix the issues

This is obviously the safest and most rewarding approach, but this will take
time. Fixing the problems one by one and - of course - report them back to
the author(s) of the module is the prefered route. A Pull Request could be
the crown on this work.

It however requires time and effort and likely a lot of extra resources that
are required for tracking down the correct solution or fix.

### Demote errors to warnings

This is actually wiping possible problems under the carpet, but it might not
be the worst approach. You will not know without digging. Maybe the error
is in code that is never used in your environment or just triggered when in
debugging mode.

Change the generated `Makefile`s for each promoted warning:
```
$ perl Makefile.PL
$ find * -name Makefile | xargs perl -pi -e'm/^\s*CCFLAGS\s*=/ and s/$/ -Wno-error=incompatible-pointer-types/'
$ find * -name Makefile | xargs perl -pi -e'm/^\s*CCFLAGS\s*=/ and s/$/ -Wno-error=implicit-int/'
$ ...
```
or generic for all of them
```
$ perl Makefile.PL
$ find * -name Makefile | xargs perl -pi -e'm/^\s*CCFLAGS\s*=/ and s/$/ -fpermissive/'
```
which will downgrade some required diagnostics about nonconformant code from
errors to warnings. Thus, using `-fpermissive` allows some nonconforming code
to compile. Some C++ diagnostics are controlled only by this flag, but it also
downgrades some C and C++ diagnostics that have their own flag.
