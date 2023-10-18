# Dart Style Guide

The Catalyst projects follows the guidelines in [Effective Dart](https://dart.dev/guides/language/effective-dart), but with some additions.
All code must be formatted using [dart format](https://dart.dev/tools/dart-format) before being checked in.

- [Dart Style Guide](#dart-style-guide)
  - [Additional Style Rules](#additional-style-rules)
    - [DON'T follow the Flutter repository style guide.](#dont-follow-the-flutter-repository-style-guide)
    - [DO use trailing commas.](#do-use-trailing-commas)
    - [DO order members.](#do-order-members)
    - [PREFER to keep lines below 80 characters.](#prefer-to-keep-lines-below-80-characters)
  - [Additional Usage Rules](#additional-usage-rules)
    - [PREFER minimizing the number of public members.](#prefer-minimizing-the-number-of-public-members)
    - [CONSIDER exporting publicly visible classes in a single `.dart` file.](#consider-exporting-publicly-visible-classes-in-a-single-dart-file)
    - [DO import all files within a package using relative paths](#do-import-all-files-within-a-package-using-relative-paths)
    - [DO use namespacing.](#do-use-namespacing)
    - [PREFER to use `show`.](#prefer-to-use-show)
    - [DON'T do useful work in assert statements.](#dont-do-useful-work-in-assert-statements)
    - [PREFER to use `const` over `final` over `var`.](#prefer-to-use-const-over-final-over-var)
    - [AVOID mixing named and positional parameters.](#avoid-mixing-named-and-positional-parameters)
    - [Avoid using var and dynamic](#avoid-using-var-and-dynamic)
    - [Employ asserts generously to identify contract breaches and confirm invariants.](#employ-asserts-generously-to-identify-contract-breaches-and-confirm-invariants)
    - [Minimize the visibility scope of constants](#minimize-the-visibility-scope-of-constants)
    - [Avoid using if chains or ?: or == with enum values](#avoid-using-if-chains-or--or--with-enum-values)
    - [Avoid checking the availability of a port prior to using it, refrain from adding timeouts, and steer clear of other race conditions.](#avoid-checking-the-availability-of-a-port-prior-to-using-it-refrain-from-adding-timeouts-and-steer-clear-of-other-race-conditions)
    - [Avoid using numbers that are vague or seem random without providing a clear explanation or justification for their use.](#avoid-using-numbers-that-are-vague-or-seem-random-without-providing-a-clear-explanation-or-justification-for-their-use)
    - [Common boilerplates for operator == and hashCode](#common-boilerplates-for-operator--and-hashcode)
    - [Override toString](#override-tostring)

## Additional Style Rules

### DON'T follow the Flutter repository style guide.

The Flutter project's style guide is meant to be used for code in the Flutter framework itself
It is not intended as style guidance for projects using Flutter.
All code in the Catalyst repositories should follow the standard Dart style.
Although we are not following the style, the Flutter's guide on documentation and development is still useful.

### DO use trailing commas.

DO use trailing commas on all tree structures longer than one line.

Without trailing commas, code that builds widget trees or similar types of code tends to be hard to read.
Adding the trailing commas allows dart format to do its job correctly.

**Without trailing commas:**

```dart
children.add(Expanded(
  child: Center(
      child: Container(
          width: 64.0, height: 64.0, child: FuchsiaSpinner())),
));
```

**With trailing commas:**

```dart
children.add(Expanded(
  child: Center(
      child: Container(
        width: 64.0,
        height: 64.0,
        child: FuchsiaSpinner(),
      ),
   ),
  ),
)
```

### DO order members.

DO order members using the Dart Analyzer.

In Visual Studio Code, this is the Dart: Organize Members command available in the Command Palette.
(Control+Shift+P or View -> Command Palette)

This formatter doesn’t appear to be available outside of the supported IDEs.


### PREFER to keep lines below 80 characters.

PREFER to keep lines below 80 characters unless it would be more readable.

This is a slight amendment from the general Dart rule. Unlike that rule, it is fine to have lines above 80 characters in the Catalyst repositories,
as long as it improves readability, and dart format won't automatically truncate the line.

## Additional Usage Rules

### PREFER minimizing the number of public members.

PREFER minimizing the number of public members exposed in a package

This can be done by only making things public when needed, and keeping all implementation detail libraries in the `/src` directory.
Assume anything public in the lib directory will be re-used.


### CONSIDER exporting publicly visible classes in a single `.dart` file.

For multiple classes that are used together but are in different files,
it’s more convenient for users of your library to import a single file rather many at once.
If the user wants narrower imports they can always restrict visibility using the show keyword.

This also helps minimize the publicly visible surface.

**Example:**

```dart
/// In src/apple.dart
class Apple {}

/// In src/orange.dart
class Orange {}

/// In src/veggies.dart
class Potato {}
class Tomato {}

/// In botanical_fruits.dart
export 'src/apple.dart';
export 'src/orange.dart';
// Can also be: export 'src/veggies.dart' hide Potato;
export 'src/veggies.dart' show Tomato;

/// In squeezer.dart
import 'package:plants/botanical_fruits.dart' show Orange;
```

### DO import all files within a package using relative paths

Mixing and matching relative and absolute paths within a single package causes Dart 
to act as if there were two separate imports of identical files,
which will introduce errors in typechecking.
Either format works as long as it is consistent.
Within the Catalyst repositories, relative paths are used.

This does not apply to external libraries, as only the absolute path can be used.

**Good:**

```dart
import 'access_point.dart';
```

**Bad**

```dart
import 'package:wifi/access_point.dart';
```

### DO use namespacing.

DO use namespacing when there is ambiguity, e.g. in class names

There are often functions or classes that can collide, e.g. File or Image. 
If you don't namespace, there will be a compile error.

**Good**:

```dart
import 'dart:ui' as ui;

import 'package:flutter/material.dart';

ui.Image(...) ...
```

**Bad**:

```dart
import 'dart:ui';

import 'package:flutter/material.dart';
...

Image(...) ... // Which Image is this?
```

### PREFER to use `show`.

PREFER to use `show` if you only have a few imports from that package. Otherwise, use `as`.

Using show can avoid collisions without requiring you to prepend namespaces to types, leading to cleaner code.


**Good**:

```dart
import 'package:fancy_style_guide/style.dart' as style;
import 'package:flutter/material.dart';
import 'package:math/simple_functions.dart' show Addition, Subtraction;
```
**Bad**:

```dart
import 'package:flutter/material.dart show Container, Row, Column, Padding,
  Expanded, ...;
```

### DON'T do useful work in assert statements.

Code inside assert statements are not executed in production code.
Asserts should only check conditions and be side-effect free.

### PREFER to use `const` over `final` over `var`.

This minimizes the mutability for each member or local variable.

### AVOID mixing named and positional parameters.

Instead, `required` should be used in place of required positional parameters.

### Avoid using var and dynamic

All variables and arguments should have specified types;
avoid using `dynamic` or `Object` when the actual type can be determined.

Ensure to specify generic types whenever possible.
Explicitly type all list and map literals and provide types for all parameters,
including in closures, regardless of parameter usage.

This serves dual purposes: it confirms the compiler-inferred type aligns with
the anticipated type and renders the code self-explanatory when the type isn't apparent
(e.g., during non-constructor calls).

Always avoid `var` and `dynamic`.
If the type is undetermined, favor using `Object` (or `Object?`) and
perform casting since utilizing dynamic bypasses all static checking.

### Employ asserts generously to identify contract breaches and confirm invariants.

The `assert()` function aids in maintaining correctness without affecting performance in release mode,
as Dart evaluates asserts only in debug mode.

It's utilized to check that contracts and invariants align with expectations.
While asserts don’t enforce contracts in release builds,
they are useful in scenarios where a false condition indicates a bug in the code.

The following example is from [firestore.dart](https://github.com/firebase/flutterfire/blob/679beaa3fc3b4182597b83f39bcc9c5649e5722a/packages/cloud_firestore/cloud_firestore/lib/src/firestore.dart#L73):

```dart
  CollectionReference<Map<String, dynamic>> collection(String collectionPath) {
    assert(
      collectionPath.isNotEmpty,
      'a collectionPath path must be a non-empty string',
    );
    assert(
      !collectionPath.contains('//'),
      'a collection path must not contain "//"',
    );
    assert(
      isValidCollectionPath(collectionPath),
      'a collection path must point to a valid collection.',
    );

    return _JsonCollectionReference(this, _delegate.collection(collectionPath));
  }
```

### Minimize the visibility scope of constants

Prefer using a local const or a static const in a relevant class than using a global constant.

As a general rule, when you have a lot of constants, wrap them in a class.

For examples of this:

```dart
class MaterialAccentColor extends ColorSwatch<int> {
  /// Creates a color swatch with a variety of shades appropriate for accent
  /// colors.
  const MaterialAccentColor(super.primary, super.swatch);

  /// The lightest shade.
  Color get shade100 => this[100]!;

  /// The default shade.
  Color get shade200 => this[200]!;

  /// The second darkest shade.
  Color get shade400 => this[400]!;

  /// The darkest shade.
  Color get shade700 => this[700]!;
}
```

### Avoid using if chains or ?: or == with enum values

Use `switch` with no default case if you are examining an `enum`,
since the analyzer will warn you if you missed any of the values when you use switch.
The `default` case should be avoided so that the analyzer will complain if a value is missing.
Unused values can be grouped together with a single `break` or `return` as appropriate.

Avoid using `if` chains, `? …​ : …​,` or, in general, any expressions involving enums.

### Avoid checking the availability of a port prior to using it, refrain from adding timeouts, and steer clear of other race conditions.

If you look for an available port, then try to open it,
some other code will likely open that port between your check and when you open the port, and that will cause failure.

>Instead, have the code that opens the port pick an available port and return it rather than being given a (supposedly) available port.

If you have a timeout, then it's very likely that some other code will happen to run while your timeout is running,
and your "really conservative" timeout will trigger even though it would have worked fine if the timeout was one second longer, and that will cause a failure.

>Instead, have the code that would time out display a message saying that things are unexpectedly taking a long time so that someone interactively using the tool can see that something is fishy. Still, an automated system won't be affected. -->

Race conditions like this are the primary cause of flaky tests, which waste everyone's time.

Similarly, avoid delays or sleeps that are intended to coincide with how long something takes.
You may think that waiting two seconds is okay because it usually takes 10ms, but several times a week,
your 10ms task will take 2045ms, and your test will fail because waiting two seconds wasn't long enough.

>Instead, wait for a triggering event.

### Avoid using numbers that are vague or seem random without providing a clear explanation or justification for their use.

Numbers in tests and elsewhere should be clearly understandable.
When the provenance of a number is not obvious, consider either leaving the expression or
adding a clear comment (bonus points for leaving a diagram).

```dart
// BAD
expect(rect.left, 4.24264068712);

// GOOD
expect(rect.left, 3.0 * math.sqrt(2));
```

### Common boilerplates for operator == and hashCode

We have many classes that override operator `==` and hashCode ("value classes").
To keep the code consistent, we use the following style for these methods:

```dart
@override
bool operator ==(Object other) {
  if (other.runtimeType != runtimeType) {
    return false;
  }
  return other is Foo
      && other.bar == bar
      && other.baz == baz
      && other.quux == quux;
}

@override
int get hashCode => Object.hash(bar, baz, quux);
```
For objects with a lot of properties, consider adding the following at the top of the operator `==`:

```dart
  if (identical(other, this)) {
    return true;
  }
```

In general, consider carefully whether overriding operator `==` is a good idea.
It can be expensive, especially if the properties it compares are themselves comparable with a custom operator `==`.
If you do override equality, you should use `@immutable` on the class hierarchy.

### Override toString

For trivial classes, override toString as follows, to aid in debugging:

```dart
@override
String toString() => '${objectRuntimeType(this, 'NameOfObject')}($bar, $baz, $quux)';
```

 **Avoid** using `$runtimeType`, since it adds a non-trivial cost even in release and profile mode.
 The `objectRuntimeType` method handles this for you, falling back to a supplied constant string when asserts are disabled.