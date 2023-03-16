# Dart

The Catalyst projects follows the guidelines in [Effective Dart](https://dart.dev/guides/language/effective-dart), but with some additions.
All code must be formatted using [dart format](https://dart.dev/tools/dart-format) before being checked in.

- [Dart](#dart)
  - [Additional Style Rules](#additional-style-rules)
    - [DON'T follow the Flutter repository style guide.](#dont-follow-the-flutter-repository-style-guide)
    - [DO use trailing commas.](#do-use-trailing-commas)
    - [DO order members.](#do-order-members)
    - [PREFER to keep lines below 80 characters.](#prefer-to-keep-lines-below-80-characters)
  - [Additional Usage Rules](#additional-usage-rules)
    - [PREFER minimizing the number of public members.](#prefer-minimizing-the-number-of-public-members)
    - [CONSIDER exporting publicly visible classes in a single `.dart` file.](#consider-exporting-publicly-visible-classes-in-a-single-dart-file)
    - [DO import all files within a package using relative paths // TODO: @minikin](#do-import-all-files-within-a-package-using-relative-paths--todo-minikin)
    - [DO use namespacing.](#do-use-namespacing)
    - [PREFER to use `show`.](#prefer-to-use-show)
    - [DON'T do useful work in assert statements.](#dont-do-useful-work-in-assert-statements)
    - [PREFER to use `const` over `final` over `var`.](#prefer-to-use-const-over-final-over-var)
    - [AVOID mixing named and positional parameters.](#avoid-mixing-named-and-positional-parameters)

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

For multiple classes that are used together but are in different files, it’s more convenient for users of your library to import a single file rather many at once.
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

### DO import all files within a package using relative paths // TODO: @minikin

Mixing and matching relative and absolute paths within a single package causes Dart to act as if there were two separate imports of identical files,
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
