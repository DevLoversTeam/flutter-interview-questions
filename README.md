**Read in other languages: [English 🇺🇸](README.en.md),
[Polska 🇵🇱](README.pl.md), [German 🇩🇪](README.de.md), [French 🇫🇷](README.fr.md),
[Spanish 🇪🇸](README.es.md), [Українська 🇺🇦](README.md).**

<h1>
  Flutter <img src="./assets/flutter.svg" width="40" height="40" />
</h1>

<h2>Найпопулярніші запитання та відповіді на співбесіді з Flutter</h2>

<details>
<summary>1. Що таке Flutter?</summary>

#### Flutter

Flutter - це open-source UI toolkit від Google для створення кросплатформених
застосунків з єдиної кодової бази.

#### Основні характеристики Flutter:

1. **Кросплатформеність:** Дозволяє створювати застосунки для iOS, Android, Web,
   Windows, macOS і Linux.

2. **Власний рушій рендерингу:** Flutter малює інтерфейс самостійно, а не
   використовує нативні OEM-віджети як основу UI.

3. **Віджетний підхід:** У Flutter майже все є віджетами: екран, текст,
   відступи, кнопки, анімації.

4. **Висока швидкість розробки:** Hot Reload дозволяє швидко бачити зміни в коді
   без повного перезапуску застосунку.

5. **Єдина мова розробки:** Увесь клієнтський код зазвичай пишеться на Dart.

Flutter часто використовують для швидкої розробки MVP, продуктових мобільних
застосунків і внутрішніх корпоративних систем.

</details>

<details>
<summary>2. Чому Flutter часто обирають для мобільної розробки?</summary>

#### Flutter

Flutter часто обирають через баланс між швидкістю розробки, якістю UI та
можливістю підтримувати одну кодову базу для кількох платформ.

#### Основні причини:

1. **Одна кодова база:** Менше дублювання логіки між Android та iOS.

2. **Швидка розробка:** Hot Reload пришвидшує ітерації команди.

3. **Передбачуваний UI:** Flutter рендерить інтерфейс сам, тому дизайн виглядає
   більш консистентно між платформами.

4. **Хороша продуктивність:** Для більшості бізнес-застосунків Flutter дає
   продуктивність, достатню для production-рівня.

5. **Сильна екосистема:** Є велика кількість пакетів для навігації, стану, HTTP,
   локального зберігання, аналітики та тестування.

6. **Зручна робота з кастомним UI:** Якщо в продукті багато нестандартних
   екранів, анімацій або складної дизайн-системи, Flutter часто виграє у
   швидкості реалізації.

#### Коли це особливо вигідно:

- Коли треба швидко вийти на iOS та Android.
- Коли команда невелика і важливо скоротити витрати на підтримку.
- Коли в продукті багато кастомного інтерфейсу.

</details>

<details>
<summary>3. Які платформи підтримує Flutter?</summary>

#### Flutter

Flutter підтримує кілька платформ з однієї кодової бази.

#### Основні платформи:

1. **Android**
2. **iOS**
3. **Web**
4. **Windows**
5. **macOS**
6. **Linux**

#### Додатково:

- Flutter також використовується для **embedded-рішень** та спеціалізованих
  пристроїв, якщо є відповідна інтеграція з рушієм.
- Найчастіше у комерційній розробці Flutter застосовують саме для **мобільних
  платформ**, але web і desktop теж підтримуються офіційно.

</details>

<details>
<summary>4. Що таке Dart і чому Flutter використовує саме цю мову?</summary>

#### Flutter

Dart - це мова програмування, розроблена Google. Flutter використовує Dart як
основну мову для написання UI, бізнес-логіки та взаємодії з фреймворком.

#### Чому Flutter використовує Dart:

1. **Швидка компіляція під час розробки:** Це робить можливим Hot Reload.

2. **AOT і JIT:** Dart підтримує JIT для швидкої розробки та AOT-компіляцію для
   ефективного production-білду.

3. **Простий синтаксис:** Dart легко сприймається розробниками з досвідом у
   Java, JavaScript, C#, Kotlin або Swift.

4. **Хороша підтримка асинхронності:** `Future`, `Stream`, `async/await`
   природно підходять для клієнтської розробки.

5. **Сильна типізація:** Це покращує підтримуваність, рефакторинг і стабільність
   великих проєктів.

#### Практична причина:

Для Flutter потрібна мова, яка добре працює і в режимі швидкої розробки, і в
режимі оптимізованої компіляції. Dart закриває обидва сценарії.

</details>

<details>
<summary>5. Яка структура проєкту Flutter?</summary>

#### Flutter

Типовий Flutter-проєкт має кілька стандартних директорій і службових файлів.

#### Базова структура:

1. **`lib/`** - основний код застосунку.
2. **`test/`** - unit- та widget-тести.
3. **`android/`** - нативна Android-частина проєкту.
4. **`ios/`** - нативна iOS-частина проєкту.
5. **`web/`** - конфігурація та точка входу для web.
6. **`macos/`, `windows/`, `linux/`** - desktop-платформи.
7. **`pubspec.yaml`** - залежності, ресурси, метадані проєкту.

#### Найважливіше на практиці:

- У більшості випадків основна продуктова логіка живе в `lib/`.
- Платформені папки змінюють тоді, коли потрібні нативні налаштування,
  permissions, SDK-конфігурація або platform channels.

#### Приклад логічної структури всередині `lib/`:

```text
lib/
  core/
  features/
  shared/
  app/
  main.dart
```

У production-проєктах зазвичай важливо не лише знати стандартну структуру
Flutter, а й мати зрозумілу feature-based або layered-архітектуру.

</details>

<details>
<summary>6. Що таке файл `pubspec.yaml` і для чого він використовується?</summary>

#### Flutter

`pubspec.yaml` - це головний конфігураційний файл Dart/Flutter-проєкту.

#### Для чого він використовується:

1. **Керування залежностями:** Пакети, які використовує застосунок.

2. **Опис ресурсів:** Підключення assets, шрифтів, іконок.

3. **Метадані проєкту:** Назва, версія, опис, environment constraints.

4. **Налаштування dev-залежностей:** Наприклад, `flutter_test`, `build_runner`,
   `flutter_lints`.

#### Приклад:

```yaml
name: flutter_interview_questions
description: Flutter interview questions and answers
version: 1.0.0+1

environment:
  sdk: '>=3.0.0 <4.0.0'

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

#### Важливо:

Після зміни `pubspec.yaml` зазвичай виконують `flutter pub get`, щоб підтягнути
нові залежності.

</details>

<details>
<summary>7. Яка роль функції `main()` у Flutter?</summary>

#### Flutter

`main()` - це точка входу в Flutter-застосунок, з якої починається виконання
програми.

#### Основна роль:

1. **Запуск застосунку:** Саме в `main()` зазвичай викликають `runApp()`.

2. **Первинна ініціалізація:** Тут можна ініціалізувати сервіси, DI-контейнер,
   Firebase, локальне сховище або конфігурацію середовища.

3. **Налаштування до старту UI:** Якщо перед запуском потрібен `await`, `main()`
   можна зробити `async`.

#### Приклад:

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}
```

#### Приклад з ініціалізацією:

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
<summary>8. Що робить функція `runApp()`?</summary>

#### Flutter

`runApp()` запускає Flutter-застосунок і монтує переданий кореневий віджет у
дерево віджетів.

#### Що відбувається на практиці:

1. **Створюється кореневий вузол UI:** Саме з нього починається все дерево
   віджетів.

2. **Flutter починає процес побудови інтерфейсу:** Далі фреймворк викликає
   `build()` і рендерить екран.

3. **Застосунок переходить під керування Flutter framework:** Всі наступні
   оновлення UI обробляються через систему віджетів, елементів і render objects.

#### Приклад:

```dart
void main() {
  runApp(const MyApp());
}
```

#### Важливо:

- Зазвичай у `runApp()` передають `MaterialApp`, `CupertinoApp` або власний
  кореневий `App`-віджет.
- Повторний виклик `runApp()` можливий, але в типовому життєвому циклі
  застосунку він зазвичай викликається один раз.

</details>

<details>
<summary>9. Що таке віджети (widgets) у Flutter?</summary>

#### Flutter

Віджети - це базові будівельні блоки UI у Flutter. Вони описують, як має
виглядати частина інтерфейсу і як вона повинна поводитися.

#### Приклади того, що є віджетами:

1. **Текст:** `Text`
2. **Кнопка:** `ElevatedButton`
3. **Відступ:** `Padding`
4. **Розмітка:** `Column`, `Row`, `Stack`
5. **Екран:** `Scaffold`

#### Особливості віджетів:

1. **Декларативність:** Ви описуєте UI як набір віджетів.

2. **Композиція:** Складний інтерфейс збирається з простих віджетів.

3. **Імм'ютабельність:** Віджети самі по собі незмінні; зміни UI досягаються
   через перебудову дерева.

#### Приклад:

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
<summary>10. У чому різниця між `StatelessWidget` і `StatefulWidget`?</summary>

#### Flutter

Різниця полягає в тому, чи має віджет внутрішній змінний стан, який впливає на
його відображення.

#### `StatelessWidget`:

Використовується для UI, який залежить лише від вхідних параметрів і не має
власного змінного стану.

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

Використовується тоді, коли віджет має стан, який може змінюватися протягом
життєвого циклу.

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

#### Основні відмінності:

1. **Стан:** `StatelessWidget` не має mutable state, `StatefulWidget` має.

2. **Оновлення UI:** У `StatefulWidget` UI оновлюється через `setState()` або
   інші state management підходи.

3. **Сценарії використання:** Статичні елементи UI проти інтерактивних або
   динамічних частин екрана.

</details>

<details>
<summary>11. Що таке дерево віджетів (widget tree)?</summary>

#### Flutter

Дерево віджетів - це ієрархія всіх віджетів, з яких складається інтерфейс
Flutter-застосунку.

#### Як це працює:

1. **Кожен віджет може містити дочірні віджети.**

2. **Весь екран формується як дерево вкладених елементів.**

3. **Під час змін стану Flutter перебудовує частини цього дерева.**

#### Приклад:

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

У цьому прикладі `MaterialApp` є коренем, всередині нього знаходиться
`Scaffold`, далі `AppBar`, `Center` і `Text`.

#### Чому це важливо:

- Розуміння widget tree допомагає правильно будувати UI.
- Це критично для дебагу, оптимізації rebuild-ів і роботи з контекстом.

</details>

<details>
<summary>12. Що таке `BuildContext`?</summary>

#### Flutter

`BuildContext` - це посилання на місце віджета в дереві віджетів.

#### Для чого він потрібен:

1. **Доступ до батьківських залежностей:** Наприклад, `Theme`, `MediaQuery`,
   `Navigator`, `ScaffoldMessenger`, `Provider`.

