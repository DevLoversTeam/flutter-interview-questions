**Read in other languages: [English 🇺🇸](README.en.md),
[Polska 🇵🇱](README.pl.md), [German 🇩🇪](README.de.md), [French 🇫🇷](README.fr.md),
[Spanish 🇪🇸](README.es.md), [Українська 🇺🇦](README.md).**

<h1>
  Flutter <img src="./assets/flutter.svg" width="40" height="40" />
</h1>

<h2>Most Popular Flutter Interview Questions and Answers</h2>

<details>
<summary>1. What is Flutter?</summary>

#### Flutter

Flutter is an open-source UI toolkit by Google for building cross-platform
applications from a single codebase.

#### Main Flutter characteristics:

1. **Cross-platform:** Lets you build apps for iOS, Android, Web, Windows,
   macOS, and Linux.

2. **Own rendering engine:** Flutter draws the UI itself instead of relying on
   native OEM widgets as the base UI.

3. **Widget-based approach:** In Flutter, almost everything is a widget: screens,
   text, spacing, buttons, animations.

4. **High development speed:** Hot Reload lets you see code changes quickly
   without fully restarting the app.

5. **Single development language:** Client-side code is typically written in Dart.

Flutter is often used for fast MVP development, production mobile apps, and
internal enterprise systems.

</details>
<details>
<summary>2. Why is Flutter often chosen for mobile development?</summary>

#### Flutter

Flutter is often chosen because it balances development speed, UI quality, and
the ability to maintain a single codebase across multiple platforms.

#### Main reasons:

1. **One codebase:** Less duplicated logic between Android and iOS.

2. **Fast development:** Hot Reload speeds up team iteration cycles.

3. **Predictable UI:** Flutter renders UI itself, so design is more consistent
   across platforms.

4. **Good performance:** For most business apps, Flutter delivers
   production-grade performance.

5. **Strong ecosystem:** Many packages are available for navigation, state, HTTP,
   local storage, analytics, and testing.

6. **Convenient for custom UI:** If a product has many non-standard screens,
   animations, or a complex design system, Flutter often speeds up delivery.

#### When this is especially beneficial:

- When you need to launch on iOS and Android quickly.
- When the team is small and maintenance cost matters.
- When the product has a lot of custom interface work.

</details>
<details>
<summary>3. Which platforms does Flutter support?</summary>

#### Flutter

Flutter supports multiple platforms from a single codebase.

#### Main platforms:

1. **Android**
2. **iOS**
3. **Web**
4. **Windows**
5. **macOS**
6. **Linux**

#### Additionally:

- Flutter is also used for **embedded solutions** and specialized devices when
  there is proper engine integration.
- In commercial development, Flutter is most commonly used for **mobile
  platforms**, but web and desktop are officially supported as well.

</details>
<details>
<summary>4. What is Dart, and why does Flutter use this language?</summary>

#### Flutter

Dart is a programming language developed by Google. Flutter uses Dart as the
main language for UI, business logic, and framework interaction.

#### Why Flutter uses Dart:

1. **Fast compile cycle during development:** This enables Hot Reload.

2. **AOT and JIT:** Dart supports JIT for fast development and AOT compilation for
   efficient production builds.

3. **Simple syntax:** Dart is easy to pick up for developers with Java,
   JavaScript, C#, Kotlin, or Swift background.

4. **Strong async support:** `Future`, `Stream`, and `async/await` naturally fit
   client-side development.

5. **Strong typing:** This improves maintainability, refactoring, and stability in
   larger projects.

#### Practical reason:

Flutter needs a language that works well both for fast development and optimized
compilation. Dart covers both scenarios.

</details>
<details>
<summary>5. What is the structure of a Flutter project?</summary>

#### Flutter

A typical Flutter project has several standard directories and service files.

#### Basic structure:

1. **`lib/`** - main application code.
2. **`test/`** - unit and widget tests.
3. **`android/`** - native Android part of the project.
4. **`ios/`** - native iOS part of the project.
5. **`web/`** - web configuration and entry point.
6. **`macos/`, `windows/`, `linux/`** - desktop platforms.
7. **`pubspec.yaml`** - dependencies, assets, project metadata.

#### Most important in practice:

- In most cases, core product logic lives in `lib/`.
- Platform folders are updated when native settings, permissions, SDK config, or
  platform channels are needed.

#### Example of logical structure inside `lib/`:

```text
lib/
  core/
  features/
  shared/
  app/
  main.dart
```

In production projects, it's important not only to know the standard Flutter
structure but also to have a clear feature-based or layered architecture.

</details>
<details>
<summary>6. What is the `pubspec.yaml` file, and what is it used for?</summary>

#### Flutter

`pubspec.yaml` is the main configuration file of a Dart/Flutter project.

#### What it is used for:

1. **Dependency management:** Packages used by the app.

2. **Resource declaration:** Connecting assets, fonts, and icons.

3. **Project metadata:** Name, version, description, environment constraints.

4. **Dev dependency setup:** For example, `flutter_test`, `build_runner`,
   `flutter_lints`.

#### Example:

```yaml
name: flutter_interview_questions
description: Flutter interview questions and answers
version: 1.0.0+1

environment:
  sdk: ">=3.0.0 <4.0.0"

dependencies:
  flutter:
    sdk: flutter
  dio: ^5.0.0

dev_dependencies:
  flutter_test:
    sdk: flutter
  flutter_lints: ^3.0.0

flutter:
  uses-material-design: true
  assets:
    - assets/images/
```

#### Important:

After updating `pubspec.yaml`, you typically run `flutter pub get` to fetch new
dependencies.

</details>
<details>
<summary>7. What is the role of the `main()` function in Flutter?</summary>

#### Flutter

`main()` is the entry point of a Flutter application, where program execution
starts.

#### Main role:

1. **App startup:** `runApp()` is usually called inside `main()`.

2. **Initial initialization:** You can initialize services, a DI container,
   Firebase, local storage, or environment config here.

3. **Pre-UI setup:** If `await` is needed before startup, `main()` can be made
   `async`.

#### Example:

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}
```

#### Example with initialization:

```dart
import 'package:flutter/widgets.dart';

Future<void> main() async {
  WidgetsFlutterBinding.ensureInitialized();

  // await someAsyncInitialization();

  runApp(const MyApp());
}
```

</details>
<details>
<summary>8. What does the `runApp()` function do?</summary>

#### Flutter

`runApp()` starts a Flutter application and mounts the passed root widget into
the widget tree.

#### What happens in practice:

1. **A root UI node is created:** The whole widget tree starts from this node.

2. **Flutter starts building the interface:** The framework then calls `build()`
   and renders the screen.

3. **The app is put under Flutter framework control:** All further UI updates are
   handled through widgets, elements, and render objects.

#### Example:

```dart
void main() {
  runApp(const MyApp());
}
```

#### Important:

- `runApp()` usually receives `MaterialApp`, `CupertinoApp`, or a custom root
  `App` widget.
- Calling `runApp()` repeatedly is possible, but in a typical app lifecycle it is
  usually called once.

</details>
<details>
<summary>9. What are widgets in Flutter?</summary>

#### Flutter

Widgets are the basic UI building blocks in Flutter. They describe how a part of
the interface should look and behave.

#### Examples of what is a widget:

1. **Text:** `Text`
2. **Button:** `ElevatedButton`
3. **Spacing:** `Padding`
4. **Layout:** `Column`, `Row`, `Stack`
5. **Screen:** `Scaffold`

#### Widget characteristics:

1. **Declarative approach:** You describe UI as a set of widgets.

2. **Composition:** Complex interfaces are built from simple widgets.

3. **Immutability:** Widgets themselves are immutable; UI changes are achieved by
   rebuilding the tree.

#### Example:

```dart
class HelloText extends StatelessWidget {
  const HelloText({super.key});

  @override
  Widget build(BuildContext context) {
    return const Text('Hello Flutter');
  }
}
```

</details>
<details>
<summary>10. What is the difference between `StatelessWidget` and `StatefulWidget`?</summary>

#### Flutter

The difference is whether the widget has internal mutable state that affects its
rendered output.

#### `StatelessWidget`:

Used for UI that depends only on input parameters and has no internal mutable
state.

```dart
class TitleText extends StatelessWidget {
  final String title;

  const TitleText({super.key, required this.title});

  @override
  Widget build(BuildContext context) {
    return Text(title);
  }
}
```

#### `StatefulWidget`:

Used when a widget has state that can change during its lifecycle.

```dart
class CounterWidget extends StatefulWidget {
  const CounterWidget({super.key});

  @override
  State<CounterWidget> createState() => _CounterWidgetState();
}

