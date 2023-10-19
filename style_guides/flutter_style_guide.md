# Flutter Style Guide

- [Flutter Style Guide](#flutter-style-guide)
  - [DON'T use functions which return widgets](#dont-use-functions-which-return-widgets)
      - [Classes:](#classes)
      - [Functions:](#functions)
  - [DO use const widgets where possible](#do-use-const-widgets-where-possible)
  - [DON'T use runtimeType for type checking](#dont-use-runtimetype-for-type-checking)
  - [Prefer Object over dynamic](#prefer-object-over-dynamic)
  - [DO use SizedBox instead of Container](#do-use-sizedbox-instead-of-container)
  - [DO use itemExtent in ListView for long lists](#do-use-itemextent-in-listview-for-long-lists)
  - [StatefulWidget: When to call super.initState() and super.dispose()?](#statefulwidget-when-to-call-superinitstate-and-superdispose)
  - [DO always close streams when you are done with them](#do-always-close-streams-when-you-are-done-with-them)
  - [DO always dispose of AnimationControllers when you are done with them](#do-always-dispose-of-animationcontrollers-when-you-are-done-with-them)
  - [DO always dispose of ScrollControllers when you are done with them](#do-always-dispose-of-scrollcontrollers-when-you-are-done-with-them)
  - [Common constants approach](#common-constants-approach)
  - [DO always treat warnings as errors](#do-always-treat-warnings-as-errors)

##  DON'T use functions which return widgets

> Composing a tree using functions that return widgets has the same performance characteristics
> as a single large build method that returns all those widgets inline.
> Composing a tree using widgets is significantly better since it localizes rebuilds.

_To make up for some misunderstanding: This is not about functions causing problems, but classes solving some._

Flutter wouldn't have StatelessWidget if a function could do the same thing.

Similarly, it is mainly directed at public widgets, made to be reused.
It doesn't matter as much for private functions made to be used only once – although being aware of this behavior is still good.

There is an important difference between using functions instead of classes, that is:
The framework is unaware of functions, but can see classes.

Consider the following "widget" function:

```dart
Widget functionWidget({ Widget child}) {
  return Container(child: child);
}
```

used this way:

```dart
functionWidget(
  child: functionWidget(),
);
```

And it's class equivalent:

```dart
class ClassWidget extends StatelessWidget {
  final Widget child;

  const ClassWidget({Key? key, this.child}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Container(
      child: child,
    );
  }
}

```

used like that:

```dart
const ClassWidget(
  child: ClassWidget(),
)
```

In theory, both seem to do exactly the same thing: Create 2 Container,
with one nested into the other. But the reality is slightly different.

In the case of functions, the generated widget tree looks like this:

```txt
Container
  Container
```

While with classes, the widget tree is:

```txt
ClassWidget
  Container
    ClassWidget
      Container
```

This is important because it changes how the framework behaves when updating a widget.

Why that matters
By using functions to split your widget tree into multiple widgets,
you expose yourself to bugs and miss on some performance optimizations.

There is no guarantee that you will have bugs by using functions,
but by using classes, you are guaranteed to not face these issues.

Here are a few interactive examples on DartPad that you can run yourself to better understand the issues:

This example showcases how by splitting your app into functions,
you may accidentally break things like AnimatedSwitcher: https://dartpad.dev/1870e726d7e04699bc8f9d78ba71da35

This example showcases how classes allow more granular rebuilds of the widget tree, improving performances: https://dartpad.dev/a869b21a2ebd2466b876a5997c9cf3f1

This example showcases how, by using functions,
you expose yourself to misusing BuildContext and facing bugs when using InheritedWidgets (such as Theme or providers): https://dartpad.dev/06842ae9e4b82fad917acb88da108eee

Conclusion

#### Classes:

- allow performance optimization (const constructor, more granular rebuild)
- ensure that switching between two different layouts correctly disposes of the resources (functions may reuse some previous state)
- ensures that hot-reload works properly (using functions could break hot-reload for showDialogs & similar)
- are integrated into the widget inspector.
- we can see ClassWidget in the widget-tree showed by the devtool, which helps understanding what is on screen
- We can override debugFillProperties to print what the parameters passed to a widget are
- better error messages
- If an exception happens (like ProviderNotFound), the framework will give you the name of the currently building widget.
  If you've split your widget tree only in functions + Builder, your errors won't have a helpful name
- Can define keys
- Can use the context API

#### Functions:

- have a better shape and less code.


## DO use const widgets where possible


## DON'T use runtimeType for type checking

`RuntimeType` is only for debugging purposes and the application code shouldn't depend on it.
It can be overridden by classes to return fake values and probably returns unusable values.

Instead use instance of operator `is`:

```dart
class Foo { }

main() {
  final foo = Foo();
  if (foo is Foo) {
    print('it's a foo!');
  }
}
```

## Prefer Object over dynamic

The dynamic type is special. It really means `Trust me, I know what I'm doing` and it turns off some static type checking.

Another perspective on `dynamic` is that it's not really a type - it's a way to turn off type checking and tell the static type system _"trust me, I know what I'm doing"_.
Writing `dynamic o`; declares a variable that isn't typed - it's instead marked as **"not type-checked"**.

When you write `Object o = something`; you are telling the system that it can't assume anything about o except that it's an `Object`. You can call `toString` and `hashCode` because those methods are defined on `Object`, but if you try to do `o.foo()` you will get a warning - it can't see that you can do that, and so it warns you that your code is probably wrong.

If you write `dynamic o = something` you are telling the system to not assume anything, and to not check anything. If you write `o.foo()` then it will not warn you. You've told it that _"anything related to o is OK! Trust me, I know what I'm doing"_, and so it thinks `o.foo()` is **OK**.

With great power comes great responsibility - if you disable type-checking for a variable, it falls back on you to make sure you don't do anything wrong.

**Additional Notes:**

- In Dart, there is no way to distinguish the type `dynamic` and the type `Object` at `run-time`, because there is no difference.
- The difference between `dynamic` and `Object` exists only at compile-time,
where you are allowed to call any method on a value with static type dynamic, and not very many methods on something with static type `Object`.
- Using `dynamic` typed variables in Dart is often slower than using variables typed with an actual type.
A dynamic method invocation may be slower because the run-time system must add extra checks to ensure that the variable can do the things you are trying to do with it.

## DO use SizedBox instead of Container


## DO use itemExtent in ListView for long lists


## StatefulWidget: When to call super.initState() and super.dispose()?

`super.initState()` should always be the first line in your initState method.

> [Flutter docs](https://api.flutter.dev/flutter/widgets/State/initState.html): If you override this, make sure your method starts with a call to super.initState().

```dart
@override
void initState() {
  super.initState();
  // DO STUFF
}
```

---

`super.dispose()` should always be the last line in your dispose method.

> [Flutter docs](https://api.flutter.dev/flutter/widgets/State/dispose.html): If you override this, make sure to end your method with a call to super.dispose().

```dart
@override
void dispose() {
  // DO STUFF
  super.dispose();
}
```

## DO always close streams when you are done with them


## DO always dispose of AnimationControllers when you are done with them


## DO always dispose of ScrollControllers when you are done with them


## Common constants approach

- Use `_k` prefixes to all of public and private constants
- Constant classes should be named `_C` or contain `Const` in the end

```dart
const _kHorizontalPadding = 4.0;

abstract class NewConst {
  static const _kHost = 'www.example.com';
}

abstract class _C {
  static const topPaddingWeb = 100.0;
}

abstract class _NewItemConst {
  static const drep = 'dRep';
  static const publicKey = 'PUBLIC_KEY';
  static const wallet = 'WALLET';
}
```

## DO always treat warnings as errors