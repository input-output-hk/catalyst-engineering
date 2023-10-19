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

Utilizing const constructors when creating widgets in Flutter can offer significant performance optimizations.

Below are the key points concerning the use of const widgets:

**Performance Optimization:**

`const` constructors allow Flutter to reuse widgets across builds, which significantly optimizes performance by reducing the amount of widget rebuilding necessary.
The framework can quickly compare const widgets and determine whether the widget tree needs to be updated, saving both memory and CPU cycles.

**Code Maintainability:**

`const` widgets make the immutability of the widget explicit, which is a good practice for maintaining a clear, understandable codebase.
It encourages the use of immutable data structures, aligning with Flutter’s paradigm of immutable widget trees and functional reactive programming.

**Compile-time Safety:**

Using const allows for some errors to be caught at compile-time rather than runtime, which is safer and can prevent bugs from reaching production.

Example:

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: HomeScreen(),
    );
  }
}

class HomeScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: const AppBar(  // const constructor
        title: Text('Const Example'),
      ),
      body: const Center(  // const constructor
        child: Text('Hello, World!'),
      ),
    );
  }
}
```

In this example:

`const` constructors are used to create `AppBar` and `Center` widgets.
By specifying `const`, we're telling Flutter that these widgets will never change and can be reused across builds,
optimizing the performance of our app.

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

**Resource Management and Memory Leaks:**

Streams, especially those associated with IO-bound work like reading from a file or a network socket, use up system resources.
When a stream is open, it holds onto memory and potentially other resources like file handles or network connections.
If not closed, these resources remain allocated, leading to memory leaks and potentially exhausting system resources
which could affect the performance of your application or even cause it to crash.

**Error Prevention and Data Integrity:**

Not closing a stream can lead to bugs or data corruption.
For instance, if you're writing to a file through a stream and forget to close the stream,
some data might remain buffered and not get written to the file.
This can lead to data loss or corrupted files.

**Good Practice:**

Explicitly closing streams is considered good practice in Dart and Flutter,
as it shows that you're managing resources correctly which is crucial for building reliable and efficient applications.


Suppose you have a stream that emits values from a user input field and you process these values in some way.

```dart
import 'dart:async';

class InputHandler {
  final StreamController<String> _inputStreamController = StreamController<String>();

  void onUserInput(String input) {
    _inputStreamController.sink.add(input);  // Sending data into the stream
  }

  void processInput() {
    _inputStreamController.stream.listen((input) {
      // Process the user input in some way
      print('Processed input: $input');
    });
  }

  void dispose() {
    _inputStreamController.close();  // Closing the stream when done
  }
}

void main() {
  final inputHandler = InputHandler();

  inputHandler.processInput();

  // Simulate user input
  inputHandler.onUserInput('Hello, World!');

  // Dispose of resources when done
  inputHandler.dispose();
}
```
In this example:

- We have defined a class `InputHandler` with a `StreamController` `_inputStreamController` to handle the user input.
- The `onUserInput` method simulates receiving user input and adds this input to the stream.
- The processInput method sets up a listener on the stream to process the user input.
- The `dispose` method is crucial; it's where we close the `_inputStreamController`, thus releasing any resources held by the stream.
- In the main function, we create an instance of `InputHandler`, simulate some user input,
process the input, and finally call `dispose` to clean up the resources when we're done.

## DO always dispose of AnimationControllers when you are done with them


## DO always dispose of ScrollControllers when you are done with them

In Flutter, a `ScrollController` is used to control the position of a scrollable widget.
Disposing of a `ScrollController` when it's no longer needed is crucial for several reasons:

**Resource Management:**

`ScrollController` holds onto resources that need to be freed up to ensure the efficiency of your application.

**Memory Leaks Prevention:**

If not disposed of, a `ScrollController` can cause memory leaks which would degrade the performance of your application over time.

**Error Prevention:**

It's possible to encounter errors or unexpected behaviors if you try to interact with a `ScrollController` that should have been disposed.

**Adherence to Best Practices:**

Properly managing resources by disposing of objects like `ScrollController` is a good programming practice in Flutter,
making your code more robust and easier to maintain.

Here's an example illustrating how to properly dispose of a `ScrollController`:

```dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: MyHomePage(),
    );
  }
}

class MyHomePage extends StatefulWidget {
  @override
  _MyHomePageState createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  ScrollController _scrollController;

  @override
  void initState() {
    super.initState();
    _scrollController = ScrollController();
  }

  @override
  void dispose() {
    _scrollController.dispose();  // Dispose of the ScrollController
    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('ScrollController Example'),
      ),
      body: ListView.builder(
        controller: _scrollController,
        itemCount: 30,
        itemBuilder: (context, index) {
          return ListTile(
            title: Text('Item #$index'),
          );
        },
      ),
    );
  }
}
```

In this example:

- A new `ScrollController` instance is created in the initState method.
- The dispose method is overridden to ensure that `_scrollController` is disposed of when `MyHomePage` is removed from the widget tree.
- The `_scrollController` is passed to the `ListView.builder's` controller property to control the scroll position of the list.

This way, the `ScrollController` is properly disposed of, preventing any potential resource leaks or errors.


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

Treating warnings as errors in a software development project can be a highly beneficial practice.

**Early Detection of Potential Issues:**

- Warnings are often indicative of potential problems in the code. By treating warnings as errors,
developers are forced to address these issues early on, which can prevent bugs from manifesting later.

**Code Quality:**

This practice encourages cleaner, more robust code by ensuring that developers address not only blatant errors 
but also other suboptimal coding practices that might generate warnings.

**Maintainability:**

Codebases with fewer warnings are generally easier to maintain and understand.
Addressing warnings promptly keeps the codebase tidy and reduces technical debt.

**Consistency:**

Enforcing a policy where warnings are treated as errors can lead to more consistent coding practices across a development team.

**Education and Awareness:**

Sometimes, warnings alert developers to deprecated APIs or newer, better practices.
Treating warnings as errors can be educational for developers and promote awareness of evolving best practices.
Example:

In Dart/Flutter, you can treat warnings as errors by adding the following line to your `analysis_options.yaml` file:

```yaml
analyzer:
  errors:
    unused_local_variable: error
    deprecated_member_use: error
```

In this example, the `unused_local_variable` and `deprecated_member_use` warnings are promoted to errors.
Now, whenever the Dart analyzer detects an unused local variable or the use of a deprecated member,
it will report these as errors, forcing the developer to address these issues before proceeding.
This is a way to ensure that the code adheres to certain quality standards and potential issues are addressed promptly.