class _CounterWidgetState extends State<CounterWidget> {
  int counter = 0;

  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        Text('Count: $counter'),
        ElevatedButton(
          onPressed: () {
            setState(() {
              counter++;
            });
          },
          child: const Text('Increment'),
        ),
      ],
    );
  }
}
```

#### Main differences:

1. **State:** `StatelessWidget` has no mutable state; `StatefulWidget` does.

2. **UI updates:** In `StatefulWidget`, UI updates via `setState()` or other
   state management approaches.

3. **Use cases:** Static UI elements vs interactive or dynamic screen parts.

</details>
<details>
<summary>11. What is the widget tree in Flutter?</summary>

#### Flutter

The widget tree is the hierarchy of all widgets that make up the Flutter app UI.

#### How it works:

1. **Each widget can contain child widgets.**

2. **The entire screen is built as a tree of nested elements.**

3. **When state changes, Flutter rebuilds parts of this tree.**

#### Example:

```dart
MaterialApp(
  home: Scaffold(
    appBar: AppBar(
      title: const Text('Home'),
    ),
    body: const Center(
      child: Text('Hello'),
    ),
  ),
)
```

In this example, `MaterialApp` is the root. Inside it, there is `Scaffold`, then
`AppBar`, `Center`, and `Text`.

#### Why this is important:

- Understanding the widget tree helps build UI correctly.
- It is critical for debugging, rebuild optimization, and context usage.

</details>
<details>
<summary>12. What is `BuildContext`?</summary>

#### Flutter

`BuildContext` is a reference to a widget's location in the widget tree.

#### What it is used for:

1. **Access to parent dependencies:** For example, `Theme`, `MediaQuery`,
   `Navigator`, `ScaffoldMessenger`, `Provider`.

2. **Navigation:** Via `Navigator.of(context)`.

3. **Access to local environment settings:** Screen size, theme, locale, and
   other inherited dependencies.

#### Example:

```dart
final theme = Theme.of(context);
final size = MediaQuery.of(context).size;
```

#### Important nuance:

`BuildContext` must belong to the correct place in the tree. For example, if you
call `ScaffoldMessenger.of(context)` too early or from a context without the
required ancestor, you will get an error.

#### Practical rule:

Treat context not as "global access," but as "the widget's position in the tree
at this moment."

</details>
<details>
<summary>13. What is `Key` in Flutter, and why is it needed?</summary>

#### Flutter

`Key` is a widget identity mechanism in the tree that helps Flutter correctly
match old and new widgets during rebuild.

#### Why `Key` is needed:

1. **Preserving state when item order changes.**

2. **Correct behavior for lists and dynamic collections.**

3. **Accessing widgets in tests.**

4. **Controlling element uniqueness in the tree.**

#### Example:

```dart
ListView(
  children: const [
    ListTile(key: ValueKey('user_1'), title: Text('User 1')),
    ListTile(key: ValueKey('user_2'), title: Text('User 2')),
  ],
)
```

#### Main types:

1. **`ValueKey`** - when you have a stable identifier value.
2. **`ObjectKey`** - when the key is based on an object.
3. **`UniqueKey`** - when guaranteed uniqueness is required.
4. **`GlobalKey`** - for accessing a specific widget's state or context.

#### Important:

`GlobalKey` should be used carefully. It is powerful but relatively expensive,
and should not be used without real need.

</details>
<details>
<summary>14. What are Hot Reload and Hot Restart?</summary>

#### Flutter

Hot Reload and Hot Restart are two fast app restart mechanisms used during
development.

#### Hot Reload:

- Applies code changes almost instantly.
- Preserves current app state.
- Best for UI, styling, and `build()` logic updates.

#### Hot Restart:

- Restarts the Dart isolate.
- Resets current app state.
- Runs `main()` again.
- Needed when Hot Reload is no longer sufficient.

#### Difference:

| Criterion       | Hot Reload                 | Hot Restart                            |
| --------------- | -------------------------- | -------------------------------------- |
| Speed           | Faster                     | Slower                                 |
| State retention | Yes                        | No                                     |
| `main()` call   | No                         | Yes                                    |
| Typical use     | UI and small logic changes | Initialization or global state changes |

#### Important:

Not all changes can be applied correctly via Hot Reload. For example, changes in
initialization flow or some static constructs may require Hot Restart.

</details>
<details>
<summary>15. What build modes exist in Flutter (Debug, Profile, Release)?</summary>

#### Flutter

Flutter has three main build modes, each with its own purpose.

#### 1. Debug

- Used during development.
- Supports Hot Reload.
- Includes extra checks, assertions, and dev tooling.
- Not suitable for measuring real performance.

#### 2. Profile

- Used for performance analysis.
- Closer to production behavior.
- Lets you profile CPU, GPU, memory, and frame rendering.

#### 3. Release

- Used for production.
- Maximally optimized.
- No debug tools, assertions, or dev overhead.

#### When to use each mode:

1. **Debug** - daily development.
2. **Profile** - performance tuning.
3. **Release** - store release or production distribution.

</details>
<details>
<summary>16. What is `MaterialApp`?</summary>

#### Flutter

`MaterialApp` is the root widget for applications that use Material Design.

#### What it provides:

1. **Navigation**
2. **App theme**
3. **Localization**
4. **Routes**
5. **Base Material configuration**

#### Example:

```dart
import 'package:flutter/material.dart';

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        colorScheme: ColorScheme.fromSeed(seedColor: Colors.blue),
      ),
      home: const HomePage(),
    );
  }
}
```

#### When it is used:

In most Flutter applications, `MaterialApp` is the entry point at the top level
of the widget tree.

</details>
<details>
<summary>17. What is the `Scaffold` widget?</summary>

#### Flutter

`Scaffold` is a base layout widget for Material Design screens.

#### What it usually contains:

1. **`appBar`** - top bar.
2. **`body`** - main screen content.
3. **`floatingActionButton`** - floating action button.
4. **`drawer`** - side menu.
5. **`bottomNavigationBar`** - bottom navigation.
6. **`snackBar` / `bottomSheet` integration** - interaction with Material shell.

#### Example:

```dart
class HomePage extends StatelessWidget {
  const HomePage({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('Home'),
      ),
      body: const Center(
        child: Text('Content'),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: () {},
        child: const Icon(Icons.add),
      ),
    );
  }
}
```

#### Practical role:

`Scaffold` gives you a standard screen "shell." Without it, many Material
behaviors need to be implemented manually.

</details>
<details>
<summary>18. What is `SafeArea` used for?</summary>

#### Flutter

`SafeArea` is used to prevent content from being placed under system UI
elements.

#### What it protects from:

1. **Status bar**
2. **Notch / Dynamic Island / screen cutouts**
3. **System gestures and bottom safe insets**
4. **Other system areas that should not overlap content**

#### Example:

```dart
SafeArea(
  child: Column(
    children: const [
      Text('Header'),
      Text('Body'),
    ],
  ),
)
```

#### When it is especially useful:

- On screens with custom layout.
- When content touches screen edges.
- When you need quick baseline safety for UI placement.

#### Important:

`SafeArea` does not replace thoughtful layout design, but it helps avoid common
issues with system-area overlap.

</details>
<details>
<summary>19. What is the Dart programming language?</summary>

#### Flutter

Dart is a modern object-oriented programming language developed by Google and
used as the main language for Flutter development.

#### Main Dart characteristics:

1. **Strong typing:** Dart supports static typing, improving predictability and
   code safety.

2. **JIT and AOT compilation:** This combines fast development with performant
   production builds.

3. **Async support:** `Future`, `Stream`, and `async/await` are built into the
   language.

4. **Convenient syntax:** Dart is relatively easy to learn for developers with
   Java, Kotlin, Swift, C#, or JavaScript background.

5. **Sound null safety:** The language helps reduce null-related errors already
   at compile time.

#### Why Dart matters in Flutter:

Dart is not just "a language next to Flutter," but a core part of the ecosystem.
UI, business logic, state, async flows, and tests in Flutter are typically
written in Dart.

</details>
<details>
<summary>20. What is the difference between positional and named parameters in Dart?</summary>

#### Flutter

In Dart, function parameters can be **positional** or **named**.

#### Positional parameters:

Passed by order.

```dart
void printUser(String name, int age) {
  print('$name is $age years old');
}

printUser('Anna', 25);
```

#### Named parameters:

Passed by name, making calls more readable.

```dart
void printUser({required String name, required int age}) {
  print('$name is $age years old');
}

printUser(name: 'Anna', age: 25);
```

#### Main differences:

1. **Readability:** Named parameters are better for APIs with many arguments.

2. **Argument order:** Positional parameters depend on order; named parameters do
   not.

3. **Flexibility:** Named parameters usually scale better as parameter count
   grows.

#### Flutter practice:

In Flutter, most widget constructors heavily use **named parameters** because
they significantly improve UI code readability.

</details>
<details>
<summary>21. What is the difference between `var`, `final`, and `const`?</summary>

#### Flutter

In Dart, `var`, `final`, and `const` are used to declare variables, but they
have different semantics.

#### `var`

The type is inferred automatically, and the value can be changed.

```dart
var name = 'Flutter';
name = 'Dart';
```

#### `final`

The variable can be assigned only once, but its value may be known only at
runtime.

```dart
final currentTime = DateTime.now();
```

#### `const`

The value must be known at compile time.

```dart
const pi = 3.14159;
const appName = 'Flutter App';
```

#### Key difference:

1. **`var`** - regular mutable variable.
2. **`final`** - single assignment at runtime.
3. **`const`** - compile-time constant.

#### Practical nuance:

In Flutter, it is recommended to use `const` where possible, especially for
widgets, because this can reduce unnecessary object creation and rebuild overhead.

</details>
<details>
<summary>22. What are null-aware operators?</summary>

#### Flutter

Null-aware operators in Dart are special operators for safe work with `null`.

#### Main null-aware operators:

1. **`?.`** - calls a method or accesses a property only if the object is not
   `null`.
2. **`??`** - returns the right-side value if the left side is `null`.
3. **`??=`** - assigns a value only if the variable is `null`.
4. **`!`** - tells the compiler that the value is not `null`.

#### Examples:

```dart
String? name;
print(name?.length);

String result = name ?? 'Guest';