2. **Навігація:** Через `Navigator.of(context)`.

3. **Отримання локальних налаштувань середовища:** Розмір екрана, тема, локаль
   та інші inherited dependencies.

#### Приклад:

```dart
final theme = Theme.of(context);
final size = MediaQuery.of(context).size;
```

#### Важливий нюанс:

`BuildContext` повинен належати правильному місцю в дереві. Наприклад, якщо
викликати `ScaffoldMessenger.of(context)` занадто рано або з контексту, який не
має потрібного предка, отримаєте помилку.

#### Практичне правило:

Контекст треба сприймати не як "глобальний доступ", а як "позицію віджета в
дереві на цей момент".

</details>

<details>
<summary>13. Що таке `Key` у Flutter і для чого він потрібен?</summary>

#### Flutter

`Key` - це механізм ідентифікації віджетів у дереві, який допомагає Flutter
правильно зіставляти старі та нові віджети під час rebuild.

#### Для чого потрібні `Key`:

1. **Збереження стану при зміні порядку елементів.**

2. **Коректна робота списків і динамічних колекцій.**

3. **Доступ до віджетів у тестах.**

4. **Керування унікальністю елементів у дереві.**

#### Приклад:

```dart
ListView(
  children: const [
    ListTile(key: ValueKey('user_1'), title: Text('User 1')),
    ListTile(key: ValueKey('user_2'), title: Text('User 2')),
  ],
)
```

#### Основні типи:

1. **`ValueKey`** - коли є стабільне значення-ідентифікатор.
2. **`ObjectKey`** - коли ключ базується на об'єкті.
3. **`UniqueKey`** - коли потрібна гарантована унікальність.
4. **`GlobalKey`** - для доступу до state або context конкретного віджета.

#### Важливо:

`GlobalKey` треба використовувати обережно. Це потужний, але відносно дорогий
інструмент, який не варто застосовувати без реальної потреби.

</details>

<details>
<summary>14. Що таке Hot Reload і Hot Restart?</summary>

#### Flutter

Hot Reload і Hot Restart - це два механізми швидкого перезапуску застосунку під
час розробки.

#### Hot Reload:

- Впроваджує зміни в коді майже миттєво.
- Зберігає поточний стан застосунку.
- Найкраще підходить для змін у UI, стилях, логіці `build()`.

#### Hot Restart:

- Перезапускає Dart isolate.
- Скидає поточний стан застосунку.
- Повторно виконує `main()`.
- Потрібен, коли Hot Reload вже недостатній.

#### Різниця:

| Критерій         | Hot Reload                 | Hot Restart                               |
| ---------------- | -------------------------- | ----------------------------------------- |
| Швидкість        | Швидше                     | Повільніше                                |
| Збереження стану | Так                        | Ні                                        |
| Виклик `main()`  | Ні                         | Так                                       |
| Типові сценарії  | Зміни UI та дрібної логіки | Зміни ініціалізації або глобального стану |

#### Важливо:

Не всі зміни можна коректно застосувати через Hot Reload. Наприклад, зміни в
initialization flow або деяких static-конструкціях можуть вимагати Hot Restart.

</details>

<details>
<summary>15. Які режими збірки існують у Flutter (Debug, Profile, Release)?</summary>

#### Flutter

У Flutter є три основні режими збірки, кожен з яких має своє призначення.

#### 1. Debug

- Використовується під час розробки.
- Підтримує Hot Reload.
- Має додаткові перевірки, assertions і dev tooling.
- Не підходить для оцінки реальної продуктивності.

#### 2. Profile

- Використовується для аналізу продуктивності.
- Ближчий до production-поведінки.
- Дає змогу використовувати профілювання CPU, GPU, memory та frame rendering.

#### 3. Release

- Використовується для production.
- Максимально оптимізований.
- Без debug-інструментів, assertions і dev overhead.

#### Коли який режим використовувати:

1. **Debug** - щоденна розробка.
2. **Profile** - performance tuning.
3. **Release** - реліз у store або production distribution.

</details>

<details>
<summary>16. Що таке `MaterialApp`?</summary>

#### Flutter

`MaterialApp` - це кореневий віджет для застосунків, які використовують Material
Design.

#### Що він надає:

1. **Навігацію**
2. **Тему застосунку**
3. **Локалізацію**
4. **Маршрути**
5. **Базову Material-конфігурацію**

#### Приклад:

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

#### Коли використовується:

У більшості Flutter-застосунків `MaterialApp` є точкою входу у верхньому рівні
дерева віджетів.

</details>

<details>
<summary>17. Що таке віджет `Scaffold`?</summary>

#### Flutter

`Scaffold` - це базовий layout-віджет для Material Design екранів.

#### Що він зазвичай містить:

1. **`appBar`** - верхня панель.
2. **`body`** - основний контент екрана.
3. **`floatingActionButton`** - плаваюча action-кнопка.
4. **`drawer`** - бокове меню.
5. **`bottomNavigationBar`** - нижня навігація.
6. **`snackBar` / `bottomSheet` integration** - взаємодія з Material shell.

#### Приклад:

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

#### Практична роль:

`Scaffold` дає стандартний "каркас" екрана. Без нього багато Material-поведінок
доведеться організовувати вручну.

</details>

<details>
<summary>18. Для чого використовується `SafeArea`?</summary>

#### Flutter

`SafeArea` використовується для того, щоб контент не потрапляв під системні
елементи інтерфейсу.

#### Від чого він захищає:

1. **Статус-бар**
2. **Notch / Dynamic Island / вирізи екрана**
3. **Системні жести і нижні safe insets**
4. **Інші системні області, які не варто перекривати контентом**

#### Приклад:

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

#### Коли особливо корисний:

- На екранах із кастомним layout.
- Коли контент прилягає до країв екрана.
- Коли треба швидко забезпечити базову безпеку розміщення UI.

#### Важливо:

`SafeArea` не замінює продуманий layout, але допомагає уникнути типових проблем
з перекриттям системними зонами.

</details>

<details>
<summary>19. Що таке мова програмування Dart?</summary>

#### Flutter

Dart - це сучасна об'єктно-орієнтована мова програмування, розроблена Google,
яка використовується як основна мова для Flutter-розробки.

#### Основні характеристики Dart:

1. **Сильна типізація:** Dart підтримує статичну типізацію, що покращує
   передбачуваність і безпеку коду.

2. **JIT і AOT-компіляція:** Це дозволяє поєднати швидку розробку та
   продуктивний production build.

3. **Підтримка асинхронності:** `Future`, `Stream`, `async/await` є вбудованими
   частинами мови.

4. **Зручний синтаксис:** Dart відносно легко вивчати розробникам із досвідом у
   Java, Kotlin, Swift, C# або JavaScript.

5. **Sound null safety:** Мова допомагає зменшити кількість null-related помилок
   ще на етапі компіляції.

#### Чому Dart важливий у Flutter:

Dart не просто "мова поруч із Flutter", а фундаментальна частина екосистеми.
Весь UI, бізнес-логіка, стан, асинхронність і тести у Flutter зазвичай пишуться
саме на Dart.

</details>

<details>
<summary>20. Чим відрізняються позиційні та іменовані параметри у Dart?</summary>

#### Flutter

У Dart параметри функцій можуть бути **позиційними** або **іменованими**.

#### Позиційні параметри:

Передаються за порядком.

```dart
void printUser(String name, int age) {
  print('$name is $age years old');
}

printUser('Anna', 25);
```

#### Іменовані параметри:

Передаються за назвою, тому виклик стає більш читабельним.

```dart
void printUser({required String name, required int age}) {
  print('$name is $age years old');
}

printUser(name: 'Anna', age: 25);
```

#### Основні відмінності:

1. **Читабельність:** Іменовані параметри краще підходять для API з великою
   кількістю аргументів.

2. **Порядок передачі:** Для позиційних важливий порядок, для іменованих - ні.

3. **Гнучкість:** Іменовані параметри часто краще масштабуються, коли параметрів
   стає більше.

#### Практика у Flutter:

У Flutter більшість конструкторів віджетів активно використовують саме
**іменовані параметри**, бо це суттєво покращує читабельність UI-коду.

</details>

<details>
<summary>21. У чому різниця між `var`, `final` і `const`?</summary>

#### Flutter

`var`, `final` і `const` у Dart використовуються для оголошення змінних, але
мають різну семантику.

#### `var`

Тип виводиться автоматично, а значення можна змінювати.

```dart
var name = 'Flutter';
name = 'Dart';
```

#### `final`

Змінна може бути присвоєна лише один раз, але її значення може бути відоме лише
під час виконання.

```dart
final currentTime = DateTime.now();
```

#### `const`

Значення має бути відомим на етапі компіляції.

```dart
const pi = 3.14159;
const appName = 'Flutter App';
```

#### Ключова різниця:

1. **`var`** - звичайна змінна.
2. **`final`** - одноразове присвоєння під час runtime.
3. **`const`** - compile-time константа.

#### Практичний нюанс:

У Flutter бажано використовувати `const` там, де це можливо, особливо для
віджетів, тому що це може зменшити кількість зайвих об'єктів і rebuild overhead.

</details>

<details>
<summary>22. Що таке null-aware оператори?</summary>

#### Flutter

Null-aware оператори в Dart - це спеціальні оператори для безпечної роботи з
`null`.

#### Основні null-aware оператори:

1. **`?.`** - виклик методу або доступ до властивості лише якщо об'єкт не
   `null`.
2. **`??`** - повертає значення справа, якщо зліва `null`.
3. **`??=`** - присвоює значення лише якщо змінна `null`.
4. **`!`** - примусово каже компілятору, що значення не `null`.

#### Приклади:

```dart
String? name;
print(name?.length);

String result = name ?? 'Guest';

name ??= 'Anonymous';
```

#### Оператор `!`:

```dart
String? title;
print(title!.length);
```

Цей оператор треба використовувати обережно, тому що якщо значення буде `null`,
відбудеться runtime error.

#### Практична користь:

Null-aware оператори роблять код коротшим, безпечнішим і прибирають потребу в
надмірних ручних перевірках на `null`.

</details>

<details>
<summary>23. Що таке sound null safety у Dart?</summary>

#### Flutter

Sound null safety - це механізм у Dart, який дозволяє відокремлювати nullable та
non-nullable типи і виявляти частину null-related помилок ще під час компіляції.

#### Основна ідея:

Якщо тип оголошений як не-nullable, то він не може містити `null`.

```dart
String name = 'Flutter';
String? nullableName;
```

#### Що це дає:

1. **Менше runtime-помилок**
2. **Ясніший контракт типів**
3. **Кращий рефакторинг**
4. **Більш надійний production-код**