name ??= 'Anonymous';
```

#### `!` operator:

```dart
String? title;
print(title!.length);
```

This operator should be used carefully, because if the value is `null`, a
runtime error will occur.

#### Practical benefit:

Null-aware operators make code shorter, safer, and remove the need for excessive
manual null checks.

</details>
<details>
<summary>23. What is sound null safety in Dart?</summary>

#### Flutter

Sound null safety is a Dart mechanism that separates nullable and non-nullable
types and catches part of null-related errors at compile time.

#### Main idea:

If a type is declared as non-nullable, it cannot contain `null`.

```dart
String name = 'Flutter';
String? nullableName;
```

#### What this gives:

1. **Fewer runtime errors**
2. **Clearer type contracts**
3. **Better refactoring**
4. **More reliable production code**

#### How to read it:

- `String` - value must not be `null`
- `String?` - value may be `null`

#### Practical significance:

For large Flutter projects, sound null safety significantly reduces bugs related
to unexpected `null` values in UI, API models, and state management.

</details>
<details>
<summary>24. What are `async` and `await`?</summary>

#### Flutter

`async` and `await` in Dart are used for convenient work with asynchronous code.

#### `async`

Marks that a function performs asynchronous work and usually returns a `Future`.

#### `await`

Allows waiting for the result of an asynchronous operation without nested
callbacks.

#### Example:

```dart
Future<void> loadUser() async {
  final user = await fetchUser();
  print(user);
}
```

#### Benefits:

1. **Code reads like synchronous code**
2. **Less nesting**
3. **Simpler error handling via `try/catch`**

#### Example with error handling:

```dart
Future<void> loadData() async {
  try {
    final data = await fetchData();
    print(data);
  } catch (e) {
    print('Error: $e');
  }
}
```

</details>
<details>
<summary>25. What is `Future`?</summary>

#### Flutter

`Future` in Dart is an object that represents the result of an asynchronous
operation that will become available later.

#### In simple terms:

`Future` is a "promise" to produce one value or an error in the future.

#### Example:

```dart
Future<String> fetchUserName() async {
  await Future.delayed(const Duration(seconds: 1));
  return 'Viktor';
}
```

#### What a `Future` can complete with:

1. **Successful result**
2. **Error**

#### Working with `Future`:

```dart
final name = await fetchUserName();
```

or

```dart
fetchUserName()
    .then((value) => print(value))
    .catchError((error) => print(error));
```

#### Where it is used in Flutter:

- HTTP requests
- File reading
- Local database operations
- Service initialization
- Navigation, dialogs, permission flows

</details>
<details>
<summary>26. What is `Stream`?</summary>

#### Flutter

`Stream` is a sequence of asynchronous events or values that arrive over time.

#### Core idea:

If `Future` gives one value in the future, `Stream` can provide many values over
time.

#### Example:

```dart
Stream<int> counterStream() async* {
  for (int i = 1; i <= 3; i++) {
    await Future.delayed(const Duration(seconds: 1));
    yield i;
  }
}
```

#### Receiving values:

```dart
await for (final value in counterStream()) {
  print(value);
}
```

#### Where `Stream` is used:

1. **WebSocket**
2. **State propagation**
3. **Subscribing to database changes**
4. **UI events or system events**

#### In Flutter:

`Stream` is often used in BLoC, reactive data flows, and scenarios where
continuous updates matter, not one-time responses.

</details>
<details>
<summary>27. What is the difference between `Future` and `Stream`?</summary>

#### Flutter

`Future` and `Stream` are both used for asynchrony, but they solve different
tasks.

#### Core difference:

| Criterion         | `Future`                       | `Stream`                                   |
| ----------------- | ------------------------------ | ------------------------------------------ |
| Number of values  | One value or an error          | Many values over time                      |
| Completion        | Completes once                 | May run for long or complete later         |
| Typical scenario  | HTTP request, one-time read    | WebSocket, subscription, live updates      |

#### Examples:

- `Future`: load a user profile once.
- `Stream`: listen to real-time chat updates.

#### Practical rule:

If you need a response once, it is usually `Future`. If you need a stream of
updates, it is usually `Stream`.

</details>
<details>
<summary>28. What is the event loop in Dart?</summary>

#### Flutter

The event loop in Dart is a mechanism that controls execution of asynchronous
tasks in a single isolate.

#### How it works:

1. **Synchronous code runs immediately**
2. **Asynchronous tasks are placed into queues**
3. **The event loop takes tasks one by one and executes them**

#### Main queues:

1. **Microtask queue** - has higher priority.
2. **Event queue** - regular asynchronous events.

#### Example:

```dart
void main() {
  print('1');

  Future(() => print('2'));
  scheduleMicrotask(() => print('3'));

  print('4');
}
```

The output will be:

```text
1
4
3
2
```

#### Why it matters:

Understanding the event loop helps you correctly work with `Future`, `Stream`,
microtasks, UI responsiveness, and avoid unexpected code execution order.

</details>
<details>
<summary>29. What are mixins in Dart?</summary>

#### Flutter

Mixins in Dart are a mechanism for code reuse between classes without classical
multiple inheritance.

#### What they are used for:

1. **Behavior reuse**
2. **Adding shared logic to multiple classes**
3. **Composing capabilities without a rigid hierarchy**

#### Example:

```dart
mixin LoggerMixin {
  void log(String message) {
    print('LOG: $message');
  }
}

class UserService with LoggerMixin {
  void loadUser() {
    log('Loading user...');
  }
}
```

#### In Flutter, common mixins include:

- `SingleTickerProviderStateMixin`
- `TickerProviderStateMixin`
- `AutomaticKeepAliveClientMixin`

#### Practical significance:

Mixins are useful when you need to share behavior across multiple classes, but
that behavior should not be a separate base class.

</details>
<details>
<summary>30. What are extension methods?</summary>

#### Flutter

Extension methods in Dart allow adding new methods or getters to existing types
without changing their source code.

#### Example:

```dart
extension StringX on String {
  bool get isEmail => contains('@');
}
```

Now you can write:

```dart
final result = 'test@example.com'.isEmail;
```

#### Why this is useful:

1. **Improved readability**
2. **Moving utility logic closer to the type**
3. **Reducing extra helper classes**

#### Typical examples in Flutter:

- Extensions for `BuildContext`
- Extensions for `String`, `DateTime`, `num`
- Extensions for theme, spacing, localization

#### Important:

Extension methods improve code API ergonomics, but should not be overused. If an
extension starts hiding complex business logic, it usually makes code less
predictable.

</details>
<details>
<summary>31. What is `typedef` in Dart?</summary>

#### Flutter

`typedef` in Dart is used to create type aliases, most often for function types.

#### Example:

```dart
typedef OnUserTap = void Function(String userId);
```

Now this type can be used like this:

```dart
class UserTile {
  final OnUserTap onTap;

  UserTile({required this.onTap});
}
```

#### Why it is needed:

1. **Improves API readability**
2. **Adds semantic meaning to functional types**
3. **Simplifies reuse of identical signatures**

#### Where this is useful in Flutter:

- Callbacks in widgets
- DI and service contracts
- State management APIs
- Stream/listener contracts

</details>

<details>
<summary>32. What is a factory constructor?</summary>

#### Flutter

A factory constructor in Dart is a constructor that does not necessarily create
a new class instance every time it is called.

#### Main capabilities:

1. **Can return a cached object**
2. **Can return a subclass instance**
3. **Can contain additional logic before object creation**

#### Example:

```dart
class Logger {
  static final Map<String, Logger> _cache = {};

  final String name;

  factory Logger(String name) {
    return _cache.putIfAbsent(name, () => Logger._internal(name));
  }

  Logger._internal(this.name);
}
```

#### What happens here:

Instead of creating a new `Logger` every time, the factory constructor returns
an already existing instance for the same `name`.

#### Where it is commonly used:

- Singleton-like scenarios
- Model parsing
- Abstractions where instance creation must be controlled

#### Important:

A factory constructor differs from a regular constructor because it has no
direct access to `this`, since the object may not be created yet.

</details>

<details>
<summary>33. How does the layout system work in Flutter?</summary>

#### Flutter

Flutter's layout system follows the principle: **constraints go down, sizes go
up, parent sets position**.

#### How it looks in practice:

1. **The parent widget passes constraints down**
2. **The child widget chooses its size within those constraints**
3. **The parent widget determines the child's position**

#### Core idea:

Flutter does not use an XML-layout system like Android View hierarchy.
Instead, each widget participates in a clear model for computing size and
position.

#### Why this matters:

- Helps understand overflow-type errors.
- Makes behavior of `Row`, `Column`, `Expanded`, `Flexible` predictable.
- Critical for building adaptive interfaces.

#### Practical rule:

If a layout "breaks", in most cases you need to inspect constraints received by
the widget from its parent.

</details>

<details>
<summary>34. Which main widgets are used to build layouts?</summary>

#### Flutter

In Flutter, layout building most often uses basic layout widgets that compose
nearly the entire interface.

#### Main layout widgets:

1. **`Row`** - horizontal arrangement of elements
2. **`Column`** - vertical arrangement of elements
3. **`Container`** - universal wrapper widget
4. **`SizedBox`** - fixed size or spacing
5. **`Expanded`** - takes available space
6. **`Flexible`** - flexible use of space
7. **`Stack`** - overlays elements on top of each other
8. **`Padding`** - inner spacing
9. **`Align` / `Center`** - alignment
10. **`ListView`** - scrollable lists
11. **`Wrap`** - moves elements to a new line
12. **`Scaffold`** - base screen structure

#### Practical significance:

On most screens, Flutter layout is built not with one "big layout", but with a
combination of simple widgets.

</details>

<details>
<summary>35. What is the difference between `Row` and `Column`?</summary>

#### Flutter

`Row` and `Column` are basic flex widgets in Flutter, but they work in
different directions.

#### `Row`

Places children **horizontally**.

```dart
Row(
  children: const [
    Text('A'),
    Text('B'),
    Text('C'),
  ],
)
```

#### `Column`

Places children **vertically**.

```dart
Column(
  children: const [
    Text('A'),
    Text('B'),
    Text('C'),
  ],
)
```

#### Core difference:

1. **`Row`** works along the horizontal axis
2. **`Column`** works along the vertical axis

#### Important:

Both `Row` and `Column` can cause overflow if their children do not fit into
the available space.

</details>

<details>
<summary>36. What are `mainAxisAlignment` and `crossAxisAlignment`?</summary>

#### Flutter

`mainAxisAlignment` and `crossAxisAlignment` are alignment parameters in
flex-based widgets such as `Row` and `Column`.

#### Core logic:

1. **`mainAxisAlignment`** controls alignment along the main axis
2. **`crossAxisAlignment`** controls alignment along the cross axis

#### For `Row`:

- Main axis = horizontal
- Cross axis = vertical

#### For `Column`:

- Main axis = vertical
- Cross axis = horizontal

#### Example:

```dart
Row(
  mainAxisAlignment: MainAxisAlignment.spaceBetween,
  crossAxisAlignment: CrossAxisAlignment.center,
  children: const [
    Text('Left'),
    Text('Right'),
  ],
)
```

#### Common values:

- `MainAxisAlignment.start`
- `MainAxisAlignment.center`
- `MainAxisAlignment.end`
- `MainAxisAlignment.spaceBetween`
- `CrossAxisAlignment.start`
- `CrossAxisAlignment.center`
- `CrossAxisAlignment.end`
- `CrossAxisAlignment.stretch`

</details>

<details>
<summary>37. What is the `Container` widget?</summary>

#### Flutter

`Container` is a universal wrapper widget that allows you to define size,
spacing, alignment, decoration, and other layout properties.

#### What it can do:

1. **Set `width` and `height`**
2. **Add `padding` and `margin`**
3. **Apply `decoration`**
4. **Align a child widget**
5. **Paint background color**

#### Example:

```dart
Container(
  width: 200,
  height: 100,
  padding: const EdgeInsets.all(16),
  decoration: BoxDecoration(
    color: Colors.blue,
    borderRadius: BorderRadius.circular(12),
  ),
  child: const Text('Hello'),
)
```

#### Important:

`Container` is convenient, but not always optimal as a "widget for everything."
If you need only one simple function, a specialized widget is often better, such
as `Padding`, `ColoredBox`, `SizedBox`, or `Align`.

</details>

<details>
<summary>38. What is the `SizedBox` widget?</summary>

#### Flutter

`SizedBox` is a widget that sets a fixed size for a child element or is used as
a simple spacer.

#### Main scenarios:

1. **Fixed width or height**
2. **Empty spacing between elements**
3. **Constraining a child widget's size**

#### Example:

```dart
const SizedBox(height: 16)
```

or

```dart
SizedBox(
  width: 200,
  child: ElevatedButton(
    onPressed: () {},
    child: const Text('Submit'),
  ),
)
```

#### Practical tip:

For simple spacing between elements, `SizedBox` is usually more readable and
lighter than `Container`.

</details>

<details>
<summary>39. What is the `Expanded` widget?</summary>

#### Flutter

`Expanded` is a widget that forces its child to occupy all available free space
inside `Row`, `Column`, or `Flex`.

#### How it works:

`Expanded` tells Flutter: "give this element as much remaining space as
possible."

#### Example:

```dart
Row(
  children: [
    const Icon(Icons.menu),
    Expanded(
      child: Container(
        height: 40,
        color: Colors.blue,
      ),
    ),
  ],
)
```

#### Additionally:

You can use `flex` to control proportions.

```dart
Expanded(
  flex: 2,
  child: Container(color: Colors.red),
)
```

#### Important:

`Expanded` works only inside `Flex`-based widgets: `Row`, `Column`, `Flex`.

</details>

<details>
<summary>40. What is the `Flexible` widget?</summary>

#### Flutter

`Flexible` is a widget for flexible space distribution inside `Row`, `Column`,
or `Flex`.

#### Difference from `Expanded`:

- `Expanded` forces an element to take all available space.
- `Flexible` allows an element to use space more flexibly.

#### Example:

```dart
Row(
  children: [
    Flexible(
      child: Text(
        'Very long text that can wrap',
      ),
    ),
  ],
)
```

#### Practical significance:

`Flexible` is useful when an element should adapt to available space, but does
not necessarily need to stretch to the maximum.

</details>

<details>
<summary>41. What is the `Spacer` widget?</summary>

#### Flutter

`Spacer` is a special flex widget that occupies free space between other
elements.

#### Example:

```dart
Row(
  children: const [
    Text('Left'),
    Spacer(),
    Text('Right'),
  ],
)
```

#### What it is used for:

1. **Pushing elements apart**
2. **Building adaptive space in `Row` or `Column`**
3. **Improving code readability instead of manual spacing calculations**

#### Important:

`Spacer` effectively works like `Expanded` with an empty child.

</details>

<details>
<summary>42. What is the `Stack` widget?</summary>

#### Flutter

`Stack` is a layout widget that allows placing elements on top of each other.

#### When it is used:

1. **Overlay interfaces**
2. **Badges on top of images**
3. **Buttons over content**
4. **Complex UI compositions**

#### Example:

```dart
Stack(
  children: [
    Image.network('https://example.com/image.png'),
    const Positioned(
      top: 8,
      right: 8,
      child: Icon(Icons.favorite, color: Colors.red),
    ),
  ],
)
```

#### Important:

In `Stack`, child order matters: later children are painted above previous ones.

</details>

<details>
<summary>43. What is `Positioned`?</summary>

#### Flutter

`Positioned` is a widget used inside `Stack` for precise child positioning.

#### What you can set:

1. **`top`**
2. **`bottom`**
3. **`left`**
4. **`right`**
5. **`width`**
6. **`height`**

#### Example:

```dart
Stack(
  children: const [
    Positioned(
      top: 10,
      right: 10,
      child: Text('Badge'),
    ),
  ],
)
```

#### Important:

`Positioned` works only as a direct child inside `Stack`.

</details>

<details>
<summary>44. What is `LayoutBuilder`?</summary>

#### Flutter

`LayoutBuilder` is a widget that allows building UI based on constraints
received from the parent widget.

#### When it is useful:

1. **Adaptive layout**
2. **Different behavior for narrow and wide screens**
3. **Cases where available space is needed during build**

#### Example:

```dart
LayoutBuilder(
  builder: (context, constraints) {
    if (constraints.maxWidth > 600) {
      return const Text('Tablet layout');
    }
    return const Text('Phone layout');
  },
)
```

#### Practical significance:

`LayoutBuilder` is especially useful when decisions should be made not by full
screen size, but by real space available to a specific widget.

</details>

<details>
<summary>45. What is `MediaQuery`?</summary>

#### Flutter

`MediaQuery` is a mechanism to access information about the current display
environment: screen size, orientation, padding, text scale factor, and other
metrics.

#### What you can get through `MediaQuery`:

1. **Screen size**
2. **Orientation**
3. **Safe area insets**
4. **Text scale settings**

#### Example:

```dart
final size = MediaQuery.of(context).size;
final width = size.width;
```

#### Important:

`MediaQuery` is good for screen-level adaptation, but for local constraints of a
specific widget, `LayoutBuilder` is often the better choice.

</details>

<details>
<summary>46. What is `SingleChildScrollView`?</summary>

#### Flutter

`SingleChildScrollView` is a scroll widget for one child element that allows
scrolling content if it does not fit on the screen.

#### When it is used:

1. **Forms**
2. **Small screens with vertical content**
3. **Content that usually fits, but may overflow in some cases**

#### Example:

```dart
SingleChildScrollView(
  child: Column(
    children: const [
      Text('Section 1'),
      Text('Section 2'),
    ],
  ),
)
```

#### Important:

For large lists, `SingleChildScrollView` is not as suitable as `ListView`,
because it renders all child content at once.

</details>

<details>
<summary>47. What is `ListView.builder`?</summary>

#### Flutter

`ListView.builder` is an efficient way to build large or dynamic lists in
Flutter.

#### Why it matters:

Unlike static `ListView(children: [...])`, `ListView.builder` creates items
lazily, only when needed.

#### Example:

```dart
ListView.builder(
  itemCount: 100,
  itemBuilder: (context, index) {
    return ListTile(
      title: Text('Item $index'),
    );
  },
)
```

#### Advantages:

1. **Better performance on large lists**
2. **Lower memory usage**
3. **Convenient handling of dynamic data**

</details>

<details>
<summary>48. What is `AspectRatio`?</summary>

#### Flutter

`AspectRatio` is a widget that preserves a given width-to-height ratio.

#### Example:

```dart
AspectRatio(
  aspectRatio: 16 / 9,
  child: Container(
    color: Colors.blue,
  ),
)
```

#### When it is used:

1. **Images**
2. **Video players**
3. **Cards with fixed proportions**
4. **Adaptive UI blocks**

#### Practical significance:

`AspectRatio` simplifies building elements that should keep proportional shape
across different screens.

</details>

<details>
<summary>49. What is `Visibility`?</summary>

#### Flutter

`Visibility` is a widget that lets you control whether a child element is shown.

#### Main scenario:

Show or hide an element based on a condition.

#### Example:

```dart
Visibility(
  visible: isLoading,
  child: const CircularProgressIndicator(),
)
```

#### What is important to know:

`Visibility` has additional parameters that let you control whether to preserve
the hidden element's size, state, animation, and semantic information.

#### Practical nuance:

If you only need simple conditional rendering, a regular `if` or ternary
expression is sometimes more readable. `Visibility` is useful when you need
finer control of hidden widget behavior.

</details>

<details>
<summary>50. What is state in Flutter?</summary>

#### Flutter

State in Flutter is data that determines how the UI looks or behaves at a
specific point in time.

#### In simple terms:

If a value changes and the interface should update because of it, that is state.

#### Examples of state:

1. **Counter value**
2. **Text in an input field**
3. **Loading status**
4. **Selected tab**
5. **List of data received from API**

#### Why this matters:

Flutter is a declarative framework. This means UI is described as a function of
the current state.

#### Practical significance:

Working with Flutter is largely about correctly answering: "where should this
state live, who owns it, and who should react to it?"

</details>

<details>
<summary>51. What is the difference between local state (ephemeral state) and app state?</summary>

#### Flutter

The difference between ephemeral state and app state is in responsibility scope
and data lifetime.

#### Ephemeral state:

This is local state of a specific widget or a small part of UI.

#### Examples:

1. **Current checkbox value**
2. **Section open/close state**
3. **Current index in `PageView`**

#### App state:

This is state that matters for a significant part of the app or must live
longer than one specific widget.

#### Examples:

1. **User authentication**
2. **App theme**
3. **E-commerce cart**
4. **User profile**

#### Core difference:

| Criterion | Ephemeral state                | App state                          |
| --------- | ------------------------------ | ---------------------------------- |
| Scope     | One widget or small UI block   | Multiple screens or whole app      |
| Lifetime  | Short                          | Longer                             |
| Examples  | Animation, selection, input    | Auth, cart, settings, user data    |

#### Practical rule:

Do not lift local state to global level without a reason. It only makes
architecture more complex.

</details>

<details>
<summary>52. How does `setState()` work?</summary>

#### Flutter

`setState()` is a method in `StatefulWidget` that notifies Flutter that state
has changed and the related UI part should rebuild.

#### How it works:

1. **You change local state**
2. **Wrap this change in `setState()`**
3. **Flutter marks the widget as dirty**
4. **The framework calls `build()` again**

#### Example:

```dart
setState(() {
  counter++;
});
```

#### Important to understand:

`setState()` does not "draw UI itself." It only triggers rebuild for this
`State` object.

#### When it fits:

- Simple local state
- Small interactive elements
- Quick prototypes

#### When it does not fit:

If state is used across many screens or has a complex lifecycle, it is better
to use a separate state management approach.

</details>

<details>
<summary>53. Which state management approaches are used in Flutter?</summary>

#### Flutter

Flutter has several popular state management approaches. The choice depends on
project scale, domain complexity, and maintainability requirements.

#### Main approaches:

1. **`setState()`** - for simple local state
2. **`InheritedWidget`** - base mechanism for dependency propagation in tree
3. **`Provider`** - simple and popular wrapper over `InheritedWidget`
4. **BLoC / Cubit** - separation of UI and business logic via streams or state classes
5. **Riverpod** - more modern approach with better testability and dependency graph
6. **Redux** - centralized state store
7. **`ValueNotifier` / `ChangeNotifier`** - lightweight reactive models

#### Practical approach:

- For a small screen, `setState()` is often enough
- For medium apps, `Provider` or Riverpod often fits
- For complex business logic, BLoC or Riverpod is often chosen

#### Main idea:

There is no "single correct" state management solution. The right choice is the
one that keeps code understandable, predictable, and maintainable.

</details>

<details>
<summary>54. What is `Provider`?</summary>

#### Flutter

`Provider` is a popular library for dependency injection and state management in
Flutter, built on top of `InheritedWidget`.

#### What it provides:

1. **Access to objects higher in the tree**
2. **UI updates when state changes**
3. **Simpler API than raw `InheritedWidget`**

#### Example:

```dart
ChangeNotifierProvider(
  create: (_) => CounterNotifier(),
  child: const MyApp(),
)
```

Then in a widget:

```dart
final counter = context.watch<CounterNotifier>();
```

#### Why `Provider` became popular:

- Low entry barrier
- Good fit for small and medium apps
- Simple for teams that do not want complex reactive architecture

#### Limitations:

In large projects with complex dependency graphs and a lot of state, `Provider`
can become less convenient than Riverpod or BLoC.

</details>

<details>
<summary>55. What is BLoC architecture?</summary>

#### Flutter

BLoC (Business Logic Component) is an architecture approach where business logic
is separated from UI and interacts with it through events and states.

#### Core idea:

1. **UI sends an event**
2. **BLoC handles the logic**
3. **BLoC emits a new state**
4. **UI reacts to state**

#### Advantages:

1. **Clear separation of responsibilities**
2. **Predictable data flow**
3. **Good testability**
4. **Convenient for complex logic**

#### Typical elements:

- `Event`
- `State`
- `Bloc`
- `BlocBuilder`
- `BlocListener`

#### Practical significance:

BLoC is a good fit for medium and large apps where architecture discipline,
domain logic separation, and controlled data flow are important.

</details>

<details>
<summary>56. What is Riverpod?</summary>

#### Flutter

Riverpod is a modern library for state management and dependency injection in
Flutter, created as an evolution of `Provider` ideas.

#### What Riverpod provides:

1. **Better dependency control**
2. **No strict coupling to `BuildContext`**
3. **Better testability**
4. **Safer and more declarative API**

#### Core idea:

State and dependencies are described through providers, and UI or services
explicitly subscribe to them.

#### Why it is often chosen:

- Easier to scale large codebases
- Less hidden widget tree magic
- More convenient async state handling

#### Practical observation:

In modern Flutter projects, Riverpod is often considered one of the strongest
options for long-term product maintenance.

</details>

<details>
<summary>57. What is Redux in Flutter?</summary>

#### Flutter

Redux in Flutter is a state management approach with a single centralized store,
where state changes through actions and reducers.

#### Main Redux elements:

1. **Store** - single source of truth
2. **Action** - description of intent to change state
3. **Reducer** - function that computes new state
4. **Middleware** - place for async logic and side effects

#### Advantages:

1. **Predictable data flow**
2. **Centralized state**
3. **Transparent changes**

#### Disadvantages:

1. **A lot of boilerplate**
2. **Can be excessive for Flutter UI**
3. **Often less convenient than modern approaches**

#### Practical conclusion:

Redux has historical value and strong discipline, but in modern Flutter projects
it is used less often than Riverpod, Provider, or BLoC.

</details>

<details>
<summary>58. What is `ValueNotifier`?</summary>

#### Flutter

`ValueNotifier<T>` is a simple reactive class in Flutter that stores one value
and notifies listeners when that value changes.

#### Example:

```dart
final counter = ValueNotifier<int>(0);