#### Як це читається:

- `String` - значення обов'язково не `null`
- `String?` - значення може бути `null`

#### Практичне значення:

Для великих Flutter-проєктів sound null safety суттєво зменшує кількість багів,
пов'язаних із неочікуваними `null` значеннями в UI, API-моделях та state
management.

</details>

<details>
<summary>24. Що таке `async` і `await`?</summary>

#### Flutter

`async` і `await` у Dart використовуються для зручної роботи з асинхронним
кодом.

#### `async`

Позначає, що функція виконує асинхронну роботу і зазвичай повертає `Future`.

#### `await`

Дозволяє дочекатися результату асинхронної операції без вкладених callback-ів.

#### Приклад:

```dart
Future<void> loadUser() async {
  final user = await fetchUser();
  print(user);
}
```

#### Переваги:

1. **Код читається як синхронний**
2. **Менше вкладеності**
3. **Простіша обробка помилок через `try/catch`**

#### Приклад з обробкою помилок:

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
<summary>25. Що таке `Future`?</summary>

#### Flutter

`Future` у Dart - це об'єкт, який представляє результат асинхронної операції, що
буде доступний пізніше.

#### Простими словами:

`Future` - це "обіцянка" отримати одне значення або помилку в майбутньому.

#### Приклад:

```dart
Future<String> fetchUserName() async {
  await Future.delayed(const Duration(seconds: 1));
  return 'Viktor';
}
```

#### Що може завершити `Future`:

1. **Успішний результат**
2. **Помилка**

#### Робота з `Future`:

```dart
final name = await fetchUserName();
```

або

```dart
fetchUserName()
    .then((value) => print(value))
    .catchError((error) => print(error));
```

#### Де використовується у Flutter:

- HTTP-запити
- Читання файлів
- Робота з локальною базою
- Ініціалізація сервісів
- Навігація, діалоги, permission flows

</details>

<details>
<summary>26. Що таке `Stream`?</summary>

#### Flutter

`Stream` - це послідовність асинхронних подій або значень, які приходять з
часом.

#### Основна ідея:

Якщо `Future` дає одне значення в майбутньому, то `Stream` може давати багато
значень протягом часу.

#### Приклад:

```dart
Stream<int> counterStream() async* {
  for (int i = 1; i <= 3; i++) {
    await Future.delayed(const Duration(seconds: 1));
    yield i;
  }
}
```

#### Отримання значень:

```dart
await for (final value in counterStream()) {
  print(value);
}
```

#### Де використовуються `Stream`:

1. **WebSocket**
2. **Поширення стану**
3. **Підписка на зміни в базі даних**
4. **Події UI або системні події**

#### У Flutter:

`Stream` часто використовують у BLoC, реактивних потоках даних та в ситуаціях,
де важливі не одноразові, а постійні оновлення.

</details>

<details>
<summary>27. У чому різниця між `Future` і `Stream`?</summary>

#### Flutter

`Future` і `Stream` обидва використовуються для асинхронності, але вирішують
різні задачі.

#### Основна різниця:

| Критерій          | `Future`                       | `Stream`                                   |
| ----------------- | ------------------------------ | ------------------------------------------ |
| Кількість значень | Одне значення або помилка      | Багато значень з часом                     |
| Завершення        | Один раз                       | Може тривати довго або завершитися пізніше |
| Типовий сценарій  | HTTP-запит, одноразове читання | WebSocket, підписка, live updates          |

#### Приклади:

- `Future`: завантажити профіль користувача один раз.
- `Stream`: слухати оновлення чату в реальному часі.

#### Практичне правило:

Якщо відповідь потрібна один раз - зазвичай це `Future`. Якщо потрібен потік
оновлень - зазвичай це `Stream`.

</details>

<details>
<summary>28. Що таке event loop у Dart?</summary>

#### Flutter

Event loop у Dart - це механізм, який керує виконанням асинхронних задач у
одному isolate.

#### Як це працює:

1. **Синхронний код виконується одразу**
2. **Асинхронні задачі ставляться в черги**
3. **Event loop по черзі бере задачі та виконує їх**

#### Основні черги:

1. **Microtask queue** - має вищий пріоритет.
2. **Event queue** - звичайні асинхронні події.

#### Приклад:

```dart
void main() {
  print('1');

  Future(() => print('2'));
  scheduleMicrotask(() => print('3'));

  print('4');
}
```

Результат буде:

```text
1
4
3
2
```

#### Чому це важливо:

Розуміння event loop допомагає правильно працювати з `Future`, `Stream`,
мікротасками, UI responsiveness і уникати неочікуваного порядку виконання коду.

</details>

<details>
<summary>29. Що таке mixins у Dart?</summary>

#### Flutter

Mixins у Dart - це механізм повторного використання коду між класами без
класичного множинного наслідування.

#### Для чого вони використовуються:

1. **Повторне використання поведінки**
2. **Додавання спільної логіки кільком класам**
3. **Композиція можливостей без жорсткої ієрархії**

#### Приклад:

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

#### У Flutter mixins часто зустрічаються:

- `SingleTickerProviderStateMixin`
- `TickerProviderStateMixin`
- `AutomaticKeepAliveClientMixin`

#### Практичний сенс:

Mixins корисні, коли треба поділитися поведінкою між кількома класами, але ця
поведінка не повинна бути окремим базовим класом.

</details>

<details>
<summary>30. Що таке extension methods?</summary>

#### Flutter

Extension methods у Dart дозволяють додавати нові методи або геттери до існуючих
типів без зміни їхнього вихідного коду.

#### Приклад:

```dart
extension StringX on String {
  bool get isEmail => contains('@');
}
```

Тепер можна писати:

```dart
final result = 'test@example.com'.isEmail;
```

#### Для чого це корисно:

1. **Покращення читабельності**
2. **Винесення utility-логіки ближче до типу**
3. **Прибирання зайвих helper-класів**

#### Типові приклади у Flutter:

- Extensions для `BuildContext`
- Extensions для `String`, `DateTime`, `num`
- Extensions для теми, відступів, локалізації

#### Важливо:

Extension methods покращують API коду, але ними не варто зловживати. Якщо
extension починає ховати складну бізнес-логіку, це зазвичай погіршує
передбачуваність коду.

</details>

<details>
<summary>31. Що таке `typedef` у Dart?</summary>

#### Flutter

`typedef` у Dart використовується для створення псевдонімів типів, найчастіше
для функцій.

#### Приклад:

```dart
typedef OnUserTap = void Function(String userId);
```

Тепер цей тип можна використовувати так:

```dart
class UserTile {
  final OnUserTap onTap;

  UserTile({required this.onTap});
}
```

#### Для чого це потрібно:

1. **Покращує читабельність API**
2. **Додає семантичний зміст функціональним типам**
3. **Спрощує повторне використання однакових сигнатур**

#### Де це корисно у Flutter:

- Callbacks у віджетах
- DI і service contracts
- State management APIs
- Stream/listener contracts

</details>

<details>
<summary>32. Що таке factory constructor?</summary>

#### Flutter

Factory constructor у Dart - це конструктор, який не обов'язково створює новий
екземпляр класу щоразу при виклику.

#### Основні можливості:

1. **Може повертати кешований об'єкт**
2. **Може повертати екземпляр підкласу**
3. **Може містити додаткову логіку перед створенням об'єкта**

#### Приклад:

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

#### Що тут відбувається:

Замість створення нового `Logger` щоразу factory constructor повертає вже
існуючий екземпляр для того самого `name`.

#### Де часто використовується:

- Singleton-подібні сценарії
- Парсинг моделей
- Абстракції, де потрібен контроль над створенням екземпляра

#### Важливо:

Factory constructor відрізняється від звичайного тим, що не має прямого доступу
до `this`, бо об'єкт може ще не бути створений.

</details>

<details>
<summary>33. Як працює система layout у Flutter?</summary>

#### Flutter

Система layout у Flutter працює за принципом **constraints go down, sizes go up,
parent sets position**.

#### Як це виглядає на практиці:

1. **Батьківський віджет передає constraints вниз**
2. **Дочірній віджет обирає свій розмір у межах цих constraints**
3. **Батьківський віджет визначає позицію дочірнього елемента**

#### Основна ідея:

Flutter не використовує XML-layout систему на кшталт Android View hierarchy.
Замість цього кожен віджет бере участь у чіткій моделі обчислення розміру та
позиції.

#### Чому це важливо:

- Допомагає розуміти помилки типу overflow.
- Дає можливість передбачати поведінку `Row`, `Column`, `Expanded`, `Flexible`.
- Критично для побудови адаптивних інтерфейсів.

#### Практичне правило:

Якщо layout "ламається", майже завжди треба дивитися на constraints, які отримує
віджет від свого parent.

</details>

<details>
<summary>34. Які основні віджети використовуються для побудови макетів?</summary>

#### Flutter

У Flutter для побудови макетів найчастіше використовуються базові layout
віджети, з яких складається майже весь інтерфейс.

#### Основні layout-віджети:

1. **`Row`** - горизонтальне розміщення елементів
2. **`Column`** - вертикальне розміщення елементів
3. **`Container`** - універсальний обгортковий віджет
4. **`SizedBox`** - фіксований розмір або відступ
5. **`Expanded`** - зайняття доступного простору
6. **`Flexible`** - гнучке використання простору
7. **`Stack`** - накладання елементів один на один
8. **`Padding`** - внутрішні відступи
9. **`Align` / `Center`** - вирівнювання
10. **`ListView`** - прокручувані списки
11. **`Wrap`** - перенесення елементів на новий рядок
12. **`Scaffold`** - базова структура екрана

#### Практичний сенс:

У більшості екранів Flutter-розмітка будується не одним "великим layout", а
комбінацією простих віджетів.

</details>

<details>
<summary>35. У чому різниця між `Row` і `Column`?</summary>

#### Flutter

`Row` і `Column` - це базові flex-віджети у Flutter, але вони працюють у різних
напрямках.

#### `Row`

Розміщує дочірні елементи **горизонтально**.

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

Розміщує дочірні елементи **вертикально**.

```dart
Column(
  children: const [
    Text('A'),
    Text('B'),
    Text('C'),
  ],
)
```

#### Основна різниця:

1. **`Row`** працює по горизонтальній осі
2. **`Column`** працює по вертикальній осі

#### Важливо:

І `Row`, і `Column` можуть викликати overflow, якщо їхні дочірні елементи не
вміщаються в доступний простір.

</details>

<details>
<summary>36. Що таке `mainAxisAlignment` і `crossAxisAlignment`?</summary>

#### Flutter

`mainAxisAlignment` і `crossAxisAlignment` - це параметри вирівнювання у flex-
віджетах, таких як `Row` і `Column`.

#### Основна логіка:

1. **`mainAxisAlignment`** керує вирівнюванням уздовж головної осі
2. **`crossAxisAlignment`** керує вирівнюванням уздовж поперечної осі

#### Для `Row`:

- Main axis = горизонтальна
- Cross axis = вертикальна

#### Для `Column`:

- Main axis = вертикальна
- Cross axis = горизонтальна

#### Приклад:

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

#### Поширені значення:

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
<summary>37. Що таке віджет `Container`?</summary>

#### Flutter

`Container` - це універсальний віджет-обгортка, який дозволяє задавати розмір,
відступи, вирівнювання, декорацію та інші layout-властивості.

#### Що він може робити:

1. **Задавати `width` і `height`**
2. **Додавати `padding` і `margin`**
3. **Застосовувати `decoration`**
4. **Вирівнювати дочірній елемент**
5. **Фарбувати фон**

#### Приклад:

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

#### Важливо:

`Container` зручний, але не завжди оптимальний як "віджет на всі випадки". Якщо
потрібна лише одна проста функція, часто краще використати спеціалізований
віджет, наприклад `Padding`, `ColoredBox`, `SizedBox` або `Align`.

</details>

<details>
<summary>38. Що таке віджет `SizedBox`?</summary>

#### Flutter

`SizedBox` - це віджет, який задає фіксований розмір для дочірнього елемента або
використовується як простий spacer.

#### Основні сценарії:

1. **Фіксована ширина або висота**
2. **Порожній відступ між елементами**
3. **Обмеження розміру дочірнього віджета**

#### Приклад:

```dart
const SizedBox(height: 16)
```

або

```dart
SizedBox(
  width: 200,
  child: ElevatedButton(
    onPressed: () {},
    child: const Text('Submit'),
  ),
)
```

#### Практична порада:

Для простих відступів між елементами `SizedBox` зазвичай читабельніший і легший,
ніж `Container`.

</details>

<details>
<summary>39. Що таке віджет `Expanded`?</summary>

#### Flutter

`Expanded` - це віджет, який змушує дочірній елемент зайняти весь доступний
вільний простір усередині `Row`, `Column` або `Flex`.

#### Як він працює:

`Expanded` каже Flutter: "дай цьому елементу стільки вільного місця, скільки
можливо".

#### Приклад:

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

#### Додатково:

Можна використовувати `flex`, щоб керувати пропорціями.

```dart
Expanded(
  flex: 2,
  child: Container(color: Colors.red),
)
```

#### Важливо:

`Expanded` працює тільки всередині `Flex`-based віджетів: `Row`, `Column`,
`Flex`.

</details>

<details>
<summary>40. Що таке віджет `Flexible`?</summary>

#### Flutter

`Flexible` - це віджет для гнучкого розподілу простору всередині `Row`, `Column`
або `Flex`.

#### Різниця з `Expanded`:

- `Expanded` змушує елемент зайняти весь доступний простір.
- `Flexible` дозволяє елементу займати простір більш гнучко.

#### Приклад:

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

#### Практичний сенс:

`Flexible` корисний, коли елемент має адаптуватися до простору, але не
обов'язково розтягуватися максимально.

</details>

<details>
<summary>41. Що таке віджет `Spacer`?</summary>

#### Flutter

`Spacer` - це спеціальний flex-віджет, який займає вільний простір між іншими
елементами.

#### Приклад:

```dart
Row(
  children: const [
    Text('Left'),
    Spacer(),
    Text('Right'),
  ],
)
```

#### Для чого використовується:

1. **Розштовхування елементів**
2. **Побудова адаптивного простору в `Row` або `Column`**
3. **Поліпшення читабельності коду замість ручних обчислень відступів**

#### Важливо:

`Spacer` фактично працює як `Expanded` з порожнім дочірнім елементом.

</details>

<details>
<summary>42. Що таке віджет `Stack`?</summary>

#### Flutter

`Stack` - це layout-віджет, який дозволяє розміщувати елементи один поверх
одного.

#### Коли він використовується:

1. **Overlay-інтерфейси**
2. **Бейджі поверх картинок**
3. **Кнопки поверх контенту**
4. **Складні композиції UI**

#### Приклад:

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

#### Важливо:

У `Stack` порядок дочірніх елементів має значення: пізніші елементи малюються
поверх попередніх.

</details>

<details>
<summary>43. Що таке `Positioned`?</summary>

#### Flutter

`Positioned` - це віджет, який використовується всередині `Stack` для точного
позиціонування дочірнього елемента.

#### Що можна задавати:

1. **`top`**
2. **`bottom`**
3. **`left`**
4. **`right`**
5. **`width`**
6. **`height`**

#### Приклад:

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

#### Важливо:

`Positioned` працює тільки як direct child всередині `Stack`.

</details>

<details>
<summary>44. Що таке `LayoutBuilder`?</summary>

#### Flutter

`LayoutBuilder` - це віджет, який дозволяє будувати UI на основі constraints,
отриманих від батьківського віджета.

#### Коли він корисний:

1. **Адаптивний layout**
2. **Різна поведінка для вузьких і широких екранів**
3. **Рішення, де потрібно знати доступний простір під час build**

#### Приклад:

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

#### Практичний сенс:

`LayoutBuilder` особливо корисний тоді, коли рішення треба приймати не за
розміром всього екрана, а за реальним простором, доступним конкретному віджету.

</details>

<details>
<summary>45. Що таке `MediaQuery`?</summary>

#### Flutter

`MediaQuery` - це механізм доступу до інформації про поточне середовище
відображення: розмір екрана, орієнтація, padding, text scale factor та інші
метрики.

#### Що можна отримати через `MediaQuery`:

1. **Розмір екрана**
2. **Орієнтацію**
3. **Safe area insets**
4. **Налаштування масштабу тексту**

#### Приклад:

```dart
final size = MediaQuery.of(context).size;
final width = size.width;
```

#### Важливо:

`MediaQuery` добре підходить для screen-level адаптації, але якщо йдеться про
локальні constraints конкретного віджета, часто правильніше використовувати
`LayoutBuilder`.

</details>

<details>
<summary>46. Що таке `SingleChildScrollView`?</summary>

#### Flutter

`SingleChildScrollView` - це scroll-віджет для одного дочірнього елемента, який
дозволяє прокручувати контент, якщо він не вміщується на екрані.

#### Коли використовується:

1. **Форми**
2. **Невеликі екрани з вертикальним контентом**
3. **Контент, який зазвичай поміщається, але іноді може overflow-итися**

#### Приклад:

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

#### Важливо:

Для великих списків `SingleChildScrollView` не підходить так добре, як
`ListView`, бо він рендерить весь дочірній контент одразу.

</details>

<details>
<summary>47. Що таке `ListView.builder`?</summary>

#### Flutter

`ListView.builder` - це ефективний спосіб створення великих або динамічних
списків у Flutter.

#### Чому він важливий:

На відміну від статичного `ListView(children: [...])`, `ListView.builder`
створює елементи ліниво, у міру потреби.

#### Приклад:

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

#### Переваги:

1. **Краща продуктивність на великих списках**
2. **Менше споживання пам'яті**
3. **Зручна робота з динамічними даними**

</details>

<details>
<summary>48. Що таке `AspectRatio`?</summary>

#### Flutter

`AspectRatio` - це віджет, який зберігає задане співвідношення ширини до висоти.

#### Приклад:

```dart
AspectRatio(
  aspectRatio: 16 / 9,
  child: Container(
    color: Colors.blue,
  ),
)
```

#### Коли використовується:

1. **Зображення**
2. **Відеоплеєри**
3. **Картки з фіксованими пропорціями**
4. **Адаптивні UI-блоки**

#### Практичний сенс:

`AspectRatio` спрощує побудову елементів, які мають виглядати пропорційно на
різних екранах.

</details>

<details>
<summary>49. Що таке `Visibility`?</summary>

#### Flutter

`Visibility` - це віджет, який дозволяє керувати відображенням дочірнього
елемента.

#### Основний сценарій:

Показати або приховати елемент залежно від умови.

#### Приклад:

```dart
Visibility(
  visible: isLoading,
  child: const CircularProgressIndicator(),
)
```

#### Що важливо знати:

`Visibility` має додаткові параметри, які дозволяють контролювати, чи зберігати
розмір, state, animation та semantic-інформацію прихованого елемента.

#### Практичний нюанс:

Якщо потрібне просте умовне рендерення, іноді читабельніше використовувати
звичайний `if` або ternary-вираз. `Visibility` корисний тоді, коли треба тонше
керувати поведінкою прихованого віджета.

</details>

<details>
<summary>50. Що таке state у Flutter?</summary>

#### Flutter

State у Flutter - це дані, від яких залежить те, як виглядає або поводиться UI в
конкретний момент часу.

#### Простими словами:

Якщо значення змінюється і через це має оновитися інтерфейс, це і є state.

#### Приклади state:

1. **Значення лічильника**
2. **Текст у полі вводу**
3. **Стан завантаження**
4. **Обраний таб**
5. **Список отриманих з API даних**

#### Чому це важливо:

Flutter є декларативним фреймворком. Це означає, що UI описується як функція від
поточного state.

#### Практичний сенс:

Робота з Flutter значною мірою зводиться до правильної відповіді на питання: "де
має жити цей state, хто ним володіє і хто повинен на нього реагувати?"

</details>

<details>
<summary>51. У чому різниця між локальним станом (ephemeral state) і станом застосунку (app state)?</summary>

#### Flutter

Різниця між ephemeral state і app state полягає в області відповідальності та
тривалості життя цих даних.

#### Ephemeral state:

Це локальний стан конкретного віджета або невеликої частини UI.

#### Приклади:

1. **Поточне значення checkbox**
2. **Стан відкриття/закриття секції**
3. **Поточний індекс у `PageView`**

#### App state:

Це стан, який важливий для значної частини застосунку або має жити довше, ніж
один окремий віджет.

#### Приклади:

1. **Авторизація користувача**
2. **Тема застосунку**
3. **Кошик в e-commerce**
4. **Профіль користувача**

#### Основна різниця:

| Критерій   | Ephemeral state               | App state                          |
| ---------- | ----------------------------- | ---------------------------------- |
| Область    | Один віджет або малий UI-блок | Кілька екранів або весь застосунок |
| Тривалість | Коротка                       | Довша                              |
| Приклади   | Animation, selection, input   | Auth, cart, settings, user data    |

#### Практичне правило:

Не варто піднімати локальний стан до глобального рівня без причини. Це лише
ускладнює архітектуру.

</details>

<details>
<summary>52. Як працює `setState()`?</summary>

#### Flutter

`setState()` - це метод у `StatefulWidget`, який повідомляє Flutter, що стан
змінився і відповідну частину UI потрібно перебудувати.