counter.value++;
```

#### What it is used for:

1. **Simple local or screen-level state**
2. **Minimalistic reactive scenarios**
3. **When you do not want full state management setup**

#### What it works with:

Most often with `ValueListenableBuilder`.

```dart
ValueListenableBuilder<int>(
  valueListenable: counter,
  builder: (context, value, child) {
    return Text('$value');
  },
)
```

#### Practical significance:

`ValueNotifier` is a good lightweight tool when state is simple and does not
require complex architecture.

</details>

<details>
<summary>59. What is `InheritedWidget`?</summary>

#### Flutter

`InheritedWidget` is the base Flutter mechanism for passing data down the widget
tree and updating dependent widgets when that data changes.

#### Main role:

1. **Propagating shared data through a subtree**
2. **Accessing dependencies via `BuildContext`**
3. **Optimized updates only for subscribed widgets**

#### Where it is used:

- `Theme`
- `MediaQuery`
- `Directionality`
- `Provider` and other libraries under the hood

#### Why this matters:

`InheritedWidget` is a fundamental Flutter mechanism. Even if a team does not
write it manually, many popular libraries are built on top of it.

</details>

<details>
<summary>60. What is the difference between `Provider` and `InheritedWidget`?</summary>

#### Flutter

`InheritedWidget` is Flutter's base mechanism, while `Provider` is a convenient
library abstraction on top of it.

#### Main difference:

| Criterion     | `InheritedWidget`                     | `Provider`                    |
| ------------- | ------------------------------------- | ----------------------------- |
| Level         | Low-level core API                    | High-level abstraction        |
| Convenience   | Requires more manual code             | Much easier to use            |
| Boilerplate   | More                                  | Less                          |
| Scalability   | Less convenient directly for most teams | Better for real apps        |

#### Practical conclusion:

- If you need to understand Flutter fundamentals, you should know `InheritedWidget`
- If you need to build app-level state quickly and conveniently, teams more often use `Provider`

#### Key idea:

`Provider` does not replace the `InheritedWidget` concept; it makes it more
convenient for everyday development.

</details>

<details>
<summary>61. How does navigation work in Flutter?</summary>

#### Flutter

Navigation in Flutter is built around a stack of routes. When a user moves to a
new screen, a new route is added to the stack, and when they go back, the top
route is removed.

#### Core idea:

1. **Current screen is the top stack element**
2. **A new transition adds a new route**
3. **Back navigation removes the top route**

#### How it looks in practice:

- Forward navigation: `push`
- Back navigation: `pop`

#### Navigation options:

1. **Imperative navigation** via `Navigator`
2. **Named routes**
3. **Router API / declarative navigation**
4. **Packages like `go_router` or `auto_route`**

#### Practical conclusion:

For simple apps, basic `Navigator` is often enough. For larger products with
deep links, web navigation, and complex routing, a router-based approach is more
common.

</details>

<details>
<summary>62. What is `Navigator`?</summary>

#### Flutter

`Navigator` is Flutter's core mechanism for managing transitions between screens.

#### What it does:

1. **Stores route stack**
2. **Adds new screens**
3. **Removes current screens**
4. **Returns result back to previous screen**

#### Example role of `Navigator`:

It can be viewed as a page stack where the last opened page is active.

#### Example:

```dart
Navigator.of(context).push(
  MaterialPageRoute(
    builder: (_) => const DetailsPage(),
  ),
);
```

#### Important:

`Navigator` is tightly connected to `BuildContext`, so it should be called from
a context that has access to the required navigation tree.

</details>

<details>
<summary>63. What do `Navigator.push()` and `Navigator.pop()` do?</summary>

#### Flutter

`Navigator.push()` adds a new screen to the navigation stack, and
`Navigator.pop()` goes back by removing the top screen from the stack.

#### `Navigator.push()`

Opens a new route.

```dart
Navigator.push(
  context,
  MaterialPageRoute(
    builder: (_) => const DetailsPage(),
  ),
);
```

#### `Navigator.pop()`

Closes the current route.

```dart
Navigator.pop(context);
```

#### Additionally:

`pop()` can return a value back:

```dart
Navigator.pop(context, 'success');
```

#### Practical significance:

These are the basic navigation methods in most Flutter apps and one of the
first APIs you should know confidently for interviews.

</details>

<details>
<summary>64. How to pass data between screens in Flutter?</summary>

#### Flutter

Data between screens in Flutter is most often passed through the destination
screen route constructor, or through a result returned back from
`Navigator.pop()`.

#### Forward passing through constructor:

```dart
Navigator.push(
  context,
  MaterialPageRoute(
    builder: (_) => DetailsPage(userId: '42'),
  ),
);
```

#### Receiver screen:

```dart
class DetailsPage extends StatelessWidget {
  final String userId;

  const DetailsPage({super.key, required this.userId});

  @override
  Widget build(BuildContext context) {
    return Text(userId);
  }
}
```

#### Returning data back:

```dart
final result = await Navigator.push<String>(
  context,
  MaterialPageRoute(
    builder: (_) => const DetailsPage(),
  ),
);
```

And back:

```dart
Navigator.pop(context, 'done');
```

#### Other options:

1. **Named routes arguments**
2. **Global/app state**
3. **State management via Provider, Riverpod, BLoC**

#### Practical rule:

One-time screen-to-screen data should be passed explicitly via constructor. You
do not need to introduce global state for this immediately.

</details>

<details>
<summary>65. What is `ModalBottomSheet`?</summary>

#### Flutter

`ModalBottomSheet` is a bottom modal panel that appears above current content
and blocks interaction with the background until it is closed.

#### What it is used for:

1. **Content actions**
2. **Option selection**
3. **Filters**
4. **Short interaction forms**

#### Example:

```dart
showModalBottomSheet(
  context: context,
  builder: (context) {
    return const Padding(
      padding: EdgeInsets.all(16),
      child: Text('Bottom Sheet'),
    );
  },
);
```

#### Important:

- This is a **modal** component
- It can be closed by gesture or via `Navigator.pop(context)`

#### Practical significance:

`ModalBottomSheet` is often used in mobile UI instead of a separate screen or
dialog when you need quick contextual interaction.

</details>

<details>
<summary>66. What is theme (`Theme`) in Flutter?</summary>

#### Flutter

Theme in Flutter is a centralized set of app visual settings: colors,
typography, button styles, input field styles, app bar styles, and other
component styles.

#### Why it is needed:

1. **Unified visual style**
2. **Easy design changes in one place**
3. **Light/dark mode support**
4. **UI consistency across the app**

#### Example:

```dart
MaterialApp(
  theme: ThemeData(
    colorScheme: ColorScheme.fromSeed(seedColor: Colors.blue),
    useMaterial3: true,
  ),
  home: const HomePage(),
)
```

#### Theme access:

```dart
final theme = Theme.of(context);
```

#### Practical conclusion:

In production apps, theme is an important part of the design system, not just a
set of colors.

</details>

<details>
<summary>67. What is the difference between Material and Cupertino widgets?</summary>

#### Flutter

Material and Cupertino are two different sets of UI components in Flutter that
match different platform design systems.

#### Material:

- Focused on **Google Material Design**
- More often used as default Flutter approach
- Main widgets: `MaterialApp`, `Scaffold`, `AppBar`, `ElevatedButton`

#### Cupertino:

- Focused on **Apple Human Interface Guidelines**
- Provides iOS-style look and behavior
- Main widgets: `CupertinoApp`, `CupertinoPageScaffold`, `CupertinoButton`,
  `CupertinoNavigationBar`

#### Core difference:

| Criterion        | Material                    | Cupertino       |
| ---------------- | --------------------------- | --------------- |
| Design           | Google Material             | Apple iOS style |
| Components       | Android-first style         | iOS-first style |
| Typical use case | Cross-platform default UI   | iOS-native feel |

#### Practical approach:

Many teams use Material as the base even for cross-platform apps. But if the
product needs a maximally native iOS feel, Cupertino becomes important.

</details>

<details>
<summary>68. How to implement adaptive UI in Flutter?</summary>

#### Flutter

Adaptive UI in Flutter is implemented through a combination of responsive
layout, flexible widgets, and logic that considers screen size and device
characteristics.

#### Main tools:

1. **`LayoutBuilder`**
2. **`MediaQuery`**
3. **`Expanded` / `Flexible`**
4. **`Wrap`**
5. **`AspectRatio`**
6. **Conditional rendering for different breakpoints**

#### Example approach:

```dart
LayoutBuilder(
  builder: (context, constraints) {
    if (constraints.maxWidth > 900) {
      return const DesktopLayout();
    }
    if (constraints.maxWidth > 600) {
      return const TabletLayout();
    }
    return const MobileLayout();
  },
)
```

#### Practical principles:

- Do not hardcode everything in pixels
- Consider portrait and landscape
- Consider tablet, foldable, desktop, and web
- Keep breakpoint logic in a clear structure

#### Practical conclusion:

Adaptiveness in Flutter is not one widget. It is a layout discipline so UI
scales correctly across different form factors.

</details>

<details>
<summary>69. What is `FittedBox`?</summary>

#### Flutter

`FittedBox` is a widget that scales and positions its child so it fits the
available space according to selected `fit`.

#### What it is used for:

1. **Scaling text or icons**
2. **Adapting content to container**
3. **Avoiding overflow in some layout scenarios**

#### Example:

```dart
FittedBox(
  fit: BoxFit.scaleDown,
  child: Text(
    'Very long title',
    style: TextStyle(fontSize: 32),
  ),
)
```

#### Important:

`FittedBox` does not "fix" all layout issues. It should be used when content
scaling is really needed, not as a replacement for proper constraints handling.

#### Practical significance:

It is a useful tool for edge cases in responsive UI, but not the foundation of
layout architecture.

</details>

<details>
<summary>70. What are isolates in Flutter?</summary>

#### Flutter

Isolates in Dart/Flutter are separate execution units with their own memory and
their own event loop.

#### Core idea:

Unlike classic threads with shared memory, isolates do not share state directly.

#### What this means:

1. **Each isolate has its own heap**
2. **Each isolate executes independently**
3. **Data is not shared directly between isolates**

#### Why this matters:

This approach reduces risk of race conditions and shared-memory problems.

#### Practical significance in Flutter:

UI usually runs in the main isolate. Heavy computations can be moved to another
isolate to avoid blocking the interface.

</details>

<details>
<summary>71. What are isolates used for?</summary>

#### Flutter

Isolates are used to move heavy or long-running tasks out of the main isolate
where UI runs.

#### Typical scenarios:

1. **Heavy computations**
2. **Parsing large JSON**
3. **File processing**
4. **Data encryption or decoding**
5. **CPU-intensive business logic**

#### Why this is needed:

If heavy synchronous work runs in the main isolate, UI can lag, drop frames, or
"freeze."

#### Practical conclusion:

Isolates are needed not for every async operation, but specifically for
CPU-bound tasks. For regular HTTP requests or I/O, `Future` and `async/await`
are usually enough.

</details>

<details>
<summary>72. How do isolates communicate with each other?</summary>

#### Flutter

Isolates communicate through message passing, not shared memory.

#### Main mechanisms:

1. **`SendPort`** - for sending messages
2. **`ReceivePort`** - for receiving messages

#### Example idea:

One isolate sends data to another isolate via message passing.

#### Important:

- isolates cannot directly mutate a shared object
- data is transferred through serialized or transferable messages

#### Practical significance:

This model is more complex than regular async calls, but makes parallel
execution safer and more predictable.

</details>

<details>
<summary>73. Which stream types exist in Dart?</summary>

#### Flutter

In Dart, two main stream types are most commonly used: **single-subscription**
and **broadcast streams**.

#### 1. Single-subscription stream

This stream is intended for one listener.

#### Features:

1. **Has one subscriber**
2. **Suitable for sequential data flow**
3. **Often used for file I/O or async data pipelines**

#### 2. Broadcast stream

This stream allows multiple listeners to subscribe at the same time.

#### Features:

1. **Has many subscribers**
2. **Suitable for events**
3. **Similar to event bus / signal source**

#### Practical conclusion:

If a data source has one consumer, single-subscription stream is usually enough.
If events must be delivered to multiple listeners, broadcast stream is used.

</details>

<details>
<summary>74. What is `FutureBuilder`?</summary>

#### Flutter

`FutureBuilder` is a Flutter widget that builds UI based on a `Future` state.

#### What it is used for:

1. **Showing loading**
2. **Showing successful result**
3. **Showing error**

#### Example:

```dart
FutureBuilder<String>(
  future: fetchUserName(),
  builder: (context, snapshot) {
    if (snapshot.connectionState == ConnectionState.waiting) {
      return const CircularProgressIndicator();
    }

    if (snapshot.hasError) {
      return Text('Error: ${snapshot.error}');
    }

    return Text(snapshot.data ?? '');
  },
)
```

#### What `snapshot` provides:

1. **`connectionState`**
2. **`hasData`**
3. **`hasError`**
4. **`data`**
5. **`error`**

#### Practical nuance:

Avoid creating `Future` directly inside `build()` without need, otherwise it may
restart on every rebuild.

</details>

<details>
<summary>75. What is `StreamBuilder`?</summary>

#### Flutter

`StreamBuilder` is a Flutter widget that builds UI based on values coming from a
`Stream`.

#### Main difference from `FutureBuilder`:

- `FutureBuilder` works with one-time result
- `StreamBuilder` works with a stream of updates over time

#### Example:

```dart
StreamBuilder<int>(
  stream: counterStream(),
  builder: (context, snapshot) {
    if (snapshot.hasError) {
      return Text('Error: ${snapshot.error}');
    }

    if (!snapshot.hasData) {
      return const CircularProgressIndicator();
    }

    return Text('Value: ${snapshot.data}');
  },
)
```

#### Typical scenarios:

1. **WebSocket updates**
2. **Live data**
3. **BLoC state streams**
4. **Reactive events**

#### Practical significance:

`StreamBuilder` is convenient for reactive UI, but stream lifecycle should be
controlled to avoid extra subscriptions or memory leaks.

</details>

<details>
<summary>76. How do animations work in Flutter?</summary>

#### Flutter

Animations in Flutter work through sequential value changes over time and UI
repainting on each frame.

#### Core idea:

1. **There is a start value**
2. **There is an end value**
3. **Flutter computes intermediate states**
4. **UI updates frame by frame**

#### Main components:

1. **`AnimationController`** - controls animation time
2. **`Tween`** - defines value range
3. **`CurvedAnimation`** - defines motion curve
4. **Builder or Animated widget** - updates UI

#### Two main approaches:

1. **Implicit animations** - simple animations without manual control
2. **Explicit animations** - full control via controller

#### Practical significance:

Flutter has a very strong animation system because UI is drawn by its own
rendering engine, which gives high flexibility for smooth transitions and custom
motion.

</details>

<details>
<summary>77. What is `AnimationController`?</summary>

#### Flutter

`AnimationController` is an object that controls explicit animation lifecycle:
start, stop, reverse, and current progress.

#### What it does:

1. **Stores animation duration**
2. **Moves across a value scale, usually from `0.0` to `1.0`**
3. **Lets you run `forward()`, `reverse()`, `repeat()`**

#### Example:

```dart
late final AnimationController controller;