#### Як це працює:

1. **Ви змінюєте локальний state**
2. **Обгортаєте цю зміну в `setState()`**
3. **Flutter помічає віджет як dirty**
4. **Фреймворк викликає `build()` повторно**

#### Приклад:

```dart
setState(() {
  counter++;
});
```

#### Важливо розуміти:

`setState()` не "малює UI сам". Він лише тригерить rebuild для цього `State`
об'єкта.

#### Коли підходить:

- Простий локальний стан
- Невеликі інтерактивні елементи
- Швидкі прототипи

#### Коли не підходить:

Якщо стан використовується в багатьох екранах або має складний життєвий цикл,
краще застосувати окремий state management підхід.

</details>

<details>
<summary>53. Які підходи до керування станом використовують у Flutter?</summary>

#### Flutter

У Flutter існує кілька популярних підходів до state management. Вибір залежить
від масштабу проєкту, складності домену та вимог до підтримуваності.

#### Основні підходи:

1. **`setState()`** - для простого локального стану
2. **`InheritedWidget`** - базовий механізм поширення залежностей у дереві
3. **`Provider`** - простий і популярний wrapper над `InheritedWidget`
4. **BLoC / Cubit** - поділ UI і бізнес-логіки через потоки або state classes
5. **Riverpod** - сучасніший підхід із кращою testability і dependency graph
6. **Redux** - централізований state store
7. **`ValueNotifier` / `ChangeNotifier`** - lightweight реактивні моделі

#### Практичний підхід:

- Для малого екрана достатньо `setState()`
- Для середніх застосунків часто підходить `Provider` або Riverpod
- Для складної бізнес-логіки часто вибирають BLoC або Riverpod

#### Головна ідея:

Не існує "єдиного правильного" state management. Правильний вибір той, який
робить код зрозумілим, прогнозованим і підтримуваним.

</details>

<details>
<summary>54. Що таке `Provider`?</summary>

#### Flutter

`Provider` - це популярна бібліотека для dependency injection і state management
у Flutter, побудована поверх `InheritedWidget`.

#### Що вона дає:

1. **Доступ до об'єктів вище по дереву**
2. **Оновлення UI при зміні state**
3. **Простіший API, ніж у чистого `InheritedWidget`**

#### Приклад:

```dart
ChangeNotifierProvider(
  create: (_) => CounterNotifier(),
  child: const MyApp(),
)
```

Потім у віджеті:

```dart
final counter = context.watch<CounterNotifier>();
```

#### Чому `Provider` став популярним:

- Невисокий поріг входу
- Добре підходить для невеликих і середніх застосунків
- Простий для команди, яка не хоче складну реактивну архітектуру

#### Обмеження:

На великих проєктах із складним dependency graph і великою кількістю станів
`Provider` може ставати менш зручним, ніж Riverpod або BLoC.

</details>

<details>
<summary>55. Що таке архітектура BLoC?</summary>

#### Flutter

BLoC (Business Logic Component) - це підхід до архітектури, у якому
бізнес-логіка відокремлюється від UI і взаємодіє з ним через події та стани.

#### Основна ідея:

1. **UI відправляє event**
2. **BLoC обробляє логіку**
3. **BLoC віддає новий state**
4. **UI реагує на state**

#### Переваги:

1. **Чітке розділення відповідальностей**
2. **Прогнозований потік даних**
3. **Хороша testability**
4. **Зручно для складної логіки**

#### Типові елементи:

- `Event`
- `State`
- `Bloc`
- `BlocBuilder`
- `BlocListener`

#### Практичний сенс:

BLoC добре підходить для середніх і великих застосунків, де важлива дисципліна
архітектури, відокремлення доменної логіки та контрольований data flow.

</details>

<details>
<summary>56. Що таке Riverpod?</summary>

#### Flutter

Riverpod - це сучасна бібліотека для state management і dependency injection у
Flutter, створена як еволюція ідей `Provider`.

#### Що дає Riverpod:

1. **Кращий контроль залежностей**
2. **Відсутність жорсткої прив'язки до `BuildContext`**
3. **Кращу testability**
4. **Безпечніший і більш декларативний API**

#### Основна ідея:

Стан і залежності описуються через providers, а UI або сервіси підписуються на
них явно.

#### Чому його часто обирають:

- Простішe масштабувати великий код
- Менше прихованої магії дерева віджетів
- Зручніше працювати з async state

#### Практичне спостереження:

У сучасних Flutter-проєктах Riverpod часто вважається одним із найсильніших
варіантів для довгострокової підтримки продукту.

</details>

<details>
<summary>57. Що таке Redux у Flutter?</summary>

#### Flutter

Redux у Flutter - це підхід до керування станом із єдиним централізованим store,
де стан змінюється через actions і reducers.

#### Основні елементи Redux:

1. **Store** - єдине джерело істини
2. **Action** - опис наміру змінити стан
3. **Reducer** - функція, яка обчислює новий state
4. **Middleware** - місце для async логіки та side effects

#### Переваги:

1. **Прогнозований data flow**
2. **Централізований state**
3. **Прозорість змін**

#### Недоліки:

1. **Багато boilerplate**
2. **Може бути надмірним для Flutter UI**
3. **Часто програє сучаснішим підходам у зручності**

#### Практичний висновок:

Redux має історичну цінність і хорошу дисципліну, але в сучасних Flutter-
проєктах його використовують рідше, ніж Riverpod, Provider або BLoC.

</details>

<details>
<summary>58. Що таке `ValueNotifier`?</summary>

#### Flutter

`ValueNotifier<T>` - це простий реактивний клас у Flutter, який зберігає одне
значення і сповіщає слухачів, коли це значення змінюється.

#### Приклад:

```dart
final counter = ValueNotifier<int>(0);

counter.value++;
```

#### Для чого використовується:

1. **Простий локальний або screen-level state**
2. **Мінімалістичні реактивні сценарії**
3. **Коли не хочеться тягнути повноцінний state management**

#### З чим працює:

Найчастіше разом із `ValueListenableBuilder`.

```dart
ValueListenableBuilder<int>(
  valueListenable: counter,
  builder: (context, value, child) {
    return Text('$value');
  },
)
```

#### Практичний сенс:

`ValueNotifier` - хороший lightweight інструмент, якщо state простий і не
потребує складної архітектури.

</details>

<details>
<summary>59. Що таке `InheritedWidget`?</summary>

#### Flutter

`InheritedWidget` - це базовий механізм Flutter для передачі даних вниз по
дереву віджетів і оновлення залежних віджетів при зміні цих даних.

#### Основна роль:

1. **Поширення спільних даних у піддереві**
2. **Доступ до залежностей через `BuildContext`**
3. **Оптимізоване оновлення лише підписаних віджетів**

#### Де використовується:

- `Theme`
- `MediaQuery`
- `Directionality`
- `Provider` та інші бібліотеки під капотом

#### Чому це важливо:

`InheritedWidget` - фундаментальний механізм Flutter. Навіть якщо команда не
пише його вручну, багато популярних бібліотек базуються саме на ньому.

</details>

<details>
<summary>60. У чому різниця між `Provider` і `InheritedWidget`?</summary>

#### Flutter

`InheritedWidget` - це базовий механізм Flutter, а `Provider` - це зручна
бібліотечна абстракція поверх нього.

#### Основна різниця:

| Критерій      | `InheritedWidget`                     | `Provider`                     |
| ------------- | ------------------------------------- | ------------------------------ |
| Рівень        | Низькорівневий базовий API            | High-level abstraction         |
| Зручність     | Потрібно багато писати вручну         | Значно простіше у використанні |
| Boilerplate   | Більше                                | Менше                          |
| Масштабування | Незручно напряму для більшості команд | Краще для реальних застосунків |

#### Практичний висновок:

- Якщо потрібне розуміння основ Flutter, треба знати `InheritedWidget`
- Якщо треба швидко і зручно будувати app-level state, частіше використовують
  `Provider`

#### Ключова ідея:

`Provider` не замінює концепцію `InheritedWidget`, а робить її зручнішою для
щоденної розробки.

</details>

<details>
<summary>61. Як працює навігація у Flutter?</summary>

#### Flutter

Навігація у Flutter побудована навколо стеку маршрутів (routes). Коли користувач
переходить на новий екран, новий route додається у стек, а при поверненні зі
стека прибирається верхній route.

#### Основна ідея:

1. **Поточний екран є верхнім елементом стеку**
2. **Новий перехід додає новий route**
3. **Повернення видаляє верхній route**

#### Як це виглядає на практиці:

- Перехід вперед: `push`
- Повернення назад: `pop`

#### Варіанти навігації:

1. **Imperative navigation** через `Navigator`
2. **Named routes**
3. **Router API / declarative navigation**
4. **Пакети на кшталт `go_router` або `auto_route`**

#### Практичний висновок:

Для простих застосунків часто достатньо базового `Navigator`. Для великих
продуктів із deep links, web navigation і складним routing частіше обирають
router-based підхід.

</details>

<details>
<summary>62. Що таке `Navigator`?</summary>

#### Flutter

`Navigator` - це core-механізм Flutter для керування переходами між екранами.

#### Що він робить:

1. **Зберігає стек маршрутів**
2. **Додає нові екрани**
3. **Прибирає поточні екрани**
4. **Повертає результат назад у попередній екран**

#### Приклад ролі `Navigator`:

Його можна уявити як стек сторінок, де остання відкрита сторінка є активною.

#### Приклад:

```dart
Navigator.of(context).push(
  MaterialPageRoute(
    builder: (_) => const DetailsPage(),
  ),
);
```

#### Важливо:

`Navigator` тісно пов'язаний із `BuildContext`, тому треба викликати його з
контексту, який має доступ до потрібного навігаційного дерева.

</details>

<details>
<summary>63. Що роблять методи `Navigator.push()` і `Navigator.pop()`?</summary>

#### Flutter

`Navigator.push()` додає новий екран у стек навігації, а `Navigator.pop()`
повертає назад, видаляючи верхній екран зі стеку.

#### `Navigator.push()`

Відкриває новий route.

```dart
Navigator.push(
  context,
  MaterialPageRoute(
    builder: (_) => const DetailsPage(),
  ),
);
```

#### `Navigator.pop()`

Закриває поточний route.

```dart
Navigator.pop(context);
```

#### Додатково:

`pop()` може повертати значення назад:

```dart
Navigator.pop(context, 'success');
```

#### Практичний сенс:

Це базові методи для навігації у більшості Flutter-застосунків і один із перших
API, який потрібно впевнено знати на співбесіді.

</details>

<details>
<summary>64. Як передати дані між екранами у Flutter?</summary>

#### Flutter

Дані між екранами у Flutter найчастіше передаються через конструктор route
екрана або через результат, який повертається назад із `Navigator.pop()`.

#### Передача вперед через конструктор:

```dart
Navigator.push(
  context,
  MaterialPageRoute(
    builder: (_) => DetailsPage(userId: '42'),
  ),
);
```

#### Екран-отримувач:

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

#### Повернення даних назад:

```dart
final result = await Navigator.push<String>(
  context,
  MaterialPageRoute(
    builder: (_) => const DetailsPage(),
  ),
);
```

І назад:

```dart
Navigator.pop(context, 'done');
```

#### Інші варіанти:

1. **Named routes arguments**
2. **Global/app state**
3. **State management через Provider, Riverpod, BLoC**

#### Практичне правило:

Разові дані екран-до-екрана краще передавати явно через конструктор. Не варто
для цього одразу тягнути глобальний state.

</details>

<details>
<summary>65. Що таке `ModalBottomSheet`?</summary>

#### Flutter

`ModalBottomSheet` - це нижня модальна панель, яка з'являється поверх поточного
контенту і блокує взаємодію з фоном, поки не буде закрита.

#### Для чого використовується:

1. **Дії над контентом**
2. **Вибір опцій**
3. **Фільтри**
4. **Форми короткої взаємодії**

#### Приклад:

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

#### Важливо:

- Це саме **modal**-компонент
- Його можна закрити жестом або через `Navigator.pop(context)`

#### Практичний сенс:

`ModalBottomSheet` часто використовують у mobile UI замість окремого екрана або
діалогу, коли потрібно дати швидку контекстну взаємодію.

</details>

<details>
<summary>66. Що таке тема (`Theme`) у Flutter?</summary>

#### Flutter

Тема у Flutter - це централізований набір візуальних налаштувань застосунку:
кольори, типографіка, стилі кнопок, input-полів, app bar та інших компонентів.

#### Для чого вона потрібна:

1. **Єдиний візуальний стиль**
2. **Проста зміна дизайну в одному місці**
3. **Підтримка light/dark mode**
4. **Консистентність UI в усьому застосунку**

#### Приклад:

```dart
MaterialApp(
  theme: ThemeData(
    colorScheme: ColorScheme.fromSeed(seedColor: Colors.blue),
    useMaterial3: true,
  ),
  home: const HomePage(),
)
```

#### Доступ до теми:

```dart
final theme = Theme.of(context);
```

#### Практичний висновок:

У production-застосунках тема є важливою частиною design system, а не просто
набором кольорів.

</details>

<details>
<summary>67. У чому різниця між Material і Cupertino віджетами?</summary>

#### Flutter

Material і Cupertino - це два різні набори UI-компонентів у Flutter, які
відповідають різним дизайн-системам платформ.

#### Material:

- Орієнтований на **Google Material Design**
- Частіше використовується як дефолтний підхід у Flutter
- Основні віджети: `MaterialApp`, `Scaffold`, `AppBar`, `ElevatedButton`

#### Cupertino:

- Орієнтований на **Apple Human Interface Guidelines**
- Дає iOS-style вигляд і поведінку
- Основні віджети: `CupertinoApp`, `CupertinoPageScaffold`, `CupertinoButton`,
  `CupertinoNavigationBar`

#### Основна різниця:

| Критерій         | Material                    | Cupertino       |
| ---------------- | --------------------------- | --------------- |
| Дизайн           | Google Material             | Apple iOS style |
| Компоненти       | Android-first style         | iOS-first style |
| Типовий use case | Кросплатформений default UI | iOS-native feel |

#### Практичний підхід:

Багато команд використовують Material як базу навіть для кросплатформених
застосунків. Але якщо продукт хоче максимально нативне відчуття iOS, тоді
Cupertino стає важливим.

</details>

<details>
<summary>68. Як реалізувати адаптивний інтерфейс у Flutter?</summary>

#### Flutter

Адаптивний інтерфейс у Flutter реалізують через комбінацію responsive layout,
гнучких віджетів і логіки, яка враховує розмір та особливості екрана.

#### Основні інструменти:

1. **`LayoutBuilder`**
2. **`MediaQuery`**
3. **`Expanded` / `Flexible`**
4. **`Wrap`**
5. **`AspectRatio`**
6. **Умовний рендеринг для різних breakpoint-ів**

#### Приклад підходу:

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

#### Практичні принципи:

- Не фіксувати все жорстко в пікселях
- Враховувати portrait і landscape
- Враховувати tablet, foldable, desktop і web
- Виносити breakpoint logic у зрозумілу структуру

#### Практичний висновок:

Адаптивність у Flutter - це не один віджет, а дисципліна побудови layout так,
щоб UI коректно масштабувався на різних форм-факторах.

</details>

<details>
<summary>69. Що таке `FittedBox`?</summary>

#### Flutter

`FittedBox` - це віджет, який масштабує і позиціонує дочірній елемент так, щоб
він вписався у доступний простір відповідно до обраного `fit`.

#### Для чого використовується:

1. **Масштабування тексту або іконок**
2. **Адаптація контенту до контейнера**
3. **Уникнення overflow у деяких layout-сценаріях**

#### Приклад:

```dart
FittedBox(
  fit: BoxFit.scaleDown,
  child: Text(
    'Very long title',
    style: TextStyle(fontSize: 32),
  ),
)
```

#### Важливо:

`FittedBox` не "лікує" всі layout-проблеми. Його треба застосовувати тоді, коли
дійсно потрібне масштабування контенту, а не замість правильного управління
constraints.

#### Практичний сенс:

Це корисний інструмент для edge cases у responsive UI, але не основа layout-
архітектури.

</details>

<details>
<summary>70. Що таке ізоляти (Isolates) у Flutter?</summary>

#### Flutter

Ізоляти (Isolates) у Dart/Flutter - це окремі одиниці виконання з власною
пам'яттю та власним event loop.

#### Основна ідея:

На відміну від класичних threads зі спільною пам'яттю, isolates не ділять стан
напряму між собою.

#### Що це означає:

1. **Кожен isolate має свій heap**
2. **Кожен isolate виконується незалежно**
3. **Дані не шаряться напряму між isolate-ами**

#### Чому це важливо:

Такий підхід зменшує ризик race conditions і проблем зі спільною пам'яттю.

#### Практичний сенс у Flutter:

UI зазвичай працює в головному isolate. Важкі обчислення можна винести в інший
isolate, щоб не блокувати інтерфейс.

</details>

<details>
<summary>71. Для чого використовуються ізоляти?</summary>

#### Flutter

Ізоляти використовуються для винесення важких або довготривалих задач із
головного isolate, де працює UI.

#### Типові сценарії:

1. **Важкі обчислення**
2. **Парсинг великих JSON**
3. **Обробка файлів**
4. **Шифрування або декодування даних**
5. **CPU-intensive business logic**

#### Чому це потрібно:

Якщо виконувати важку синхронну роботу в головному isolate, UI може почати
лагати, пропускати кадри або "заморожуватися".

#### Практичний висновок:

Ізоляти потрібні не для будь-якої async-операції, а саме для CPU-bound задач.
Для звичайних HTTP-запитів або I/O найчастіше достатньо `Future` та
`async/await`.

</details>

<details>
<summary>72. Як ізоляти взаємодіють між собою?</summary>

#### Flutter

Ізоляти взаємодіють між собою через передачу повідомлень, а не через спільну
пам'ять.

#### Основні механізми:

1. **`SendPort`** - для відправки повідомлень
2. **`ReceivePort`** - для отримання повідомлень

#### Приклад ідеї:

Один isolate надсилає дані іншому isolate-у у вигляді message passing.

#### Важливо:

- isolates не можуть напряму змінювати спільний об'єкт
- дані передаються через серіалізовані або transferable повідомлення

#### Практичний сенс:

Ця модель складніша за звичайні async-виклики, але робить паралельне виконання
безпечнішим і більш передбачуваним.

</details>

<details>
<summary>73. Які типи Streams існують у Dart?</summary>

#### Flutter

У Dart найчастіше виділяють два основні типи streams: **single-subscription** та
**broadcast streams**.

#### 1. Single-subscription stream

Такий stream призначений для одного слухача.

#### Особливості:

1. **Має одного subscriber-а**
2. **Підходить для послідовного потоку даних**
3. **Часто використовується для file I/O або async data pipelines**

#### 2. Broadcast stream

Такий stream дозволяє кільком слухачам підписуватися одночасно.

#### Особливості:

1. **Має багато subscriber-ів**
2. **Підходить для подій**
3. **Схожий на event bus / signal source**

#### Практичний висновок:

Якщо джерело даних має одного споживача, зазвичай достатньо single-subscription
stream. Якщо потрібно розсилати події кільком слухачам, використовують broadcast
stream.

</details>

<details>
<summary>74. Що таке `FutureBuilder`?</summary>

#### Flutter

`FutureBuilder` - це Flutter-віджет, який будує UI на основі стану `Future`.

#### Для чого він використовується:

1. **Показ завантаження**
2. **Показ успішного результату**
3. **Показ помилки**

#### Приклад:

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

#### Що дає `snapshot`:

1. **`connectionState`**
2. **`hasData`**
3. **`hasError`**
4. **`data`**
5. **`error`**

#### Практичний нюанс:

Не варто створювати `Future` прямо всередині `build()` без потреби, інакше він
може запускатися повторно при кожному rebuild.

</details>

<details>
<summary>75. Що таке `StreamBuilder`?</summary>

#### Flutter

`StreamBuilder` - це Flutter-віджет, який будує UI на основі значень, що
надходять зі `Stream`.

#### Основна різниця з `FutureBuilder`:

- `FutureBuilder` працює з одноразовим результатом
- `StreamBuilder` працює з потоком оновлень у часі

#### Приклад:

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

#### Типові сценарії:

1. **WebSocket updates**
2. **Live data**
3. **BLoC state streams**
4. **Реактивні події**

#### Практичний сенс:

`StreamBuilder` зручний для реактивного UI, але важливо контролювати життєвий
цикл stream-ів, щоб не отримувати зайві підписки або memory leaks.

</details>

<details>
<summary>76. Як працюють анімації у Flutter?</summary>

#### Flutter

Анімації у Flutter працюють через послідовну зміну значень у часі та
перемальовування UI на кожному кадрі.

#### Основна ідея:

1. **Є початкове значення**
2. **Є кінцеве значення**
3. **Flutter обчислює проміжні стани**
4. **UI оновлюється кадр за кадром**

#### Основні складові:

1. **`AnimationController`** - керує часом анімації
2. **`Tween`** - задає діапазон значень
3. **`CurvedAnimation`** - задає криву руху
4. **Builder або Animated widget** - оновлює UI

#### Два основні підходи:

1. **Implicit animations** - прості анімації без ручного контролю
2. **Explicit animations** - повний контроль через controller

#### Практичний сенс:

Flutter має дуже сильну animation system, бо UI малюється власним rendering
engine, і це дає багато гнучкості для smooth transitions та custom motion.

</details>

<details>
<summary>77. Що таке `AnimationController`?</summary>

#### Flutter

`AnimationController` - це об'єкт, який керує життєвим циклом explicit анімації:
запуском, зупинкою, реверсом і поточним прогресом.

#### Що він робить:

1. **Зберігає тривалість анімації**
2. **Рухається по шкалі значень, зазвичай від `0.0` до `1.0`**
3. **Дає змогу запускати `forward()`, `reverse()`, `repeat()`**

#### Приклад:

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

#### Важливо:

`AnimationController` зазвичай треба `dispose()`-ити, інакше можна отримати
витік ресурсів.

</details>

<details>
<summary>78. Що таке Tween-анімація?</summary>

#### Flutter

Tween-анімація - це анімація, у якій значення плавно змінюється між двома
точками: `begin` і `end`.

#### Основна ідея:

Tween описує, **як саме інтерполювати значення**.

#### Приклад:

```dart
final animation = Tween<double>(
  begin: 0,
  end: 100,
).animate(controller);
```

#### Що можна анімувати через Tween:

1. **Числа**
2. **Кольори**
3. **Відступи**
4. **Розміри**
5. **Alignment**

#### Практичний сенс:

Tween не запускає анімацію сам по собі. Він лише описує перехід значень, а рухає
цей перехід `AnimationController`.

</details>

<details>
<summary>79. Що таке `vsync`?</summary>

#### Flutter

`vsync` - це механізм синхронізації анімації з частотою оновлення екрана.

#### Навіщо він потрібен:

1. **Щоб не рахувати кадри, коли віджет не видно**
2. **Щоб зменшити зайве навантаження**
3. **Щоб анімації були синхронізовані з rendering pipeline**

#### Як це виглядає:

У `State` часто використовують `SingleTickerProviderStateMixin` і передають
`this` у `AnimationController`.

```dart
controller = AnimationController(
  vsync: this,
  duration: const Duration(milliseconds: 300),
);
```

#### Практичний сенс:

Без `vsync` анімації могли б продовжувати працювати навіть тоді, коли їх не
треба рендерити, що погіршує продуктивність.

</details>

<details>
<summary>80. Що таке ticker у Flutter?</summary>

#### Flutter

Ticker у Flutter - це об'єкт, який генерує callback на кожен кадр анімації.

#### Основна роль:

1. **Повідомляє про кожен frame**
2. **Дає змогу просувати анімацію в часі**
3. **Використовується всередині `AnimationController`**

#### Простими словами:

Ticker - це "метроном" для анімації.

#### Практичний сенс:

Коли ви працюєте з `AnimationController`, ви майже завжди опосередковано
працюєте і з ticker.

</details>

<details>
<summary>81. Що таке `AnimatedBuilder`?</summary>

#### Flutter

`AnimatedBuilder` - це віджет, який перебудовує частину UI у відповідь на зміни
анімованого значення.

#### Для чого він потрібен:

1. **Реагувати на `Animation`**
2. **Оновлювати лише потрібну частину UI**
3. **Будувати explicit animations без зайвого boilerplate**

#### Приклад:

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

#### Перевага:

Можна передати `child`, який не буде перебудовуватися на кожному кадрі.

</details>

<details>
<summary>82. Що таке `AnimatedContainer`?</summary>

#### Flutter

`AnimatedContainer` - це віджет для implicit animation, який автоматично анімує
зміни своїх властивостей.

#### Що він може анімувати:

1. **Розмір**
2. **Колір**
3. **Padding**
4. **Margin**
5. **Alignment**
6. **Decoration**

#### Приклад:

```dart
AnimatedContainer(
  duration: const Duration(milliseconds: 300),
  width: isExpanded ? 200 : 100,
  color: isExpanded ? Colors.blue : Colors.red,
)
```

#### Практичний сенс:

`AnimatedContainer` - один із найзручніших способів швидко додати плавний UI без
ручного керування controller-ами.

</details>

<details>
<summary>83. У чому різниця між implicit та explicit анімаціями?</summary>

#### Flutter

Різниця між implicit та explicit animation полягає в рівні контролю.

#### Implicit animations:

Flutter сам керує анімацією, коли змінюються властивості віджета.

#### Приклади:

- `AnimatedContainer`
- `AnimatedOpacity`
- `AnimatedAlign`

#### Explicit animations:

Розробник сам керує анімацією через `AnimationController`.

#### Приклади:

- `AnimatedBuilder`
- `FadeTransition`
- `ScaleTransition`

#### Основна різниця:

| Критерій   | Implicit animations   | Explicit animations       |
| ---------- | --------------------- | ------------------------- |
| Контроль   | Менший                | Повний                    |
| Складність | Нижча                 | Вища                      |
| Use case   | Прості UI transitions | Складні кастомні сценарії |

#### Практичний висновок:

Для простих анімацій краще починати з implicit widgets. Для складних motion
сценаріїв і синхронізації кількох анімацій потрібні explicit animations.

</details>

<details>
<summary>84. Що таке архітектура Flutter?</summary>

#### Flutter

Архітектура Flutter складається з кількох ключових шарів: framework, engine,
embedder і платформа.

#### Основні шари:

1. **Framework** - віджети, rendering, gestures, animation, foundation
2. **Engine** - рендеринг, текст, compositing, Skia/graphics integration
3. **Embedder** - інтеграція з Android, iOS, desktop або web
4. **Platform** - нативна ОС та її API

#### Основна ідея:

Flutter не просто обгортає нативні UI-компоненти, а будує свій UI стек зверху
вниз.

#### Практичний сенс:

Саме через цю архітектуру Flutter дає високу консистентність UI між платформами,
але інколи вимагає окремої інтеграції з нативним кодом.

</details>

<details>
<summary>85. Що таке rendering pipeline у Flutter?</summary>

#### Flutter

Rendering pipeline у Flutter - це послідовність етапів, через які проходить UI
від зміни state до відображення кадру на екрані.

#### Спрощено pipeline виглядає так:

1. **State change**
2. **Build**
3. **Layout**
4. **Paint**
5. **Compositing**
6. **Rasterization**

#### Що це означає:

- `build` формує widget tree
- `layout` рахує розміри та позиції
- `paint` малює візуальний результат
- engine перетворює це в кадр

#### Практичний сенс:

Розуміння rendering pipeline допомагає дебажити jank, зайві rebuild-і,
перефарбування та проблеми продуктивності.

</details>

<details>
<summary>86. Що таке Widgets, Elements і RenderObjects?</summary>

#### Flutter

Це три ключові рівні UI-моделі Flutter.

#### Widgets

Widgets - це immutable конфігурації UI.

#### Elements

Elements - це "живі" зв'язки між widget tree та render tree.

#### RenderObjects

RenderObjects відповідають за layout, paint і low-level rendering.

#### Простими словами:

1. **Widget** - що ми хочемо показати
2. **Element** - зв'язок і життєвий цикл у дереві
3. **RenderObject** - як це реально вимірюється і малюється

#### Практичний сенс:

Ця модель пояснює, чому Flutter може ефективно оновлювати UI, не перебудовуючи
все заново на низькому рівні.

</details>

<details>
<summary>87. Що таке `FlutterEngine`?</summary>

#### Flutter

`FlutterEngine` - це низькорівнева частина Flutter, яка відповідає за виконання
Dart-коду та рендеринг кадрів.

#### Що входить у його відповідальність:

1. **Dart runtime**
2. **Рендеринг**
3. **Text layout**
4. **Compositing**
5. **Платформену взаємодію на низькому рівні**

#### Практичний сенс:

Framework дає зручний API для віджетів, а engine відповідає за те, щоб це
реально працювало на екрані пристрою.

</details>

<details>
<summary>88. Що таке `WidgetsBinding`?</summary>

#### Flutter

`WidgetsBinding` - це binding-шар, який з'єднує Flutter framework із engine та
координує життєвий цикл застосунку на рівні віджетів.

#### Для чого він потрібен:

1. **Ініціалізація framework**
2. **Робота з frame callbacks**
3. **Доступ до binding lifecycle**
4. **Координація між framework і engine**

#### Приклад:

```dart
WidgetsFlutterBinding.ensureInitialized();
```

#### Практичний сенс:

Це один із центральних механізмів Flutter runtime, навіть якщо в типовому коді
розробник бачить його лише опосередковано.

</details>

<details>
<summary>89. Що таке `WidgetsBindingObserver`?</summary>

#### Flutter

`WidgetsBindingObserver` - це інтерфейс, який дозволяє слухати зміни життєвого
циклу застосунку та інші framework events.

#### Для чого використовується:

1. **Відстеження `AppLifecycleState`**
2. **Реакція на `resumed`, `paused`, `inactive`, `detached`**
3. **Обробка platform-level змін**

#### Приклад use case:

- зупинити відео, коли застосунок іде у background
- оновити дані, коли застосунок повертається у foreground

#### Практичний сенс:

Це важливий інструмент для життєвого циклу, особливо у застосунках із медіа,
аналітикою, socket-з'єднаннями або background-sensitive логікою.

</details>

<details>
<summary>90. Що таке platform channels?</summary>

#### Flutter

Platform channels - це механізм взаємодії між Flutter-кодом на Dart і нативним
кодом платформи, таким як Kotlin/Java на Android або Swift/Objective-C на iOS.

#### Для чого вони потрібні:

1. **Доступ до нативних API**
2. **Робота з платформеними SDK**
3. **Інтеграція з функціоналом, якого немає у Flutter напряму**

#### Основні типи:

1. **`MethodChannel`**
2. **`EventChannel`**
3. **`BasicMessageChannel`**

#### Практичний сенс:

Platform channels потрібні тоді, коли Flutter-додаток виходить за межі чистого
UI і має взаємодіяти з нативними можливостями пристрою або сторонніми SDK.

</details>

<details>
<summary>91. Що таке tree shaking?</summary>

#### Flutter

Tree shaking - це процес видалення невикористовуваного коду з фінального build.

#### Основна ідея:

Якщо певний код не використовується, компілятор або білд-система не включає його
в релізну збірку.

#### Навіщо це потрібно:

1. **Менший розмір застосунку**
2. **Швидше завантаження**
3. **Менше зайвого коду в production**

#### Практичний сенс у Flutter:

Tree shaking особливо важливий для release build-ів, бо він допомагає зменшити
розмір артефактів і покращити ефективність доставки застосунку.

</details>

<details>
<summary>92. Як оптимізувати продуктивність застосунку Flutter?</summary>

#### Flutter