@override
void initState() {
  super.initState();
  controller = AnimationController(
    vsync: this,
    duration: const Duration(milliseconds: 300),
  );
}
```

#### Important:

`AnimationController` usually must be `dispose()`-d, otherwise resource leaks
are possible.

</details>

<details>
<summary>78. What is Tween animation?</summary>

#### Flutter

Tween animation is an animation where a value changes smoothly between two
points: `begin` and `end`.

#### Core idea:

Tween describes **how exactly to interpolate values**.

#### Example:

```dart
final animation = Tween<double>(
  begin: 0,
  end: 100,
).animate(controller);
```

#### What can be animated via Tween:

1. **Numbers**
2. **Colors**
3. **Paddings**
4. **Sizes**
5. **Alignment**

#### Practical significance:

Tween does not start animation by itself. It only describes the value transition,
and `AnimationController` drives that transition.

</details>

<details>
<summary>79. What is `vsync`?</summary>

#### Flutter

`vsync` is a mechanism for synchronizing animation with the screen refresh rate.

#### Why it is needed:

1. **To avoid frame calculations when widget is not visible**
2. **To reduce unnecessary load**
3. **To keep animations synced with rendering pipeline**

#### How it looks:

In `State`, `SingleTickerProviderStateMixin` is often used and `this` is passed
to `AnimationController`.

```dart
controller = AnimationController(
  vsync: this,
  duration: const Duration(milliseconds: 300),
);
```

#### Practical significance:

Without `vsync`, animations could continue running even when they should not be
rendered, which hurts performance.

</details>

<details>
<summary>80. What is ticker in Flutter?</summary>

#### Flutter

Ticker in Flutter is an object that generates a callback for each animation
frame.

#### Main role:

1. **Notifies about each frame**
2. **Allows animation progression over time**
3. **Used inside `AnimationController`**

#### In simple terms:

Ticker is a "metronome" for animation.

#### Practical significance:

When you work with `AnimationController`, you almost always work with ticker
indirectly as well.

</details>

<details>
<summary>81. What is `AnimatedBuilder`?</summary>

#### Flutter

`AnimatedBuilder` is a widget that rebuilds part of UI in response to changes
in animated value.

#### Why it is needed:

1. **React to `Animation`**
2. **Update only the required UI part**
3. **Build explicit animations without extra boilerplate**

#### Example:

```dart
AnimatedBuilder(
  animation: controller,
  builder: (context, child) {
    return Transform.scale(
      scale: controller.value,
      child: child,
    );
  },
  child: const FlutterLogo(),
)
```

#### Advantage:

You can pass a `child` that will not rebuild on every frame.

</details>

<details>
<summary>82. What is `AnimatedContainer`?</summary>

#### Flutter

`AnimatedContainer` is a widget for implicit animation that automatically
animates changes of its properties.

#### What it can animate:

1. **Size**
2. **Color**
3. **Padding**
4. **Margin**
5. **Alignment**
6. **Decoration**

#### Example:

```dart
AnimatedContainer(
  duration: const Duration(milliseconds: 300),
  width: isExpanded ? 200 : 100,
  color: isExpanded ? Colors.blue : Colors.red,
)
```

#### Practical significance:

`AnimatedContainer` is one of the most convenient ways to quickly add smooth UI
without manual controller management.

</details>

<details>
<summary>83. What is the difference between implicit and explicit animations?</summary>

#### Flutter

The difference between implicit and explicit animations is the level of control.

#### Implicit animations:

Flutter controls animation automatically when widget properties change.

#### Examples:

- `AnimatedContainer`
- `AnimatedOpacity`
- `AnimatedAlign`

#### Explicit animations:

Developer controls animation manually through `AnimationController`.

#### Examples:

- `AnimatedBuilder`
- `FadeTransition`
- `ScaleTransition`

#### Core difference:

| Criterion  | Implicit animations   | Explicit animations       |
| ---------- | --------------------- | ------------------------- |
| Control    | Lower                 | Full                      |
| Complexity | Lower                 | Higher                    |
| Use case   | Simple UI transitions | Complex custom scenarios  |

#### Practical conclusion:

For simple animations, implicit widgets are a better starting point. For complex
motion scenarios and synchronization of multiple animations, explicit animations
are needed.

</details>

<details>
<summary>84. What is Flutter architecture?</summary>

#### Flutter

Flutter architecture consists of several key layers: framework, engine,
embedder, and platform.

#### Main layers:

1. **Framework** - widgets, rendering, gestures, animation, foundation
2. **Engine** - rendering, text, compositing, Skia/graphics integration
3. **Embedder** - integration with Android, iOS, desktop, or web
4. **Platform** - native OS and its APIs

#### Core idea:

Flutter does not just wrap native UI components. It builds its own UI stack from
top to bottom.

#### Practical significance:

This architecture is why Flutter provides high UI consistency across platforms,
but sometimes requires separate native code integration.

</details>

<details>
<summary>85. What is rendering pipeline in Flutter?</summary>

#### Flutter

Rendering pipeline in Flutter is the sequence of stages UI goes through from
state change to frame display on screen.

#### Simplified pipeline:

1. **State change**
2. **Build**
3. **Layout**
4. **Paint**
5. **Compositing**
6. **Rasterization**

#### What this means:

- `build` forms widget tree
- `layout` calculates sizes and positions
- `paint` draws visual output
- engine turns this into a frame

#### Practical significance:

Understanding rendering pipeline helps debug jank, unnecessary rebuilds,
repaints, and performance issues.

</details>

<details>
<summary>86. What are Widgets, Elements, and RenderObjects?</summary>

#### Flutter

These are three key levels of Flutter's UI model.

#### Widgets

Widgets are immutable UI configurations.

#### Elements

Elements are "live" links between widget tree and render tree.

#### RenderObjects

RenderObjects are responsible for layout, paint, and low-level rendering.

#### In simple terms:

1. **Widget** - what we want to show
2. **Element** - connection and lifecycle in the tree
3. **RenderObject** - how it is actually measured and painted

#### Practical significance:

This model explains why Flutter can update UI efficiently without rebuilding
everything from scratch at low level.

</details>

<details>
<summary>87. What is `FlutterEngine`?</summary>

#### Flutter

`FlutterEngine` is the low-level part of Flutter responsible for Dart code
execution and frame rendering.

#### What it is responsible for:

1. **Dart runtime**
2. **Rendering**
3. **Text layout**
4. **Compositing**
5. **Low-level platform interaction**

#### Practical significance:

Framework provides convenient widget APIs, while engine ensures everything
actually works on device screen.

</details>

<details>
<summary>88. What is `WidgetsBinding`?</summary>

#### Flutter

`WidgetsBinding` is a binding layer that connects Flutter framework with engine
and coordinates app lifecycle on widget level.

#### Why it is needed:

1. **Framework initialization**
2. **Work with frame callbacks**
3. **Access to binding lifecycle**
4. **Coordination between framework and engine**

#### Example:

```dart
WidgetsFlutterBinding.ensureInitialized();
```

#### Practical significance:

It is one of the central Flutter runtime mechanisms, even if in typical code
developer sees it only indirectly.

</details>

<details>
<summary>89. What is `WidgetsBindingObserver`?</summary>

#### Flutter

`WidgetsBindingObserver` is an interface that allows listening to app lifecycle
changes and other framework events.

#### What it is used for:

1. **Tracking `AppLifecycleState`**
2. **Reacting to `resumed`, `paused`, `inactive`, `detached`**
3. **Handling platform-level changes**

#### Example use case:

- stop video when app goes to background
- refresh data when app returns to foreground

#### Practical significance:

It is an important lifecycle tool, especially for apps with media, analytics,
socket connections, or background-sensitive logic.

</details>

<details>
<summary>90. What are platform channels?</summary>

#### Flutter

Platform channels are a mechanism of interaction between Flutter Dart code and
native platform code, such as Kotlin/Java on Android or Swift/Objective-C on
iOS.

#### Why they are needed:

1. **Access to native APIs**
2. **Work with platform SDKs**
3. **Integration with functionality not available directly in Flutter**

#### Main types:

1. **`MethodChannel`**
2. **`EventChannel`**
3. **`BasicMessageChannel`**

#### Practical significance:

Platform channels are needed when a Flutter app goes beyond pure UI and must
interact with native device capabilities or third-party SDKs.

</details>

<details>
<summary>91. What is tree shaking?</summary>

#### Flutter

Tree shaking is the process of removing unused code from the final build.

#### Core idea:

If certain code is not used, compiler or build system does not include it in
release build.

#### Why it is needed:

1. **Smaller app size**
2. **Faster loading**
3. **Less unnecessary code in production**

#### Practical significance in Flutter:

Tree shaking is especially important for release builds because it helps reduce
artifact size and improve app delivery efficiency.

</details>

<details>
<summary>92. How to optimize Flutter app performance?</summary>

#### Flutter

Performance optimization in Flutter mostly means reducing unnecessary rebuilds,
repaints, expensive computations on UI isolate, and excessive memory usage.

#### Main optimization directions:

1. **Reduce unnecessary rebuilds**
2. **Avoid heavy CPU-bound tasks in main isolate**
3. **Use lazy lists**
4. **Use `const` where possible**
5. **Optimize images and assets**
6. **Profile app in profile mode**

#### Practical tools:

- Flutter DevTools
- Performance overlay
- Timeline profiling
- Memory profiler

#### Practical conclusion:

Performance in Flutter should not be guessed, it should be measured. Good
optimization almost always starts with profiling, not random changes.

</details>

<details>
<summary>93. How to reduce number of widget rebuilds?</summary>

#### Flutter

To reduce rebuild count, localize state and rebuild only those tree parts that
actually depend on changes.

#### Main approaches:

1. **Extract UI into smaller widgets**
2. **Use `const`**
3. **Localize state as low as possible**
4. **Avoid listening to unnecessary global state**
5. **Use selector approaches (`select`, selectors, derived state)**

#### Practical thinking example:

If only badge in header changes, there is no need to rebuild the whole screen.

#### Important:

Rebuild itself is not always a problem. Problem appears when rebuild is
expensive or happens too often.

</details>

<details>
<summary>94. What is `RepaintBoundary`?</summary>

#### Flutter

`RepaintBoundary` is a widget that separates part of render tree into a separate
repaint region.

#### Why it is needed:

1. **To avoid repainting entire screen**
2. **To isolate expensive paint areas**
3. **To improve performance in complex UI**

#### Core idea:

If one part of tree changes often and another does not, `RepaintBoundary` can
help reduce unnecessary repaints.

#### Practical nuance:

It should not be added everywhere blindly. Like any optimization, it makes sense
where profiling shows a real repaint problem.

</details>

<details>
<summary>95. How to reduce Flutter app size?</summary>

#### Flutter

Flutter app size is reduced through dependency optimization, asset optimization,
and release build configuration.

#### Main approaches:

1. **Remove unnecessary packages**
2. **Optimize assets and images**
3. **Use tree shaking**
4. **Do not include large SDKs without need**
5. **Minimize number of fonts and locales**

#### Practical steps:

- build release, not debug
- analyze build composition
- check which packages add size

#### Practical conclusion:

App size often grows not because of Flutter itself, but because of excessive
assets, SDKs, and third-party dependencies.

</details>

<details>
<summary>96. What are best practices for large Flutter applications?</summary>

#### Flutter

For large Flutter apps, key best practices are tied to architecture, modularity,
testability, and state management discipline.

#### Main practices:

1. **Feature-based or layered project structure**
2. **Clear separation of UI, domain, and data layer**
3. **Transparent state management**
4. **Dependency injection**
5. **Test coverage for critical logic**
6. **Unified design system / theme system**
7. **Logging, analytics, error reporting**

#### Additionally:

- avoid god-classes
- do not mix network, UI, and business logic in one place
- standardize team approaches

#### Practical conclusion:

A large Flutter app almost always struggles without architecture discipline,
even if it started as a "simple mobile client."

</details>

<details>
<summary>97. Which testing types exist in Flutter?</summary>

#### Flutter

In Flutter, three main testing types are used most often.

#### 1. Unit tests

Test individual functions, services, use cases, and business logic.

#### 2. Widget tests

Test individual widgets and their behavior in isolated environment.

#### 3. Integration tests

Test real user flows in a near-complete application.

#### Practical significance:

A healthy test strategy usually combines all three types, not just one.

</details>

<details>
<summary>98. What is unit testing?</summary>

#### Flutter

Unit testing is testing of small isolated code units without UI and without
dependency on real application runtime.

#### What is usually tested:

1. **Functions**
2. **Services**
3. **Use cases**
4. **Parsing**
5. **Validation**

#### Advantages:

1. **Fast execution**
2. **Low-cost debugging**
3. **Good fit for business logic**

#### Practical conclusion:

If logic can be tested without Flutter UI, this is often the most stable and
most cost-effective test type.

</details>

<details>
<summary>99. What is widget testing?</summary>

#### Flutter

Widget testing is testing Flutter widgets in a controlled environment without
running full app on a real device.

#### What can be verified:

1. **What widget renders**
2. **How it reacts to user interaction**
3. **Whether UI changes after action**

#### Example scenario:

- tap a button
- verify new text appears

#### Practical significance:

Widget tests provide a strong balance between speed and value, so in Flutter
they are often considered one of the most useful test types.

</details>

<details>
<summary>100. What is integration testing?</summary>

#### Flutter

Integration testing is testing full or near-full user flows in application.

#### What is verified:

1. **Interaction of multiple screens**
2. **Navigation**
3. **Work with real services or close replacements**
4. **Complete behavior of user scenario**

#### Example:

- login
- open list
- navigate to details
- complete user action

#### Practical downside:

Integration tests are slower, more fragile, and more expensive than unit and
widget tests, so they usually cover critical scenarios.

</details>

<details>
<summary>101. How to test a separate widget in Flutter?</summary>

#### Flutter

A separate widget in Flutter is usually tested with a widget test using
`testWidgets`, `WidgetTester`, and `pumpWidget()`.

#### Example:

```dart
testWidgets('counter increments smoke test', (WidgetTester tester) async {
  await tester.pumpWidget(const MaterialApp(
    home: CounterPage(),
  ));

  expect(find.text('0'), findsOneWidget);

  await tester.tap(find.byType(FloatingActionButton));
  await tester.pump();

  expect(find.text('1'), findsOneWidget);
});
```

#### Typical process:

1. **Build widget via `pumpWidget()`**
2. **Find elements via `find`**
3. **Perform interaction**
4. **Verify expected result**

#### Practical significance:

For most UI components, this is the basic and correct way to verify behavior.

</details>

<details>
<summary>102. How to make HTTP requests in Flutter?</summary>

#### Flutter

HTTP requests in Flutter are usually made through packages like `http` or `dio`.

#### Main approaches:

1. **`http` package** - simple basic option
2. **`dio` package** - more powerful option with interceptors, retries, and config

#### Example with `http`:

```dart
final response = await http.get(
  Uri.parse('https://example.com/api/users'),
);
```

#### Practical production approach:

- separate API client
- data models
- error handling
- timeout/retry strategy
- request logging

#### Practical conclusion:

HTTP call itself is simple, but production-ready networking is already a
separate architectural area of the app.

</details>

<details>
<summary>103. Which databases can be used with Flutter?</summary>

#### Flutter

With Flutter, you can use several types of local and remote databases.

#### Local options:

1. **SQLite**
2. **Hive**
3. **Isar**
4. **SharedPreferences / key-value storage**

#### Remote options:

1. **Firebase Firestore**
2. **Supabase / PostgreSQL-backed services**
3. **Any backend with REST or GraphQL API**

#### Practical choice:

- **Hive / Isar** - fast local storage
- **SQLite** - structured local data
- **Firestore** - real-time cloud data

#### Practical conclusion:

Database choice depends not on Flutter itself, but on data model, offline-first
requirements, synchronization needs, and domain complexity.

</details>

<details>
<summary>104. What are Flutter plugins?</summary>

#### Flutter

Flutter plugins are packages that provide Flutter API for access to native
platform capabilities.

#### What they provide:

1. **Camera access**
2. **Geolocation access**
3. **Push notifications**
4. **Bluetooth, sensors, storage, permissions**

#### Core idea:

A plugin has Dart API and platform implementations for Android, iOS, and
sometimes other platforms.

#### Practical significance:

Plugins allow not writing platform channels manually every time, but using
ready integration.

</details>

<details>
<summary>105. How to integrate Flutter into an existing native app?</summary>

#### Flutter

Flutter can be integrated into an existing Android or iOS app as a separate
module.

#### Core idea:

Flutter does not have to be the "whole app." It can be embedded only into
specific screens or features.

#### How it usually works:

1. **Create Flutter module**
2. **Native app connects this module**
3. **Specific screens open via `FlutterActivity`, `FlutterFragment`, or iOS integration**

#### Practical scenarios:

- gradual migration of native app to Flutter
- launching a new Flutter feature without full rewrite

#### Practical conclusion:

Add-to-app approach is useful when business is not ready to rewrite everything
but wants to introduce Flutter into product gradually.

</details>

<details>
<summary>106. How to implement platform-specific code in Flutter?</summary>

#### Flutter

Platform-specific code in Flutter can be implemented in several ways depending
on the task level.

#### Main approaches:

1. **Platform channels** - when native code is needed
2. **Ready plugins** - when a package for required feature already exists
3. **`Platform.isAndroid` / `Platform.isIOS`** - for platform-specific logic branches
4. **`defaultTargetPlatform`** - for UI behavior

#### Example:

```dart
if (Platform.isIOS) {
  // iOS-specific logic
} else if (Platform.isAndroid) {
  // Android-specific logic
}
```

#### Practical conclusion:

If there is a proven ready plugin, it is better to use it. If not, then use a
platform channel or build your own plugin.

</details>