Оптимізація продуктивності у Flutter зводиться до зменшення зайвих rebuild-ів,
repaint-ів, дорогих обчислень на UI isolate та надмірного споживання пам'яті.

#### Основні напрямки оптимізації:

1. **Зменшувати кількість непотрібних rebuild-ів**
2. **Не виконувати важкі CPU-bound задачі в головному isolate**
3. **Використовувати ліниві списки**
4. **Використовувати `const`, де це можливо**
5. **Оптимізувати зображення і ресурси**
6. **Профілювати застосунок у profile mode**

#### Практичні інструменти:

- Flutter DevTools
- Performance overlay
- Timeline profiling
- Memory profiler

#### Практичний висновок:

Продуктивність у Flutter треба не "вгадувати", а вимірювати. Хороша оптимізація
майже завжди починається з профілювання, а не з випадкових змін.

</details>

<details>
<summary>93. Як зменшити кількість перебудов віджетів?</summary>

#### Flutter

Щоб зменшити кількість rebuild-ів, потрібно локалізувати state і перебудовувати
лише ті частини дерева, які справді залежать від змін.

#### Основні підходи:

1. **Виносити UI у дрібніші віджети**
2. **Використовувати `const`**
3. **Локалізувати state якомога нижче**
4. **Не слухати зайві глобальні стани**
5. **Використовувати selector-підходи (`select`, selectors, derived state)**

#### Практичний приклад мислення:

Якщо змінюється лише badge у header, не треба перебудовувати весь екран.

#### Важливо:

Rebuild сам по собі не завжди проблема. Проблема виникає тоді, коли rebuild
дорогий або відбувається занадто часто.

</details>

<details>
<summary>94. Що таке `RepaintBoundary`?</summary>

#### Flutter

`RepaintBoundary` - це віджет, який відокремлює частину render tree в окрему
область перефарбування.

#### Навіщо він потрібен:

1. **Щоб не перефарбовувати весь екран**
2. **Щоб ізолювати expensive paint-ділянки**
3. **Щоб покращити продуктивність у складному UI**

#### Основна ідея:

Якщо одна частина дерева часто змінюється, а інша ні, `RepaintBoundary` може
допомогти зменшити зайві repaint-и.

#### Практичний нюанс:

Його не варто додавати всюди бездумно. Як і будь-яка оптимізація, він має сенс
там, де профілювання показало реальну repaint-проблему.

</details>

<details>
<summary>95. Як зменшити розмір застосунку Flutter?</summary>

#### Flutter

Розмір Flutter-застосунку зменшують через оптимізацію залежностей, ресурсів та
release build конфігурації.

#### Основні підходи:

1. **Видаляти непотрібні пакети**
2. **Оптимізувати assets і зображення**
3. **Використовувати tree shaking**
4. **Не тягнути великі SDK без потреби**
5. **Мінімізувати кількість шрифтів і локалей**

#### Практичні кроки:

- збирати release, а не debug
- аналізувати склад білду
- перевіряти, які пакети додають вагу

#### Практичний висновок:

Розмір застосунку часто збільшується не через Flutter як такий, а через
надлишкові ресурси, SDK та сторонні залежності.

</details>

<details>
<summary>96. Які best practices для великих Flutter застосунків?</summary>

#### Flutter

Для великих Flutter-застосунків ключові best practices пов'язані з архітектурою,
модульністю, тестованістю і дисципліною роботи зі станом.

#### Основні практики:

1. **Feature-based або layered структура проєкту**
2. **Чітке розділення UI, domain і data layer**
3. **Прозорий state management**
4. **Dependency injection**
5. **Покриття тестами критичної логіки**
6. **Єдина design system / theme system**
7. **Логування, аналітика, error reporting**

#### Додатково:

- уникати god-classes
- не змішувати network, UI і business logic в одному місці
- стандартизувати підходи команди

#### Практичний висновок:

Великий Flutter-застосунок майже завжди програє без архітектурної дисципліни,
навіть якщо стартував як "простий мобільний клієнт".

</details>

<details>
<summary>97. Які типи тестування існують у Flutter?</summary>

#### Flutter

У Flutter найчастіше використовують три основні типи тестування.

#### 1. Unit tests

Тестують окремі функції, сервіси, use cases, business logic.

#### 2. Widget tests

Тестують окремі віджети і їхню поведінку в ізольованому середовищі.

#### 3. Integration tests

Тестують реальні user flows у майже повному застосунку.

#### Практичний сенс:

Здорова тестова стратегія зазвичай комбінує всі три типи, а не покладається лише
на один.

</details>

<details>
<summary>98. Що таке unit testing?</summary>

#### Flutter

Unit testing - це тестування маленьких ізольованих одиниць коду без UI і без
залежності від реального застосунку.

#### Що зазвичай тестують:

1. **Функції**
2. **Сервіси**
3. **Use cases**
4. **Парсинг**
5. **Валідацію**

#### Переваги:

1. **Швидке виконання**
2. **Дешевий дебаг**
3. **Добре підходить для бізнес-логіки**

#### Практичний висновок:

Якщо логіку можна протестувати без Flutter UI, це часто найстабільніший і
найдешевший тип тестування.

</details>

<details>
<summary>99. Що таке widget testing?</summary>

#### Flutter

Widget testing - це тестування віджетів Flutter у контрольованому середовищі без
запуску повного застосунку на реальному пристрої.

#### Що можна перевіряти:

1. **Що віджет відображає**
2. **Як реагує на user interaction**
3. **Чи змінюється UI після дії**

#### Приклад сценарію:

- натиснути кнопку
- перевірити, що з'явився новий текст

#### Практичний сенс:

Widget tests дають хороший баланс між швидкістю і цінністю, тому у Flutter їх
часто вважають одним із найкорисніших типів тестів.

</details>

<details>
<summary>100. Що таке integration testing?</summary>

#### Flutter

Integration testing - це тестування повних або майже повних user flows у
застосунку.

#### Що перевіряється:

1. **Взаємодія кількох екранів**
2. **Навігація**
3. **Робота з реальними сервісами або їхніми близькими замінами**
4. **Повна поведінка користувацького сценарію**

#### Приклад:

- логін
- відкриття списку
- перехід у деталі
- завершення дії користувача

#### Практичний мінус:

Integration tests повільніші, крихкіші і дорожчі за unit та widget tests, тому
ними зазвичай покривають саме критичні сценарії.

</details>

<details>
<summary>101. Як протестувати окремий віджет у Flutter?</summary>

#### Flutter

Окремий віджет у Flutter зазвичай тестують через widget test із використанням
`testWidgets`, `WidgetTester` і `pumpWidget()`.

#### Приклад:

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

#### Типовий процес:

1. **Побудувати віджет через `pumpWidget()`**
2. **Знайти елементи через `find`**
3. **Виконати interaction**
4. **Перевірити очікуваний результат**

#### Практичний сенс:

Для більшості UI-компонентів це базовий і правильний спосіб перевірки поведінки.

</details>

<details>
<summary>102. Як виконувати HTTP-запити у Flutter?</summary>

#### Flutter

HTTP-запити у Flutter зазвичай виконують через пакети на кшталт `http` або
`dio`.

#### Основні підходи:

1. **Пакет `http`** - простий базовий варіант
2. **Пакет `dio`** - більш потужний варіант із interceptors, retries і config

#### Приклад із `http`:

```dart
final response = await http.get(
  Uri.parse('https://example.com/api/users'),
);
```

#### Практичний підхід у production:

- окремий API client
- моделі даних
- error handling
- timeout/retry strategy
- логування запитів

#### Практичний висновок:

Сам виклик HTTP простий, але production-ready networking - це вже окрема
архітектурна зона застосунку.

</details>

<details>
<summary>103. Які бази даних можна використовувати з Flutter?</summary>

#### Flutter

З Flutter можна використовувати кілька типів локальних і віддалених баз даних.

#### Локальні варіанти:

1. **SQLite**
2. **Hive**
3. **Isar**
4. **SharedPreferences / key-value storage**

#### Віддалені варіанти:

1. **Firebase Firestore**
2. **Supabase / PostgreSQL-backed services**
3. **Будь-який backend із REST або GraphQL API**

#### Практичний вибір:

- **Hive / Isar** - швидке локальне сховище
- **SQLite** - структуровані локальні дані
- **Firestore** - real-time cloud data

#### Практичний висновок:

Вибір бази залежить не від Flutter, а від моделі даних, offline-first вимог,
синхронізації та складності домену.

</details>

<details>
<summary>104. Що таке Flutter plugins?</summary>

#### Flutter

Flutter plugins - це пакети, які надають Flutter API для доступу до нативних
можливостей платформи.

#### Що вони дають:

1. **Доступ до камери**
2. **Доступ до геолокації**
3. **Push notifications**
4. **Bluetooth, sensors, storage, permissions**

#### Основна ідея:

Плагін має Dart API і платформені реалізації для Android, iOS та інколи інших
платформ.

#### Практичний сенс:

Plugins дозволяють не писати platform channels вручну щоразу, а використовувати
готову інтеграцію.

</details>

<details>
<summary>105. Як інтегрувати Flutter у вже існуючий нативний застосунок?</summary>

#### Flutter

Flutter можна інтегрувати в існуючий Android або iOS застосунок як окремий
модуль.

#### Основна ідея:

Flutter не обов'язково має бути "весь застосунок". Його можна вбудувати лише в
окремі екрани або фічі.

#### Як це зазвичай працює:

1. **Створюється Flutter module**
2. **Нативний застосунок підключає цей модуль**
3. **Певні екрани відкриваються через `FlutterActivity`, `FlutterFragment` або
   iOS integration**

#### Практичні сценарії:

- поступова міграція нативного застосунку на Flutter
- запуск нової фічі на Flutter без повного переписування

#### Практичний висновок:

Add-to-app підхід корисний тоді, коли бізнес не готовий переписати все, але хоче
поступово використати Flutter у продукті.

</details>

<details>
<summary>106. Як реалізувати платформо-залежний код у Flutter?</summary>

#### Flutter

Платформо-залежний код у Flutter реалізують кількома способами залежно від рівня
задачі.

#### Основні підходи:

1. **Platform channels** - коли потрібен нативний код
2. **Готові plugins** - коли вже є пакет для потрібної функції
3. **`Platform.isAndroid` / `Platform.isIOS`** - для платформних гілок логіки
4. **`defaultTargetPlatform`** - для UI-поведінки

#### Приклад:

```dart
if (Platform.isIOS) {
  // iOS-specific logic
} else if (Platform.isAndroid) {
  // Android-specific logic
}
```

#### Практичний висновок:

Якщо є готовий перевірений plugin, краще використовувати його. Якщо немає, тоді
вже писати platform channel або власний plugin.

</details>
