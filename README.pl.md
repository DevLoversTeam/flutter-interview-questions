**Read in other languages: [English 🇺🇸](README.en.md),
[Polska 🇵🇱](README.pl.md), [German 🇩🇪](README.de.md), [French 🇫🇷](README.fr.md),
[Spanish 🇪🇸](README.es.md), [Українська 🇺🇦](README.md).**

<h1>
  Flutter <img src="./assets/flutter.svg" width="40" height="40" />
</h1>

<h2>Najpopularniejsze pytania i odpowiedzi na rozmowie o Flutterze</h2>

<details>
<summary>1. Czym jest Flutter?</summary>

#### Flutter

Flutter to open-source UI toolkit od Google do tworzenia aplikacji
wieloplatformowych z jednej bazy kodu.

#### Główne cechy Fluttera:

1. **Wieloplatformowość:** Pozwala tworzyć aplikacje na iOS, Android, Web,
   Windows, macOS i Linux.

2. **Własny silnik renderowania:** Flutter sam rysuje interfejs, zamiast opierać
   UI na natywnych widgetach OEM.

3. **Podejście oparte na widgetach:** W Flutterze prawie wszystko to widgety:
   ekran, tekst, odstępy, przyciski, animacje.

4. **Wysoka szybkość developmentu:** Hot Reload pozwala szybko widzieć zmiany w
   kodzie bez pełnego restartu aplikacji.

5. **Jeden język developmentu:** Cały kod kliencki zwykle pisze się w Dart.

Flutter często wykorzystuje się do szybkiego tworzenia MVP, produktowych aplikacji
mobilnych i wewnętrznych systemów firmowych.

</details>

<details>
<summary>2. Dlaczego Flutter jest często wybierany do developmentu mobilnego?</summary>

#### Flutter

Flutter jest często wybierany ze względu na balans między szybkością developmentu,
jakością UI i możliwością utrzymywania jednej bazy kodu dla kilku platform.

#### Główne powody:

1. **Jedna baza kodu:** Mniej duplikacji logiki między Android i iOS.

2. **Szybki development:** Hot Reload przyspiesza iteracje zespołu.

3. **Przewidywalny UI:** Flutter sam renderuje interfejs, więc design wygląda
   bardziej spójnie między platformami.

4. **Dobra wydajność:** Dla większości aplikacji biznesowych Flutter daje
   wydajność wystarczającą na poziom production.

5. **Silny ekosystem:** Jest duża liczba pakietów do nawigacji, stanu, HTTP,
   lokalnego storage, analityki i testowania.

6. **Wygodna praca z custom UI:** Jeśli produkt ma dużo niestandardowych ekranów,
   animacji lub złożony design system, Flutter często wygrywa szybkością
   realizacji.

#### Kiedy to szczególnie się opłaca:

- Gdy trzeba szybko wejść na iOS i Android.
- Gdy zespół jest mały i ważne jest obniżenie kosztów utrzymania.
- Gdy produkt ma dużo custom interfejsu.

</details>

<details>
<summary>3. Jakie platformy wspiera Flutter?</summary>

#### Flutter

Flutter wspiera kilka platform z jednej bazy kodu.

#### Główne platformy:

1. **Android**
2. **iOS**
3. **Web**
4. **Windows**
5. **macOS**
6. **Linux**

#### Dodatkowo:

- Flutter jest też używany do **rozwiązań embedded** i urządzeń
  wyspecjalizowanych, jeśli istnieje odpowiednia integracja z silnikiem.
- Najczęściej w developmentcie komercyjnym Flutter stosuje się właśnie do
  **platform mobilnych**, ale web i desktop również są wspierane oficjalnie.

</details>

<details>
<summary>4. Czym jest Dart i dlaczego Flutter używa właśnie tego języka?</summary>

#### Flutter

Dart to język programowania stworzony przez Google. Flutter używa Darta jako
głównego języka do pisania UI, logiki biznesowej i interakcji z frameworkiem.

#### Dlaczego Flutter używa Darta:

1. **Szybka kompilacja podczas developmentu:** To umożliwia Hot Reload.

2. **AOT i JIT:** Dart wspiera JIT dla szybkiego developmentu oraz kompilację AOT
   dla efektywnego production builda.

3. **Prosta składnia:** Dart jest łatwo przyswajalny dla developerów z
   doświadczeniem w Java, JavaScript, C#, Kotlin lub Swift.

4. **Dobre wsparcie asynchroniczności:** `Future`, `Stream`, `async/await`
   naturalnie pasują do developmentu klienckiego.

5. **Silne typowanie:** To poprawia utrzymywalność, refaktoryzację i stabilność
   dużych projektów.

#### Powód praktyczny:

Flutter potrzebuje języka, który dobrze działa zarówno w trybie szybkiego
developmentu, jak i w trybie zoptymalizowanej kompilacji. Dart pokrywa oba te
scenariusze.

</details>

<details>
<summary>5. Jaka jest struktura projektu Flutter?</summary>

#### Flutter

Typowy projekt Flutter ma kilka standardowych katalogów i plików pomocniczych.

#### Bazowa struktura:

1. **`lib/`** - główny kod aplikacji.
2. **`test/`** - testy unit i widget.
3. **`android/`** - natywna część Android projektu.
4. **`ios/`** - natywna część iOS projektu.
5. **`web/`** - konfiguracja i entry point dla web.
6. **`macos/`, `windows/`, `linux/`** - platformy desktop.
7. **`pubspec.yaml`** - zależności, zasoby, metadane projektu.

#### Najważniejsze w praktyce:

- W większości przypadków główna logika produktowa żyje w `lib/`.
- Foldery platformowe zmienia się wtedy, gdy potrzebne są natywne ustawienia,
  permissions, konfiguracja SDK lub platform channels.

#### Przykład logicznej struktury wewnątrz `lib/`:

```text
lib/
  core/
  features/
  shared/
  app/
  main.dart
```

W projektach production zwykle ważne jest nie tylko znać standardową strukturę
Fluttera, ale też mieć zrozumiałą architekturę feature-based lub layered.

</details>

<details>
<summary>6. Czym jest plik `pubspec.yaml` i do czego służy?</summary>

#### Flutter

`pubspec.yaml` to główny plik konfiguracyjny projektu Dart/Flutter.

#### Do czego jest używany:

1. **Zarządzanie zależnościami:** Pakiety, których używa aplikacja.

2. **Opis zasobów:** Podłączanie assets, fontów, ikon.

3. **Metadane projektu:** Nazwa, wersja, opis, environment constraints.

4. **Ustawienia zależności dev:** Na przykład `flutter_test`, `build_runner`,
   `flutter_lints`.

#### Przykład:

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

#### Ważne:

Po zmianie `pubspec.yaml` zwykle uruchamia się `flutter pub get`, żeby pobrać
nowe zależności.

</details>

<details>
<summary>7. Jaka jest rola funkcji `main()` w Flutterze?</summary>

#### Flutter

`main()` to punkt wejścia do aplikacji Flutter, od którego zaczyna się wykonanie
programu.

#### Główna rola:

1. **Uruchomienie aplikacji:** To właśnie w `main()` zwykle wywołuje się
   `runApp()`.

2. **Wstępna inicjalizacja:** Można tu zainicjalizować serwisy, kontener DI,
   Firebase, lokalny storage lub konfigurację środowiska.

3. **Konfiguracja przed startem UI:** Jeśli przed uruchomieniem potrzebny jest
   `await`, `main()` można zrobić jako `async`.

#### Przykład:

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}
```

#### Przykład z inicjalizacją:

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
<summary>8. Co robi funkcja `runApp()`?</summary>

#### Flutter

`runApp()` uruchamia aplikację Flutter i montuje przekazany root widget w drzewie
widgetów.

#### Co dzieje się w praktyce:

1. **Tworzony jest root node UI:** To od niego zaczyna się całe drzewo
   widgetów.

2. **Flutter rozpoczyna proces budowy interfejsu:** Dalej framework wywołuje
   `build()` i renderuje ekran.

3. **Aplikacja przechodzi pod kontrolę Flutter framework:** Wszystkie kolejne
   aktualizacje UI są obsługiwane przez system widgetów, elementów i render
   objects.

#### Przykład:

```dart
void main() {
  runApp(const MyApp());
}
```

#### Ważne:

- Zwykle do `runApp()` przekazuje się `MaterialApp`, `CupertinoApp` albo własny
  root widget `App`.
- Ponowne wywołanie `runApp()` jest możliwe, ale w typowym cyklu życia aplikacji
  zwykle wywołuje się je jeden raz.

</details>

<details>
<summary>9. Czym są widgety (widgets) w Flutterze?</summary>

#### Flutter

Widgety to podstawowe building blocks UI w Flutterze. Opisują, jak ma wyglądać
część interfejsu i jak ma się zachowywać.

#### Przykłady tego, co jest widgetem:

1. **Tekst:** `Text`
2. **Przycisk:** `ElevatedButton`
3. **Odstęp:** `Padding`
4. **Układ:** `Column`, `Row`, `Stack`
5. **Ekran:** `Scaffold`

#### Cechy widgetów:

1. **Deklaratywność:** Opisujesz UI jako zestaw widgetów.

2. **Kompozycja:** Złożony interfejs składa się z prostych widgetów.

3. **Niezmienność:** Same widgety są immutable; zmiany UI osiąga się przez
   przebudowę drzewa.

#### Przykład:

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
<summary>10. Jaka jest różnica między `StatelessWidget` i `StatefulWidget`?</summary>

#### Flutter

Różnica polega na tym, czy widget ma wewnętrzny zmienny stan, który wpływa na
jego wyświetlanie.

#### `StatelessWidget`:

Używany dla UI, który zależy tylko od parametrów wejściowych i nie ma własnego
zmiennego stanu.

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

Używany wtedy, gdy widget ma stan, który może się zmieniać w trakcie cyklu życia.

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

#### Główne różnice:

1. **Stan:** `StatelessWidget` nie ma mutable state, `StatefulWidget` ma.

2. **Aktualizacja UI:** W `StatefulWidget` UI aktualizuje się przez `setState()`
   lub inne podejścia state management.

3. **Scenariusze użycia:** Statyczne elementy UI kontra interaktywne albo
   dynamiczne części ekranu.

</details>

<details>
<summary>11. Czym jest drzewo widgetów (widget tree)?</summary>

#### Flutter

Drzewo widgetów to hierarchia wszystkich widgetów, z których składa się interfejs
aplikacji Flutter.

#### Jak to działa:

1. **Każdy widget może zawierać widgety potomne.**

2. **Cały ekran jest budowany jako drzewo zagnieżdżonych elementów.**

3. **Podczas zmian stanu Flutter przebudowuje części tego drzewa.**

#### Przykład:

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

W tym przykładzie `MaterialApp` jest rootem, wewnątrz znajduje się `Scaffold`,
dalej `AppBar`, `Center` i `Text`.

#### Dlaczego to ważne:

- Zrozumienie widget tree pomaga poprawnie budować UI.
- To krytyczne dla debugowania, optymalizacji rebuildów i pracy z contextem.

</details>

<details>
<summary>12. Czym jest `BuildContext`?</summary>

#### Flutter

`BuildContext` to referencja do miejsca widgetu w drzewie widgetów.

#### Do czego jest potrzebny:

1. **Dostęp do zależności rodzica:** Na przykład `Theme`, `MediaQuery`,
   `Navigator`, `ScaffoldMessenger`, `Provider`.

2. **Nawigacja:** Przez `Navigator.of(context)`.

3. **Pobieranie lokalnych ustawień środowiska:** Rozmiar ekranu, motyw, locale i
   inne inherited dependencies.

#### Przykład:

```dart
final theme = Theme.of(context);
final size = MediaQuery.of(context).size;
```

#### Ważny niuans:

`BuildContext` musi należeć do właściwego miejsca w drzewie. Na przykład jeśli
wywołasz `ScaffoldMessenger.of(context)` zbyt wcześnie albo z kontekstu, który
nie ma potrzebnego przodka, dostaniesz błąd.

#### Zasada praktyczna:

Context należy traktować nie jako "globalny dostęp", ale jako "pozycję widgetu w
drzewie w danym momencie".

</details>

<details>
<summary>13. Czym jest `Key` w Flutterze i do czego służy?</summary>

#### Flutter

`Key` to mechanizm identyfikacji widgetów w drzewie, który pomaga Flutterowi
poprawnie dopasowywać stare i nowe widgety podczas rebuildu.

#### Do czego są potrzebne `Key`:

1. **Zachowanie stanu przy zmianie kolejności elementów.**

2. **Poprawne działanie list i dynamicznych kolekcji.**

3. **Dostęp do widgetów w testach.**

4. **Zarządzanie unikalnością elementów w drzewie.**

#### Przykład:

```dart
ListView(
  children: const [
    ListTile(key: ValueKey('user_1'), title: Text('User 1')),
    ListTile(key: ValueKey('user_2'), title: Text('User 2')),
  ],
)
```

#### Główne typy:

1. **`ValueKey`** - gdy jest stabilna wartość-identyfikator.
2. **`ObjectKey`** - gdy key bazuje na obiekcie.
3. **`UniqueKey`** - gdy potrzebna jest gwarantowana unikalność.
4. **`GlobalKey`** - do dostępu do state lub context konkretnego widgetu.

#### Ważne:

`GlobalKey` trzeba używać ostrożnie. To potężne, ale relatywnie kosztowne
narzędzie, którego nie warto stosować bez realnej potrzeby.

</details>

<details>
<summary>14. Czym są Hot Reload i Hot Restart?</summary>

#### Flutter

Hot Reload i Hot Restart to dwa mechanizmy szybkiego restartu aplikacji podczas
developmentu.

#### Hot Reload:

- Wprowadza zmiany w kodzie niemal natychmiast.
- Zachowuje aktualny stan aplikacji.
- Najlepiej nadaje się do zmian w UI, stylach i logice `build()`.

#### Hot Restart:

- Restartuje Dart isolate.
- Resetuje aktualny stan aplikacji.
- Ponownie wykonuje `main()`.
- Jest potrzebny, gdy Hot Reload już nie wystarcza.

#### Różnica:

| Kryterium        | Hot Reload                   | Hot Restart                                  |
| ---------------- | ---------------------------- | -------------------------------------------- |
| Szybkość         | Szybszy                      | Wolniejszy                                   |
| Zachowanie stanu | Tak                          | Nie                                          |
| Wywołanie `main()` | Nie                        | Tak                                          |
| Typowe scenariusze | Zmiany UI i drobnej logiki | Zmiany inicjalizacji lub globalnego stanu    |

#### Ważne:

Nie wszystkie zmiany da się poprawnie zastosować przez Hot Reload. Na przykład
zmiany w initialization flow lub niektórych konstrukcjach static mogą wymagać Hot
Restart.

</details>

<details>
<summary>15. Jakie tryby builda istnieją w Flutterze (Debug, Profile, Release)?</summary>

#### Flutter

W Flutterze są trzy główne tryby builda, każdy ma swoje przeznaczenie.

#### 1. Debug

- Używany podczas developmentu.
- Wspiera Hot Reload.
- Ma dodatkowe checki, assertions i dev tooling.
- Nie nadaje się do oceny realnej wydajności.

#### 2. Profile

- Używany do analizy wydajności.
- Bliższy zachowaniu production.
- Pozwala używać profilowania CPU, GPU, memory i frame rendering.

#### 3. Release

- Używany na production.
- Maksymalnie zoptymalizowany.
- Bez narzędzi debug, assertions i dev overhead.

#### Kiedy używać którego trybu:

1. **Debug** - codzienny development.
2. **Profile** - performance tuning.
3. **Release** - release do store lub production distribution.

</details>

<details>
<summary>16. Czym jest `MaterialApp`?</summary>

#### Flutter

`MaterialApp` to root widget dla aplikacji, które używają Material Design.

#### Co zapewnia:

1. **Nawigację**
2. **Motyw aplikacji**
3. **Lokalizację**
4. **Route’y**
5. **Bazową konfigurację Material**

#### Przykład:

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

#### Kiedy jest używany:

W większości aplikacji Flutter `MaterialApp` jest punktem wejścia na najwyższym
poziomie drzewa widgetów.

</details>

<details>
<summary>17. Czym jest widget `Scaffold`?</summary>

#### Flutter

`Scaffold` to bazowy layout widget dla ekranów Material Design.

#### Co zwykle zawiera:

1. **`appBar`** - górny pasek.
2. **`body`** - główna zawartość ekranu.
3. **`floatingActionButton`** - pływający action button.
4. **`drawer`** - boczne menu.
5. **`bottomNavigationBar`** - dolna nawigacja.
6. **`snackBar` / `bottomSheet` integration** - interakcja z Material shell.

#### Przykład:

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

#### Rola praktyczna:

`Scaffold` daje standardowy "szkielet" ekranu. Bez niego wiele zachowań Material
trzeba organizować ręcznie.

</details>

<details>
<summary>18. Do czego używa się `SafeArea`?</summary>

#### Flutter

`SafeArea` jest używany po to, aby content nie trafiał pod systemowe elementy
interfejsu.

#### Przed czym chroni:

1. **Status bar**
2. **Notch / Dynamic Island / wycięcia ekranu**
3. **System gestures i dolne safe insets**
4. **Inne obszary systemowe, których content nie powinien przykrywać**

#### Przykład:

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

#### Kiedy jest szczególnie przydatny:

- Na ekranach z custom layoutem.
- Gdy content przylega do krawędzi ekranu.
- Gdy trzeba szybko zapewnić bazowe bezpieczeństwo rozmieszczenia UI.

#### Ważne:

`SafeArea` nie zastępuje przemyślanego layoutu, ale pomaga uniknąć typowych
problemów z nachodzeniem stref systemowych.

</details>

<details>
<summary>19. Czym jest język programowania Dart?</summary>

#### Flutter

Dart to nowoczesny obiektowy język programowania stworzony przez Google, używany
jako główny język do developmentu Flutter.

#### Główne cechy Darta:

1. **Silne typowanie:** Dart wspiera statyczne typowanie, co poprawia
   przewidywalność i bezpieczeństwo kodu.

2. **Kompilacja JIT i AOT:** Pozwala to połączyć szybki development i wydajny
   production build.

3. **Wsparcie asynchroniczności:** `Future`, `Stream`, `async/await` to wbudowane
   części języka.

4. **Wygodna składnia:** Dart jest relatywnie łatwy do nauki dla developerów z
   doświadczeniem w Java, Kotlin, Swift, C# lub JavaScript.

5. **Sound null safety:** Język pomaga zmniejszyć liczbę null-related błędów już
   na etapie kompilacji.

#### Dlaczego Dart jest ważny we Flutterze:

Dart to nie tylko "język obok Fluttera", ale fundamentalna część ekosystemu.
Całe UI, logika biznesowa, stan, asynchroniczność i testy we Flutterze zwykle są
pisane właśnie w Darcie.

</details>

<details>
<summary>20. Czym różnią się parametry pozycyjne i nazwane w Darcie?</summary>

#### Flutter

W Darcie parametry funkcji mogą być **pozycyjne** albo **nazwane**.

#### Parametry pozycyjne:

Są przekazywane według kolejności.

```dart
void printUser(String name, int age) {
  print('$name is $age years old');
}

printUser('Anna', 25);
```

#### Parametry nazwane:

Są przekazywane po nazwie, dzięki czemu wywołanie jest bardziej czytelne.

```dart
void printUser({required String name, required int age}) {
  print('$name is $age years old');
}

printUser(name: 'Anna', age: 25);
```

#### Główne różnice:

1. **Czytelność:** Parametry nazwane lepiej pasują do API z dużą liczbą
   argumentów.

2. **Kolejność przekazania:** Dla pozycyjnych kolejność jest ważna, dla nazwanych
   nie.

3. **Elastyczność:** Parametry nazwane często lepiej się skalują, gdy parametrów
   przybywa.

#### Praktyka we Flutterze:

We Flutterze większość konstruktorów widgetów aktywnie używa właśnie
**parametrów nazwanych**, bo to znacząco poprawia czytelność kodu UI.

</details>

<details>
<summary>21. Jaka jest różnica między `var`, `final` i `const`?</summary>

#### Flutter

`var`, `final` i `const` w Darcie są używane do deklarowania zmiennych, ale mają
różną semantykę.

#### `var`

Typ jest inferowany automatycznie, a wartość można zmieniać.

```dart
var name = 'Flutter';
name = 'Dart';
```

#### `final`

Zmienna może być przypisana tylko raz, ale jej wartość może być znana dopiero
podczas wykonania.

```dart
final currentTime = DateTime.now();
```

#### `const`

Wartość musi być znana na etapie kompilacji.

```dart
const pi = 3.14159;
const appName = 'Flutter App';
```

#### Kluczowa różnica:

1. **`var`** - zwykła zmienna.
2. **`final`** - jednokrotne przypisanie w runtime.
3. **`const`** - compile-time stała.

#### Praktyczny niuans:

W Flutterze warto używać `const` tam, gdzie to możliwe, szczególnie dla
widgetów, bo może to zmniejszyć liczbę zbędnych obiektów i rebuild overhead.

</details>

<details>
<summary>22. Czym są null-aware operatory?</summary>

#### Flutter

Null-aware operatory w Darcie to specjalne operatory do bezpiecznej pracy z
`null`.

#### Główne null-aware operatory:

1. **`?.`** - wywołanie metody albo dostęp do właściwości tylko wtedy, gdy obiekt
   nie jest `null`.
2. **`??`** - zwraca wartość po prawej, jeśli po lewej jest `null`.
3. **`??=`** - przypisuje wartość tylko wtedy, gdy zmienna jest `null`.
4. **`!`** - wymusza informację dla kompilatora, że wartość nie jest `null`.

#### Przykłady:

```dart
String? name;
print(name?.length);

String result = name ?? 'Guest';

name ??= 'Anonymous';
```

#### Operator `!`:

```dart
String? title;
print(title!.length);
```

Tego operatora trzeba używać ostrożnie, bo jeśli wartość będzie `null`, wystąpi
runtime error.

#### Praktyczna korzyść:

Null-aware operatory robią kod krótszym, bezpieczniejszym i usuwają potrzebę
nadmiernych ręcznych checków na `null`.

</details>

<details>
<summary>23. Czym jest sound null safety w Darcie?</summary>

#### Flutter

Sound null safety to mechanizm w Darcie, który pozwala rozdzielać typy nullable i
non-nullable oraz wykrywać część null-related błędów już podczas kompilacji.

#### Główna idea:

Jeśli typ jest zadeklarowany jako non-nullable, nie może zawierać `null`.

```dart
String name = 'Flutter';
String? nullableName;
```

#### Co to daje:

1. **Mniej runtime błędów**
2. **Czytelniejszy kontrakt typów**
3. **Lepszy refaktoring**
4. **Bardziej niezawodny production kod**

#### Jak to czytać:

- `String` - wartość obowiązkowo nie jest `null`
- `String?` - wartość może być `null`

#### Znaczenie praktyczne:

Dla dużych projektów Flutter sound null safety znacząco zmniejsza liczbę bugów
związanych z nieoczekiwanymi wartościami `null` w UI, modelach API i state
management.

</details>

<details>
<summary>24. Czym są `async` i `await`?</summary>

#### Flutter

`async` i `await` w Darcie są używane do wygodnej pracy z asynchronicznym kodem.

#### `async`

Oznacza, że funkcja wykonuje asynchroniczną pracę i zwykle zwraca `Future`.

#### `await`

Pozwala poczekać na wynik asynchronicznej operacji bez zagnieżdżonych callbacków.

#### Przykład:

```dart
Future<void> loadUser() async {
  final user = await fetchUser();
  print(user);
}
```

#### Zalety:

1. **Kod czyta się jak synchroniczny**
2. **Mniej zagnieżdżeń**
3. **Prostsza obsługa błędów przez `try/catch`**

#### Przykład z obsługą błędów:

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
<summary>25. Czym jest `Future`?</summary>

#### Flutter

`Future` w Darcie to obiekt, który reprezentuje wynik asynchronicznej operacji,
dostępny później.

#### Mówiąc prosto:

`Future` to "obietnica" otrzymania jednej wartości albo błędu w przyszłości.

#### Przykład:

```dart
Future<String> fetchUserName() async {
  await Future.delayed(const Duration(seconds: 1));
  return 'Viktor';
}
```

#### Co może zakończyć `Future`:

1. **Udany wynik**
2. **Błąd**

#### Praca z `Future`:

```dart
final name = await fetchUserName();
```

albo

```dart
fetchUserName()
    .then((value) => print(value))
    .catchError((error) => print(error));
```

#### Gdzie jest używany w Flutterze:

- HTTP requesty
- Odczyt plików
- Praca z lokalną bazą
- Inicjalizacja serwisów
- Nawigacja, dialogi, permission flows

</details>

<details>
<summary>26. Czym jest `Stream`?</summary>

#### Flutter

`Stream` to sekwencja asynchronicznych zdarzeń albo wartości, które przychodzą w
czasie.

#### Główna idea:

Jeśli `Future` daje jedną wartość w przyszłości, to `Stream` może dawać wiele
wartości w czasie.

#### Przykład:

```dart
Stream<int> counterStream() async* {
  for (int i = 1; i <= 3; i++) {
    await Future.delayed(const Duration(seconds: 1));
    yield i;
  }
}
```

#### Odbieranie wartości:

```dart
await for (final value in counterStream()) {
  print(value);
}
```

#### Gdzie używa się `Stream`:

1. **WebSocket**
2. **Rozpowszechnianie stanu**
3. **Subskrypcja zmian w bazie danych**
4. **Zdarzenia UI albo systemowe**

#### We Flutterze:

`Stream` często jest używany w BLoC, reaktywnych data flow i w sytuacjach, gdzie
ważne są nie jednorazowe, tylko ciągłe aktualizacje.

</details>

<details>
<summary>27. Jaka jest różnica między `Future` i `Stream`?</summary>

#### Flutter

`Future` i `Stream` oba są używane do asynchroniczności, ale rozwiązują różne
zadania.

#### Główna różnica:

| Kryterium         | `Future`                       | `Stream`                                   |
| ----------------- | ------------------------------ | ------------------------------------------ |
| Liczba wartości   | Jedna wartość albo błąd        | Wiele wartości w czasie                    |
| Zakończenie       | Jeden raz                      | Może trwać długo albo zakończyć się później |
| Typowy scenariusz | HTTP request, jednorazowy odczyt | WebSocket, subskrypcja, live updates     |

#### Przykłady:

- `Future`: załadować profil użytkownika jeden raz.
- `Stream`: słuchać aktualizacji czatu w czasie rzeczywistym.

#### Zasada praktyczna:

Jeśli odpowiedź jest potrzebna jeden raz, zwykle to `Future`. Jeśli potrzebny
jest strumień aktualizacji, zwykle to `Stream`.

</details>

<details>
<summary>28. Czym jest event loop w Darcie?</summary>

#### Flutter

Event loop w Darcie to mechanizm, który zarządza wykonywaniem asynchronicznych
zadań w jednym isolate.

#### Jak to działa:

1. **Kod synchroniczny wykonuje się od razu**
2. **Asynchroniczne zadania trafiają do kolejek**
3. **Event loop bierze zadania po kolei i je wykonuje**

#### Główne kolejki:

1. **Microtask queue** - ma wyższy priorytet.
2. **Event queue** - zwykłe asynchroniczne zdarzenia.

#### Przykład:

```dart
void main() {
  print('1');

  Future(() => print('2'));
  scheduleMicrotask(() => print('3'));

  print('4');
}
```

Wynik będzie:

```text
1
4
3
2
```

#### Dlaczego to ważne:

Zrozumienie event loop pomaga poprawnie pracować z `Future`, `Stream`,
microtaskami, UI responsiveness i unikać nieoczekiwanej kolejności wykonania
kodu.

</details>

<details>
<summary>29. Czym są mixins w Darcie?</summary>

#### Flutter

Mixins w Darcie to mechanizm ponownego użycia kodu między klasami bez klasycznego
wielokrotnego dziedziczenia.

#### Do czego są używane:

1. **Ponowne użycie zachowania**
2. **Dodanie wspólnej logiki kilku klasom**
3. **Kompozycja możliwości bez sztywnej hierarchii**

#### Przykład:

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

#### We Flutterze mixins często spotkasz:

- `SingleTickerProviderStateMixin`
- `TickerProviderStateMixin`
- `AutomaticKeepAliveClientMixin`

#### Sens praktyczny:

Mixins są przydatne, gdy trzeba podzielić się zachowaniem między kilkoma klasami,
ale to zachowanie nie powinno być osobną klasą bazową.

</details>

<details>
<summary>30. Czym są extension methods?</summary>

#### Flutter

Extension methods w Darcie pozwalają dodawać nowe metody albo gettery do
istniejących typów bez zmiany ich kodu źródłowego.

#### Przykład:

```dart
extension StringX on String {
  bool get isEmail => contains('@');
}
```

Teraz można pisać:

```dart
final result = 'test@example.com'.isEmail;
```

#### Do czego to przydatne:

1. **Poprawa czytelności**
2. **Przeniesienie utility logiki bliżej typu**
3. **Usunięcie zbędnych helper klas**

#### Typowe przykłady we Flutterze:

- Extensions dla `BuildContext`
- Extensions dla `String`, `DateTime`, `num`
- Extensions dla motywu, odstępów, lokalizacji

#### Ważne:

Extension methods poprawiają API kodu, ale nie warto ich nadużywać. Jeśli
extension zaczyna ukrywać złożoną logikę biznesową, zwykle pogarsza to
przewidywalność kodu.

</details>

<details>
<summary>31. Czym jest `typedef` w Darcie?</summary>

#### Flutter

`typedef` w Darcie jest używany do tworzenia aliasów typów, najczęściej dla
funkcji.

#### Przykład:

```dart
typedef OnUserTap = void Function(String userId);
```

Teraz tego typu można użyć tak:

```dart
class UserTile {
  final OnUserTap onTap;

  UserTile({required this.onTap});
}
```

#### Do czego to potrzebne:

1. **Poprawia czytelność API**
2. **Dodaje semantyczne znaczenie typom funkcyjnym**
3. **Upraszcza ponowne użycie tych samych sygnatur**

#### Gdzie to jest przydatne we Flutterze:

- Callbacks w widgetach
- DI i service contracts
- State management APIs
- Stream/listener contracts

</details>

<details>
<summary>32. Czym jest factory constructor?</summary>

#### Flutter

Factory constructor w Darcie to konstruktor, który nie musi tworzyć nowej
instancji klasy przy każdym wywołaniu.

#### Główne możliwości:

1. **Może zwracać cachowany obiekt**
2. **Może zwracać instancję podklasy**
3. **Może zawierać dodatkową logikę przed utworzeniem obiektu**

#### Przykład:

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

#### Co tu się dzieje:

Zamiast tworzyć nowy `Logger` za każdym razem, factory constructor zwraca już
istniejącą instancję dla tego samego `name`.

#### Gdzie jest często używany:

- Scenariusze podobne do Singleton
- Parsowanie modeli
- Abstrakcje, gdzie potrzebna jest kontrola tworzenia instancji

#### Ważne:

Factory constructor różni się od zwykłego tym, że nie ma bezpośredniego dostępu
do `this`, bo obiekt może jeszcze nie być utworzony.

</details>

<details>
<summary>33. Jak działa system layoutu w Flutterze?</summary>

#### Flutter

System layoutu w Flutterze działa według zasady **constraints go down, sizes go
up, parent sets position**.

#### Jak to wygląda w praktyce:

1. **Widget rodzica przekazuje constraints w dół**
2. **Widget potomny wybiera swój rozmiar w granicach tych constraints**
3. **Widget rodzica określa pozycję elementu potomnego**

#### Główna idea:

Flutter nie używa systemu XML-layout jak Android View hierarchy. Zamiast tego
każdy widget uczestniczy w jasnym modelu obliczania rozmiaru i pozycji.

#### Dlaczego to ważne:

- Pomaga rozumieć błędy typu overflow.
- Daje możliwość przewidywania zachowania `Row`, `Column`, `Expanded`,
  `Flexible`.
- Jest krytyczne dla budowy adaptacyjnych interfejsów.

#### Zasada praktyczna:

Jeśli layout się "psuje", prawie zawsze trzeba patrzeć na constraints, które
widget dostaje od swojego parent.

</details>

<details>
<summary>34. Jakie główne widgety są używane do budowy layoutów?</summary>

#### Flutter

W Flutterze do budowy layoutów najczęściej używa się bazowych layout widgetów, z
których składa się prawie cały interfejs.

#### Główne layout widgety:

1. **`Row`** - poziome rozmieszczenie elementów
2. **`Column`** - pionowe rozmieszczenie elementów
3. **`Container`** - uniwersalny widget-opakowanie
4. **`SizedBox`** - stały rozmiar albo odstęp
5. **`Expanded`** - zajmowanie dostępnej przestrzeni
6. **`Flexible`** - elastyczne użycie przestrzeni
7. **`Stack`** - nakładanie elementów jeden na drugi
8. **`Padding`** - wewnętrzne odstępy
9. **`Align` / `Center`** - wyrównanie
10. **`ListView`** - scrollowalne listy
11. **`Wrap`** - przenoszenie elementów do nowego wiersza
12. **`Scaffold`** - bazowa struktura ekranu

#### Sens praktyczny:

Na większości ekranów layout Fluttera buduje się nie jednym "dużym layoutem",
tylko kombinacją prostych widgetów.

</details>

<details>
<summary>35. Jaka jest różnica między `Row` i `Column`?</summary>

#### Flutter

`Row` i `Column` to bazowe flex-widgety we Flutterze, ale działają w różnych
kierunkach.

#### `Row`

Rozmieszcza elementy potomne **poziomo**.

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

Rozmieszcza elementy potomne **pionowo**.

```dart
Column(
  children: const [
    Text('A'),
    Text('B'),
    Text('C'),
  ],
)
```

#### Główna różnica:

1. **`Row`** działa na osi poziomej
2. **`Column`** działa na osi pionowej

#### Ważne:

I `Row`, i `Column` mogą powodować overflow, jeśli ich elementy potomne nie
mieszczą się w dostępnej przestrzeni.

</details>

<details>
<summary>36. Czym są `mainAxisAlignment` i `crossAxisAlignment`?</summary>

#### Flutter

`mainAxisAlignment` i `crossAxisAlignment` to parametry wyrównania we
flex-widgetach, takich jak `Row` i `Column`.

#### Główna logika:

1. **`mainAxisAlignment`** steruje wyrównaniem wzdłuż głównej osi
2. **`crossAxisAlignment`** steruje wyrównaniem wzdłuż osi poprzecznej

#### Dla `Row`:

- Main axis = pozioma
- Cross axis = pionowa

#### Dla `Column`:

- Main axis = pionowa
- Cross axis = pozioma

#### Przykład:

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

#### Popularne wartości:

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
<summary>37. Czym jest widget `Container`?</summary>

#### Flutter

`Container` to uniwersalny widget-opakowanie, który pozwala ustawiać rozmiar,
odstępy, wyrównanie, dekorację i inne właściwości layoutu.

#### Co może robić:

1. **Ustawiać `width` i `height`**
2. **Dodawać `padding` i `margin`**
3. **Stosować `decoration`**
4. **Wyrównywać element potomny**
5. **Kolorować tło**

#### Przykład:

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

#### Ważne:

`Container` jest wygodny, ale nie zawsze optymalny jako "widget do wszystkiego".
Jeśli potrzebna jest tylko jedna prosta funkcja, często lepiej użyć
wyspecjalizowanego widgetu, na przykład `Padding`, `ColoredBox`, `SizedBox` albo
`Align`.

</details>

<details>
<summary>38. Czym jest widget `SizedBox`?</summary>

#### Flutter

`SizedBox` to widget, który ustawia stały rozmiar elementu potomnego albo jest
używany jako prosty spacer.

#### Główne scenariusze:

1. **Stała szerokość albo wysokość**
2. **Pusty odstęp między elementami**
3. **Ograniczenie rozmiaru widgetu potomnego**

#### Przykład:

```dart
const SizedBox(height: 16)
```

albo

```dart
SizedBox(
  width: 200,
  child: ElevatedButton(
    onPressed: () {},
    child: const Text('Submit'),
  ),
)
```

#### Praktyczna wskazówka:

Dla prostych odstępów między elementami `SizedBox` jest zwykle bardziej czytelny
i lżejszy niż `Container`.

</details>

<details>
<summary>39. Czym jest widget `Expanded`?</summary>

#### Flutter

`Expanded` to widget, który zmusza element potomny do zajęcia całej dostępnej
wolnej przestrzeni wewnątrz `Row`, `Column` albo `Flex`.

#### Jak działa:

`Expanded` mówi Flutterowi: "daj temu elementowi tyle wolnego miejsca, ile
możliwe".

#### Przykład:

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

#### Dodatkowo:

Można użyć `flex`, żeby kontrolować proporcje.

```dart
Expanded(
  flex: 2,
  child: Container(color: Colors.red),
)
```

#### Ważne:

`Expanded` działa tylko wewnątrz widgetów opartych o `Flex`: `Row`, `Column`,
`Flex`.

</details>

<details>
<summary>40. Czym jest widget `Flexible`?</summary>

#### Flutter

`Flexible` to widget do elastycznego podziału przestrzeni wewnątrz `Row`,
`Column` albo `Flex`.

#### Różnica względem `Expanded`:

- `Expanded` zmusza element do zajęcia całej dostępnej przestrzeni.
- `Flexible` pozwala elementowi zajmować przestrzeń bardziej elastycznie.

#### Przykład:

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

#### Sens praktyczny:

`Flexible` jest przydatny, gdy element ma się dostosować do przestrzeni, ale nie
musi maksymalnie się rozciągać.

</details>

<details>
<summary>41. Czym jest widget `Spacer`?</summary>

#### Flutter

`Spacer` to specjalny flex-widget, który zajmuje wolną przestrzeń między innymi
elementami.

#### Przykład:

```dart
Row(
  children: const [
    Text('Left'),
    Spacer(),
    Text('Right'),
  ],
)
```

#### Do czego jest używany:

1. **Rozpychanie elementów**
2. **Budowa adaptacyjnej przestrzeni w `Row` albo `Column`**
3. **Poprawa czytelności kodu zamiast ręcznych wyliczeń odstępów**

#### Ważne:

`Spacer` faktycznie działa jak `Expanded` z pustym elementem potomnym.

</details>

<details>
<summary>42. Czym jest widget `Stack`?</summary>

#### Flutter

`Stack` to layout-widget, który pozwala umieszczać elementy jeden na drugim.

#### Kiedy jest używany:

1. **Interfejsy overlay**
2. **Badge na obrazkach**
3. **Przyciski nad contentem**
4. **Złożone kompozycje UI**

#### Przykład:

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

#### Ważne:

W `Stack` kolejność elementów potomnych ma znaczenie: późniejsze elementy są
rysowane nad wcześniejszymi.

</details>

<details>
<summary>43. Czym jest `Positioned`?</summary>

#### Flutter

`Positioned` to widget używany wewnątrz `Stack` do precyzyjnego pozycjonowania
elementu potomnego.

#### Co można ustawiać:

1. **`top`**
2. **`bottom`**
3. **`left`**
4. **`right`**
5. **`width`**
6. **`height`**

#### Przykład:

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

#### Ważne:

`Positioned` działa tylko jako direct child wewnątrz `Stack`.

</details>

<details>
<summary>44. Czym jest `LayoutBuilder`?</summary>

#### Flutter

`LayoutBuilder` to widget, który pozwala budować UI na podstawie constraints
otrzymanych od widgetu rodzica.

#### Kiedy jest przydatny:

1. **Adaptacyjny layout**
2. **Różne zachowanie dla wąskich i szerokich ekranów**
3. **Rozwiązania, gdzie trzeba znać dostępną przestrzeń podczas build**

#### Przykład:

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

#### Sens praktyczny:

`LayoutBuilder` jest szczególnie przydatny wtedy, gdy decyzję trzeba podejmować
nie po rozmiarze całego ekranu, ale po realnej przestrzeni dostępnej dla
konkretnego widgetu.

</details>

<details>
<summary>45. Czym jest `MediaQuery`?</summary>

#### Flutter

`MediaQuery` to mechanizm dostępu do informacji o bieżącym środowisku
wyświetlania: rozmiar ekranu, orientacja, padding, text scale factor i inne
metryki.

#### Co można pobrać przez `MediaQuery`:

1. **Rozmiar ekranu**
2. **Orientację**
3. **Safe area insets**
4. **Ustawienia skali tekstu**

#### Przykład:

```dart
final size = MediaQuery.of(context).size;
final width = size.width;
```

#### Ważne:

`MediaQuery` dobrze pasuje do adaptacji na poziomie ekranu, ale jeśli chodzi o
lokalne constraints konkretnego widgetu, często poprawniej użyć `LayoutBuilder`.

</details>

<details>
<summary>46. Czym jest `SingleChildScrollView`?</summary>

#### Flutter

`SingleChildScrollView` to scroll-widget dla jednego elementu potomnego, który
pozwala przewijać content, jeśli nie mieści się na ekranie.

#### Kiedy jest używany:

1. **Formularze**
2. **Małe ekrany z pionowym contentem**
3. **Content, który zwykle się mieści, ale czasem może overflowować**

#### Przykład:

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

#### Ważne:

Dla dużych list `SingleChildScrollView` nie nadaje się tak dobrze jak
`ListView`, bo renderuje cały content potomny od razu.

</details>

<details>
<summary>47. Czym jest `ListView.builder`?</summary>

#### Flutter

`ListView.builder` to efektywny sposób tworzenia dużych albo dynamicznych list w
Flutterze.

#### Dlaczego jest ważny:

W przeciwieństwie do statycznego `ListView(children: [...])`, `ListView.builder`
tworzy elementy leniwie, w miarę potrzeby.

#### Przykład:

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

#### Zalety:

1. **Lepsza wydajność na dużych listach**
2. **Mniejsze zużycie pamięci**
3. **Wygodna praca z dynamicznymi danymi**

</details>

<details>
<summary>48. Czym jest `AspectRatio`?</summary>

#### Flutter

`AspectRatio` to widget, który zachowuje zadany stosunek szerokości do wysokości.

#### Przykład:

```dart
AspectRatio(
  aspectRatio: 16 / 9,
  child: Container(
    color: Colors.blue,
  ),
)
```

#### Kiedy jest używany:

1. **Obrazy**
2. **Odtwarzacze wideo**
3. **Karty o stałych proporcjach**
4. **Adaptacyjne bloki UI**

#### Sens praktyczny:

`AspectRatio` upraszcza budowanie elementów, które mają wyglądać proporcjonalnie
na różnych ekranach.

</details>

<details>
<summary>49. Czym jest `Visibility`?</summary>

#### Flutter

`Visibility` to widget, który pozwala sterować wyświetlaniem elementu potomnego.

#### Główny scenariusz:

Pokazać albo ukryć element zależnie od warunku.

#### Przykład:

```dart
Visibility(
  visible: isLoading,
  child: const CircularProgressIndicator(),
)
```

#### Co warto wiedzieć:

`Visibility` ma dodatkowe parametry, które pozwalają kontrolować, czy zachować
rozmiar, state, animation i semantic informacje ukrytego elementu.

#### Praktyczny niuans:

Jeśli potrzebny jest prosty warunkowy rendering, czasem czytelniej użyć zwykłego
`if` albo wyrażenia ternary. `Visibility` jest przydatny, gdy trzeba precyzyjniej
sterować zachowaniem ukrytego widgetu.

</details>

<details>
<summary>50. Czym jest state we Flutterze?</summary>

#### Flutter

State we Flutterze to dane, od których zależy to, jak wygląda albo zachowuje się
UI w konkretnym momencie.

#### Mówiąc prosto:

Jeśli wartość się zmienia i przez to interfejs ma się zaktualizować, to właśnie
jest state.

#### Przykłady state:

1. **Wartość licznika**
2. **Tekst w polu input**
3. **Stan ładowania**
4. **Wybrana zakładka**
5. **Lista danych otrzymanych z API**

#### Dlaczego to ważne:

Flutter jest deklaratywnym frameworkiem. To oznacza, że UI opisuje się jako
funkcję od aktualnego state.

#### Sens praktyczny:

Praca z Flutterem w dużej mierze sprowadza się do poprawnej odpowiedzi na
pytanie: "gdzie ma żyć ten state, kto nim zarządza i kto powinien na niego
reagować?"

</details>

<details>
<summary>51. Jaka jest różnica między lokalnym stanem (ephemeral state) a stanem aplikacji (app state)?</summary>

#### Flutter

Różnica między ephemeral state i app state polega na zakresie odpowiedzialności i
czasie życia tych danych.

#### Ephemeral state:

To lokalny stan konkretnego widgetu albo małej części UI.

#### Przykłady:

1. **Aktualna wartość checkboxa**
2. **Stan otwarcia/zamknięcia sekcji**
3. **Aktualny indeks w `PageView`**

#### App state:

To stan, który jest ważny dla znaczącej części aplikacji albo ma żyć dłużej niż
jeden konkretny widget.

#### Przykłady:

1. **Autoryzacja użytkownika**
2. **Motyw aplikacji**
3. **Koszyk w e-commerce**
4. **Profil użytkownika**

#### Główna różnica:

| Kryterium | Ephemeral state              | App state                            |
| --------- | ---------------------------- | ------------------------------------ |
| Zakres    | Jeden widget albo mały blok UI | Kilka ekranów albo cała aplikacja |
| Czas życia | Krótki                      | Dłuższy                              |
| Przykłady | Animation, selection, input  | Auth, cart, settings, user data      |

#### Zasada praktyczna:

Nie warto podnosić lokalnego stanu do poziomu globalnego bez powodu. To tylko
komplikuje architekturę.

</details>

<details>
<summary>52. Jak działa `setState()`?</summary>

#### Flutter

`setState()` to metoda w `StatefulWidget`, która informuje Fluttera, że stan się
zmienił i odpowiednią część UI trzeba przebudować.

#### Jak to działa:

1. **Zmienia się lokalny state**
2. **Ta zmiana jest opakowana w `setState()`**
3. **Flutter oznacza widget jako dirty**
4. **Framework ponownie wywołuje `build()`**

#### Przykład:

```dart
setState(() {
  counter++;
});
```

#### Ważne do zrozumienia:

`setState()` nie "rysuje UI sam". On tylko triggeruje rebuild dla tego obiektu
`State`.

#### Kiedy pasuje:

- Prosty lokalny stan
- Małe interaktywne elementy
- Szybkie prototypy

#### Kiedy nie pasuje:

Jeśli stan jest używany na wielu ekranach albo ma złożony cykl życia, lepiej
zastosować osobne podejście state management.

</details>

<details>
<summary>53. Jakie podejścia do zarządzania stanem są używane w Flutterze?</summary>

#### Flutter

We Flutterze istnieje kilka popularnych podejść do state management. Wybór
zależy od skali projektu, złożoności domeny i wymagań utrzymywalności.

#### Główne podejścia:

1. **`setState()`** - dla prostego lokalnego stanu
2. **`InheritedWidget`** - bazowy mechanizm rozpowszechniania zależności w drzewie
3. **`Provider`** - prosty i popularny wrapper nad `InheritedWidget`
4. **BLoC / Cubit** - podział UI i logiki biznesowej przez strumienie albo state classes
5. **Riverpod** - nowocześniejsze podejście z lepszą testability i dependency graph
6. **Redux** - scentralizowany state store
7. **`ValueNotifier` / `ChangeNotifier`** - lightweight reaktywne modele

#### Podejście praktyczne:

- Dla małego ekranu wystarczy `setState()`
- Dla średnich aplikacji często pasuje `Provider` albo Riverpod
- Dla złożonej logiki biznesowej często wybiera się BLoC albo Riverpod

#### Główna idea:

Nie istnieje "jedyny poprawny" state management. Poprawny wybór to ten, który
robi kod zrozumiałym, przewidywalnym i utrzymywalnym.

</details>

<details>
<summary>54. Czym jest `Provider`?</summary>

#### Flutter

`Provider` to popularna biblioteka do dependency injection i state management we
Flutterze, zbudowana na `InheritedWidget`.

#### Co daje:

1. **Dostęp do obiektów wyżej w drzewie**
2. **Aktualizację UI przy zmianie state**
3. **Prostsze API niż czysty `InheritedWidget`**

#### Przykład:

```dart
ChangeNotifierProvider(
  create: (_) => CounterNotifier(),
  child: const MyApp(),
)
```

Potem w widgetcie:

```dart
final counter = context.watch<CounterNotifier>();
```

#### Dlaczego `Provider` stał się popularny:

- Niski próg wejścia
- Dobrze pasuje do małych i średnich aplikacji
- Prosty dla zespołu, który nie chce złożonej reaktywnej architektury

#### Ograniczenia:

W dużych projektach ze złożonym dependency graph i dużą liczbą stanów `Provider`
może być mniej wygodny niż Riverpod albo BLoC.

</details>

<details>
<summary>55. Czym jest architektura BLoC?</summary>

#### Flutter

BLoC (Business Logic Component) to podejście architektoniczne, w którym logika
biznesowa jest oddzielona od UI i współdziała z nim przez zdarzenia i stany.

#### Główna idea:

1. **UI wysyła event**
2. **BLoC przetwarza logikę**
3. **BLoC zwraca nowy state**
4. **UI reaguje na state**

#### Zalety:

1. **Czytelny podział odpowiedzialności**
2. **Przewidywalny przepływ danych**
3. **Dobra testability**
4. **Wygodne dla złożonej logiki**

#### Typowe elementy:

- `Event`
- `State`
- `Bloc`
- `BlocBuilder`
- `BlocListener`

#### Sens praktyczny:

BLoC dobrze pasuje do średnich i dużych aplikacji, gdzie ważna jest dyscyplina
architektury, oddzielenie logiki domenowej i kontrolowany data flow.

</details>

<details>
<summary>56. Czym jest Riverpod?</summary>

#### Flutter

Riverpod to nowoczesna biblioteka do state management i dependency injection we
Flutterze, stworzona jako ewolucja idei `Provider`.

#### Co daje Riverpod:

1. **Lepszą kontrolę zależności**
2. **Brak sztywnego powiązania z `BuildContext`**
3. **Lepszą testability**
4. **Bezpieczniejsze i bardziej deklaratywne API**

#### Główna idea:

Stan i zależności opisuje się przez providers, a UI albo serwisy subskrybują je
jawnie.

#### Dlaczego często jest wybierany:

- Łatwiej skalować duży kod
- Mniej ukrytej magii drzewa widgetów
- Wygodniej pracować z async state

#### Praktyczna obserwacja:

W nowoczesnych projektach Flutter Riverpod często jest uznawany za jedną z
najmocniejszych opcji dla długoterminowego utrzymania produktu.

</details>

<details>
<summary>57. Czym jest Redux we Flutterze?</summary>

#### Flutter

Redux we Flutterze to podejście do zarządzania stanem z jednym scentralizowanym
store, gdzie stan zmienia się przez actions i reducers.

#### Główne elementy Redux:

1. **Store** - jedno źródło prawdy
2. **Action** - opis intencji zmiany stanu
3. **Reducer** - funkcja, która oblicza nowy state
4. **Middleware** - miejsce dla async logiki i side effects

#### Zalety:

1. **Przewidywalny data flow**
2. **Scentralizowany state**
3. **Przejrzystość zmian**

#### Wady:

1. **Dużo boilerplate**
2. **Może być nadmiarowy dla Flutter UI**
3. **Często przegrywa wygodą z nowocześniejszymi podejściami**

#### Praktyczny wniosek:

Redux ma historyczną wartość i dobrą dyscyplinę, ale w nowoczesnych projektach
Flutter jest używany rzadziej niż Riverpod, Provider albo BLoC.

</details>

<details>
<summary>58. Czym jest `ValueNotifier`?</summary>

#### Flutter

`ValueNotifier<T>` to prosty reaktywny class we Flutterze, który przechowuje jedną
wartość i powiadamia listenerów, gdy ta wartość się zmienia.

#### Przykład:

```dart
final counter = ValueNotifier<int>(0);

counter.value++;
```

#### Do czego jest używany:

1. **Prosty lokalny albo screen-level state**
2. **Minimalistyczne reaktywne scenariusze**
3. **Gdy nie chcesz używać pełnego state management**

#### Z czym współpracuje:

Najczęściej razem z `ValueListenableBuilder`.

```dart
ValueListenableBuilder<int>(
  valueListenable: counter,
  builder: (context, value, child) {
    return Text('$value');
  },
)
```

#### Sens praktyczny:

`ValueNotifier` to dobre lightweight narzędzie, jeśli state jest prosty i nie
wymaga złożonej architektury.

</details>

<details>
<summary>59. Czym jest `InheritedWidget`?</summary>

#### Flutter

`InheritedWidget` to bazowy mechanizm Fluttera do przekazywania danych w dół
drzewa widgetów i aktualizacji zależnych widgetów przy zmianie tych danych.

#### Główna rola:

1. **Rozpowszechnianie wspólnych danych w poddrzewie**
2. **Dostęp do zależności przez `BuildContext`**
3. **Zoptymalizowana aktualizacja tylko subskrybowanych widgetów**

#### Gdzie jest używany:

- `Theme`
- `MediaQuery`
- `Directionality`
- `Provider` i inne biblioteki pod spodem

#### Dlaczego to ważne:

`InheritedWidget` to fundamentalny mechanizm Fluttera. Nawet jeśli zespół nie
pisze go ręcznie, wiele popularnych bibliotek opiera się właśnie na nim.

</details>

<details>
<summary>60. Jaka jest różnica między `Provider` i `InheritedWidget`?</summary>

#### Flutter

`InheritedWidget` to bazowy mechanizm Fluttera, a `Provider` to wygodna
biblioteczna abstrakcja nad nim.

#### Główna różnica:

| Kryterium      | `InheritedWidget`                     | `Provider`                     |
| -------------- | ------------------------------------- | ------------------------------ |
| Poziom         | Niskopoziomowe bazowe API             | High-level abstraction         |
| Wygoda         | Trzeba dużo pisać ręcznie             | Znacznie prostszy w użyciu     |
| Boilerplate    | Więcej                                | Mniej                          |
| Skalowanie     | Niewygodne bezpośrednio dla większości zespołów | Lepsze dla realnych aplikacji |

#### Praktyczny wniosek:

- Jeśli potrzebujesz zrozumienia fundamentów Fluttera, trzeba znać
  `InheritedWidget`
- Jeśli trzeba szybko i wygodnie budować app-level state, częściej używa się
  `Provider`

#### Kluczowa idea:

`Provider` nie zastępuje koncepcji `InheritedWidget`, tylko czyni ją wygodniejszą
w codziennym developmentcie.

</details>

<details>
<summary>61. Jak działa nawigacja w Flutterze?</summary>

#### Flutter

Nawigacja w Flutterze jest zbudowana wokół stosu route’ów (routes). Gdy użytkownik
przechodzi na nowy ekran, nowy route jest dodawany do stosu, a przy powrocie ze
stosu usuwany jest górny route.

#### Główna idea:

1. **Aktualny ekran jest górnym elementem stosu**
2. **Nowe przejście dodaje nowy route**
3. **Powrót usuwa górny route**

#### Jak to wygląda w praktyce:

- Przejście do przodu: `push`
- Powrót wstecz: `pop`

#### Warianty nawigacji:

1. **Imperative navigation** przez `Navigator`
2. **Named routes**
3. **Router API / declarative navigation**
4. **Pakiety typu `go_router` albo `auto_route`**

#### Praktyczny wniosek:

Dla prostych aplikacji często wystarczy bazowy `Navigator`. Dla dużych produktów
z deep links, web navigation i złożonym routingiem częściej wybiera się podejście
router-based.

</details>

<details>
<summary>62. Czym jest `Navigator`?</summary>

#### Flutter

`Navigator` to core mechanizm Fluttera do zarządzania przejściami między
ekranami.

#### Co robi:

1. **Przechowuje stos route’ów**
2. **Dodaje nowe ekrany**
3. **Usuwa aktualne ekrany**
4. **Zwraca wynik do poprzedniego ekranu**

#### Przykład roli `Navigator`:

Można go traktować jak stos stron, gdzie ostatnia otwarta strona jest aktywna.

#### Przykład:

```dart
Navigator.of(context).push(
  MaterialPageRoute(
    builder: (_) => const DetailsPage(),
  ),
);
```

#### Ważne:

`Navigator` jest ściśle powiązany z `BuildContext`, dlatego trzeba go wywoływać z
kontekstu, który ma dostęp do potrzebnego drzewa nawigacji.

</details>

<details>
<summary>63. Co robią metody `Navigator.push()` i `Navigator.pop()`?</summary>

#### Flutter

`Navigator.push()` dodaje nowy ekran do stosu nawigacji, a `Navigator.pop()`
wraca wstecz, usuwając górny ekran ze stosu.

#### `Navigator.push()`

Otwiera nowy route.

```dart
Navigator.push(
  context,
  MaterialPageRoute(
    builder: (_) => const DetailsPage(),
  ),
);
```

#### `Navigator.pop()`

Zamyka aktualny route.

```dart
Navigator.pop(context);
```

#### Dodatkowo:

`pop()` może zwracać wartość:

```dart
Navigator.pop(context, 'success');
```

#### Sens praktyczny:

To bazowe metody nawigacji w większości aplikacji Flutter i jedno z pierwszych
API, które trzeba pewnie znać na rozmowie.

</details>

<details>
<summary>64. Jak przekazywać dane między ekranami w Flutterze?</summary>

#### Flutter

Dane między ekranami w Flutterze najczęściej przekazuje się przez konstruktor
route’u ekranu albo przez wynik, który jest zwracany z `Navigator.pop()`.

#### Przekazanie do przodu przez konstruktor:

```dart
Navigator.push(
  context,
  MaterialPageRoute(
    builder: (_) => DetailsPage(userId: '42'),
  ),
);
```

#### Ekran odbiorca:

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

#### Zwrócenie danych z powrotem:

```dart
final result = await Navigator.push<String>(
  context,
  MaterialPageRoute(
    builder: (_) => const DetailsPage(),
  ),
);
```

I z powrotem:

```dart
Navigator.pop(context, 'done');
```

#### Inne warianty:

1. **Named routes arguments**
2. **Global/app state**
3. **State management przez Provider, Riverpod, BLoC**

#### Zasada praktyczna:

Jednorazowe dane ekran-do-ekranu lepiej przekazywać jawnie przez konstruktor. Nie
warto od razu ciągnąć do tego globalnego state.

</details>

<details>
<summary>65. Czym jest `ModalBottomSheet`?</summary>

#### Flutter

`ModalBottomSheet` to dolny modalny panel, który pojawia się nad aktualnym
contentem i blokuje interakcję z tłem, dopóki nie zostanie zamknięty.

#### Do czego jest używany:

1. **Akcje na contencie**
2. **Wybór opcji**
3. **Filtry**
4. **Formy krótkiej interakcji**

#### Przykład:

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

#### Ważne:

- To właśnie komponent **modal**
- Można go zamknąć gestem albo przez `Navigator.pop(context)`

#### Sens praktyczny:

`ModalBottomSheet` często jest używany w mobile UI zamiast osobnego ekranu albo
dialogu, gdy trzeba dać szybką kontekstową interakcję.

</details>

<details>
<summary>66. Czym jest motyw (`Theme`) we Flutterze?</summary>

#### Flutter

Motyw we Flutterze to scentralizowany zestaw wizualnych ustawień aplikacji:
kolory, typografia, style przycisków, pól input, app bara i innych komponentów.

#### Do czego jest potrzebny:

1. **Jednolity styl wizualny**
2. **Prosta zmiana designu w jednym miejscu**
3. **Wsparcie light/dark mode**
4. **Spójność UI w całej aplikacji**

#### Przykład:

```dart
MaterialApp(
  theme: ThemeData(
    colorScheme: ColorScheme.fromSeed(seedColor: Colors.blue),
    useMaterial3: true,
  ),
  home: const HomePage(),
)
```

#### Dostęp do motywu:

```dart
final theme = Theme.of(context);
```

#### Praktyczny wniosek:

W aplikacjach production motyw jest ważną częścią design system, a nie tylko
zestawem kolorów.

</details>

<details>
<summary>67. Jaka jest różnica między widgetami Material i Cupertino?</summary>

#### Flutter

Material i Cupertino to dwa różne zestawy komponentów UI we Flutterze, które
odpowiadają różnym design system platform.

#### Material:

- Zorientowany na **Google Material Design**
- Częściej używany jako domyślne podejście we Flutterze
- Główne widgety: `MaterialApp`, `Scaffold`, `AppBar`, `ElevatedButton`

#### Cupertino:

- Zorientowany na **Apple Human Interface Guidelines**
- Daje iOS-style wygląd i zachowanie
- Główne widgety: `CupertinoApp`, `CupertinoPageScaffold`, `CupertinoButton`,
  `CupertinoNavigationBar`

#### Główna różnica:

| Kryterium       | Material                    | Cupertino       |
| --------------- | --------------------------- | --------------- |
| Design          | Google Material             | Apple iOS style |
| Komponenty      | Android-first style         | iOS-first style |
| Typowy use case | Cross-platform default UI   | iOS-native feel |

#### Podejście praktyczne:

Wiele zespołów używa Material jako bazy nawet dla aplikacji cross-platform. Ale
jeśli produkt chce maksymalnie natywnego odczucia iOS, wtedy Cupertino staje się
ważny.

</details>

<details>
<summary>68. Jak zrealizować adaptacyjny interfejs we Flutterze?</summary>

#### Flutter

Adaptacyjny interfejs we Flutterze realizuje się przez kombinację responsive
layoutu, elastycznych widgetów i logiki, która uwzględnia rozmiar oraz cechy
ekranu.

#### Główne narzędzia:

1. **`LayoutBuilder`**
2. **`MediaQuery`**
3. **`Expanded` / `Flexible`**
4. **`Wrap`**
5. **`AspectRatio`**
6. **Warunkowy rendering dla różnych breakpointów**

#### Przykład podejścia:

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

#### Praktyczne zasady:

- Nie ustawiać wszystkiego sztywno w pikselach
- Uwzględniać portrait i landscape
- Uwzględniać tablet, foldable, desktop i web
- Wynosić breakpoint logic do czytelnej struktury

#### Praktyczny wniosek:

Adaptacyjność we Flutterze to nie jeden widget, tylko dyscyplina budowania
layoutu tak, aby UI poprawnie skalował się na różnych form factor.

</details>

<details>
<summary>69. Czym jest `FittedBox`?</summary>

#### Flutter

`FittedBox` to widget, który skaluje i pozycjonuje element potomny tak, aby
wpasował się w dostępną przestrzeń zgodnie z wybranym `fit`.

#### Do czego jest używany:

1. **Skalowanie tekstu albo ikon**
2. **Adaptacja contentu do kontenera**
3. **Unikanie overflow w niektórych scenariuszach layoutu**

#### Przykład:

```dart
FittedBox(
  fit: BoxFit.scaleDown,
  child: Text(
    'Very long title',
    style: TextStyle(fontSize: 32),
  ),
)
```

#### Ważne:

`FittedBox` nie "leczy" wszystkich problemów layoutu. Trzeba go stosować wtedy,
gdy realnie potrzebne jest skalowanie contentu, a nie zamiast poprawnego
zarządzania constraints.

#### Sens praktyczny:

To przydatne narzędzie dla edge cases w responsive UI, ale nie podstawa
architektury layoutu.

</details>

<details>
<summary>70. Czym są izolaty (Isolates) we Flutterze?</summary>

#### Flutter

Izolaty (Isolates) w Dart/Flutter to oddzielne jednostki wykonania z własną
pamięcią i własnym event loop.

#### Główna idea:

W przeciwieństwie do klasycznych threads ze współdzieloną pamięcią, isolates nie
dzielą stanu bezpośrednio między sobą.

#### Co to oznacza:

1. **Każdy isolate ma swój heap**
2. **Każdy isolate wykonuje się niezależnie**
3. **Dane nie są współdzielone bezpośrednio między isolate’ami**

#### Dlaczego to ważne:

Takie podejście zmniejsza ryzyko race conditions i problemów ze współdzieloną
pamięcią.

#### Sens praktyczny we Flutterze:

UI zwykle działa w głównym isolate. Ciężkie obliczenia można wynieść do innego
isolate, żeby nie blokować interfejsu.

</details>

<details>
<summary>71. Do czego są używane izolaty?</summary>

#### Flutter

Izolaty są używane do wynoszenia ciężkich albo długotrwałych zadań z głównego
isolate, gdzie działa UI.

#### Typowe scenariusze:

1. **Ciężkie obliczenia**
2. **Parsowanie dużych JSON**
3. **Przetwarzanie plików**
4. **Szyfrowanie albo dekodowanie danych**
5. **CPU-intensive business logic**

#### Dlaczego to potrzebne:

Jeśli wykonywać ciężką synchroniczną pracę w głównym isolate, UI może zacząć
lagować, gubić klatki albo "zamrażać się".

#### Praktyczny wniosek:

Izolaty są potrzebne nie do każdej async operacji, ale właśnie do zadań
CPU-bound. Dla zwykłych HTTP requestów albo I/O najczęściej wystarczą `Future`
i `async/await`.

</details>

<details>
<summary>72. Jak izolaty komunikują się między sobą?</summary>

#### Flutter

Izolaty komunikują się między sobą przez przekazywanie wiadomości, a nie przez
współdzieloną pamięć.

#### Główne mechanizmy:

1. **`SendPort`** - do wysyłania wiadomości
2. **`ReceivePort`** - do odbierania wiadomości

#### Przykład idei:

Jeden isolate wysyła dane do innego isolate w postaci message passing.

#### Ważne:

- isolates nie mogą bezpośrednio zmieniać współdzielonego obiektu
- dane są przekazywane przez serializowane albo transferable wiadomości

#### Sens praktyczny:

Ten model jest bardziej złożony niż zwykłe async wywołania, ale robi równoległe
wykonanie bezpieczniejszym i bardziej przewidywalnym.

</details>

<details>
<summary>73. Jakie typy Streams istnieją w Darcie?</summary>

#### Flutter

W Darcie najczęściej wyróżnia się dwa główne typy streams: **single-subscription**
i **broadcast streams**.

#### 1. Single-subscription stream

Taki stream jest przeznaczony dla jednego listenera.

#### Cechy:

1. **Ma jednego subscribera**
2. **Pasuje do sekwencyjnego strumienia danych**
3. **Często używany dla file I/O albo async data pipelines**

#### 2. Broadcast stream

Taki stream pozwala subskrybować się jednocześnie wielu listenerom.

#### Cechy:

1. **Ma wielu subscriberów**
2. **Pasuje do zdarzeń**
3. **Jest podobny do event bus / signal source**

#### Praktyczny wniosek:

Jeśli źródło danych ma jednego konsumenta, zwykle wystarcza single-subscription
stream. Jeśli trzeba rozsyłać zdarzenia wielu listenerom, używa się broadcast
stream.

</details>

<details>
<summary>74. Czym jest `FutureBuilder`?</summary>

#### Flutter

`FutureBuilder` to Flutter widget, który buduje UI na podstawie stanu `Future`.

#### Do czego jest używany:

1. **Pokazanie ładowania**
2. **Pokazanie udanego wyniku**
3. **Pokazanie błędu**

#### Przykład:

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

#### Co daje `snapshot`:

1. **`connectionState`**
2. **`hasData`**
3. **`hasError`**
4. **`data`**
5. **`error`**

#### Praktyczny niuans:

Nie warto tworzyć `Future` bezpośrednio wewnątrz `build()` bez potrzeby, bo może
uruchamiać się ponownie przy każdym rebuildzie.

</details>

<details>
<summary>75. Czym jest `StreamBuilder`?</summary>

#### Flutter

`StreamBuilder` to Flutter widget, który buduje UI na podstawie wartości, które
przychodzą ze `Stream`.

#### Główna różnica względem `FutureBuilder`:

- `FutureBuilder` pracuje z jednorazowym wynikiem
- `StreamBuilder` pracuje ze strumieniem aktualizacji w czasie

#### Przykład:

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

#### Typowe scenariusze:

1. **WebSocket updates**
2. **Live data**
3. **BLoC state streams**
4. **Reaktywne zdarzenia**

#### Sens praktyczny:

`StreamBuilder` jest wygodny dla reaktywnego UI, ale ważne jest kontrolowanie
cyklu życia streamów, żeby nie dostawać zbędnych subskrypcji albo memory leaks.

</details>

<details>
<summary>76. Jak działają animacje we Flutterze?</summary>

#### Flutter

Animacje we Flutterze działają przez sekwencyjną zmianę wartości w czasie i
przerysowywanie UI na każdej klatce.

#### Główna idea:

1. **Jest wartość początkowa**
2. **Jest wartość końcowa**
3. **Flutter oblicza stany pośrednie**
4. **UI aktualizuje się klatka po klatce**

#### Główne składowe:

1. **`AnimationController`** - steruje czasem animacji
2. **`Tween`** - określa zakres wartości
3. **`CurvedAnimation`** - określa krzywą ruchu
4. **Builder albo Animated widget** - aktualizuje UI

#### Dwa główne podejścia:

1. **Implicit animations** - proste animacje bez ręcznej kontroli
2. **Explicit animations** - pełna kontrola przez controller

#### Sens praktyczny:

Flutter ma bardzo mocny animation system, bo UI jest rysowany przez własny
rendering engine, a to daje dużą elastyczność dla smooth transitions i custom
motion.

</details>

<details>
<summary>77. Czym jest `AnimationController`?</summary>

#### Flutter

`AnimationController` to obiekt, który zarządza cyklem życia explicit animacji:
startem, zatrzymaniem, reverse i aktualnym postępem.

#### Co robi:

1. **Przechowuje czas trwania animacji**
2. **Porusza się po skali wartości, zwykle od `0.0` do `1.0`**
3. **Pozwala uruchamiać `forward()`, `reverse()`, `repeat()`**

#### Przykład:

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

#### Ważne:

`AnimationController` zwykle trzeba `dispose()`ować, inaczej można dostać wyciek
zasobów.

</details>

<details>
<summary>78. Czym jest Tween-animacja?</summary>

#### Flutter

Tween-animacja to animacja, w której wartość płynnie zmienia się między dwoma
punktami: `begin` i `end`.

#### Główna idea:

Tween opisuje, **jak dokładnie interpolować wartości**.

#### Przykład:

```dart
final animation = Tween<double>(
  begin: 0,
  end: 100,
).animate(controller);
```

#### Co można animować przez Tween:

1. **Liczby**
2. **Kolory**
3. **Odstępy**
4. **Rozmiary**
5. **Alignment**

#### Sens praktyczny:

Tween nie uruchamia animacji sam z siebie. On tylko opisuje przejście wartości, a
to przejście porusza `AnimationController`.

</details>

<details>
<summary>79. Czym jest `vsync`?</summary>

#### Flutter

`vsync` to mechanizm synchronizacji animacji z częstotliwością odświeżania
ekranu.

#### Po co jest potrzebny:

1. **Żeby nie liczyć klatek, gdy widget nie jest widoczny**
2. **Żeby zmniejszyć zbędne obciążenie**
3. **Żeby animacje były zsynchronizowane z rendering pipeline**

#### Jak to wygląda:

W `State` często używa się `SingleTickerProviderStateMixin` i przekazuje `this`
do `AnimationController`.

```dart
controller = AnimationController(
  vsync: this,
  duration: const Duration(milliseconds: 300),
);
```

#### Sens praktyczny:

Bez `vsync` animacje mogłyby działać nawet wtedy, gdy nie trzeba ich renderować,
co pogarsza wydajność.

</details>

<details>
<summary>80. Czym jest ticker we Flutterze?</summary>

#### Flutter

Ticker we Flutterze to obiekt, który generuje callback na każdą klatkę animacji.

#### Główna rola:

1. **Powiadamia o każdej frame**
2. **Pozwala przesuwać animację w czasie**
3. **Jest używany wewnątrz `AnimationController`**

#### Mówiąc prosto:

Ticker to "metronom" dla animacji.

#### Sens praktyczny:

Kiedy pracujesz z `AnimationController`, prawie zawsze pośrednio pracujesz też z
tickerem.

</details>

<details>
<summary>81. Czym jest `AnimatedBuilder`?</summary>

#### Flutter

`AnimatedBuilder` to widget, który przebudowuje część UI w odpowiedzi na zmiany
animowanej wartości.

#### Do czego jest potrzebny:

1. **Reagować na `Animation`**
2. **Aktualizować tylko potrzebną część UI**
3. **Budować explicit animations bez zbędnego boilerplate**

#### Przykład:

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

#### Zaleta:

Można przekazać `child`, który nie będzie przebudowywany na każdej klatce.

</details>

<details>
<summary>82. Czym jest `AnimatedContainer`?</summary>

#### Flutter

`AnimatedContainer` to widget dla implicit animation, który automatycznie animuje
zmiany swoich właściwości.

#### Co może animować:

1. **Rozmiar**
2. **Kolor**
3. **Padding**
4. **Margin**
5. **Alignment**
6. **Decoration**

#### Przykład:

```dart
AnimatedContainer(
  duration: const Duration(milliseconds: 300),
  width: isExpanded ? 200 : 100,
  color: isExpanded ? Colors.blue : Colors.red,
)
```

#### Sens praktyczny:

`AnimatedContainer` to jeden z najwygodniejszych sposobów, aby szybko dodać
płynny UI bez ręcznego sterowania controllerami.

</details>

<details>
<summary>83. Jaka jest różnica między implicit i explicit animacjami?</summary>

#### Flutter

Różnica między implicit i explicit animation polega na poziomie kontroli.

#### Implicit animations:

Flutter sam zarządza animacją, gdy zmieniają się właściwości widgetu.

#### Przykłady:

- `AnimatedContainer`
- `AnimatedOpacity`
- `AnimatedAlign`

#### Explicit animations:

Developer sam zarządza animacją przez `AnimationController`.

#### Przykłady:

- `AnimatedBuilder`
- `FadeTransition`
- `ScaleTransition`

#### Główna różnica:

| Kryterium  | Implicit animations   | Explicit animations       |
| ---------- | --------------------- | ------------------------- |
| Kontrola   | Mniejsza              | Pełna                     |
| Złożoność  | Niższa                | Wyższa                    |
| Use case   | Proste UI transitions | Złożone custom scenariusze |

#### Praktyczny wniosek:

Dla prostych animacji lepiej zaczynać od implicit widgets. Dla złożonych motion
scenariuszy i synchronizacji kilku animacji potrzebne są explicit animations.

</details>

<details>
<summary>84. Czym jest architektura Fluttera?</summary>

#### Flutter

Architektura Fluttera składa się z kilku kluczowych warstw: framework, engine,
embedder i platforma.

#### Główne warstwy:

1. **Framework** - widgety, rendering, gestures, animation, foundation
2. **Engine** - rendering, tekst, compositing, Skia/graphics integration
3. **Embedder** - integracja z Android, iOS, desktop albo web
4. **Platform** - natywny OS i jego API

#### Główna idea:

Flutter nie tylko opakowuje natywne komponenty UI, ale buduje własny UI stack od
góry do dołu.

#### Sens praktyczny:

Właśnie przez tę architekturę Flutter daje wysoką spójność UI między platformami,
ale czasem wymaga osobnej integracji z natywnym kodem.

</details>

<details>
<summary>85. Czym jest rendering pipeline we Flutterze?</summary>

#### Flutter

Rendering pipeline we Flutterze to sekwencja etapów, przez które przechodzi UI od
zmiany state do wyświetlenia klatki na ekranie.

#### Uproszczony pipeline wygląda tak:

1. **State change**
2. **Build**
3. **Layout**
4. **Paint**
5. **Compositing**
6. **Rasterization**

#### Co to oznacza:

- `build` tworzy widget tree
- `layout` liczy rozmiary i pozycje
- `paint` rysuje wynik wizualny
- engine zamienia to w klatkę

#### Sens praktyczny:

Zrozumienie rendering pipeline pomaga debugować jank, zbędne rebuildy,
przemalowania i problemy wydajności.

</details>

<details>
<summary>86. Czym są Widgets, Elements i RenderObjects?</summary>

#### Flutter

To trzy kluczowe poziomy modelu UI Fluttera.

#### Widgets

Widgets to immutable konfiguracje UI.

#### Elements

Elements to "żywe" powiązania między widget tree i render tree.

#### RenderObjects

RenderObjects odpowiadają za layout, paint i low-level rendering.

#### Mówiąc prosto:

1. **Widget** - co chcemy pokazać
2. **Element** - powiązanie i cykl życia w drzewie
3. **RenderObject** - jak to realnie jest mierzone i rysowane

#### Sens praktyczny:

Ten model wyjaśnia, dlaczego Flutter może efektywnie aktualizować UI, nie
przebudowując wszystkiego od nowa na niskim poziomie.

</details>

<details>
<summary>87. Czym jest `FlutterEngine`?</summary>

#### Flutter

`FlutterEngine` to niskopoziomowa część Fluttera, która odpowiada za wykonywanie
kodu Dart i renderowanie klatek.

#### Co wchodzi w jego odpowiedzialność:

1. **Dart runtime**
2. **Rendering**
3. **Text layout**
4. **Compositing**
5. **Platform interaction na niskim poziomie**

#### Sens praktyczny:

Framework daje wygodne API dla widgetów, a engine odpowiada za to, żeby to
faktycznie działało na ekranie urządzenia.

</details>

<details>
<summary>88. Czym jest `WidgetsBinding`?</summary>

#### Flutter

`WidgetsBinding` to warstwa binding, która łączy Flutter framework z engine i
koordynuje cykl życia aplikacji na poziomie widgetów.

#### Do czego jest potrzebny:

1. **Inicjalizacja frameworka**
2. **Praca z frame callbacks**
3. **Dostęp do binding lifecycle**
4. **Koordynacja między framework i engine**

#### Przykład:

```dart
WidgetsFlutterBinding.ensureInitialized();
```

#### Sens praktyczny:

To jeden z centralnych mechanizmów Flutter runtime, nawet jeśli w typowym kodzie
developer widzi go tylko pośrednio.

</details>

<details>
<summary>89. Czym jest `WidgetsBindingObserver`?</summary>

#### Flutter

`WidgetsBindingObserver` to interfejs, który pozwala słuchać zmian cyklu życia
aplikacji i innych framework events.

#### Do czego jest używany:

1. **Śledzenie `AppLifecycleState`**
2. **Reakcja na `resumed`, `paused`, `inactive`, `detached`**
3. **Obsługa platform-level zmian**

#### Przykład use case:

- zatrzymać wideo, gdy aplikacja idzie w background
- odświeżyć dane, gdy aplikacja wraca do foreground

#### Sens praktyczny:

To ważne narzędzie dla cyklu życia, szczególnie w aplikacjach z mediami,
analityką, połączeniami socket albo background-sensitive logiką.

</details>

<details>
<summary>90. Czym są platform channels?</summary>

#### Flutter

Platform channels to mechanizm interakcji między kodem Flutter w Dart i natywnym
kodem platformy, takim jak Kotlin/Java na Android albo Swift/Objective-C na iOS.

#### Do czego są potrzebne:

1. **Dostęp do natywnych API**
2. **Praca z platformowymi SDK**
3. **Integracja z funkcjonalnością, której we Flutterze nie ma bezpośrednio**

#### Główne typy:

1. **`MethodChannel`**
2. **`EventChannel`**
3. **`BasicMessageChannel`**

#### Sens praktyczny:

Platform channels są potrzebne wtedy, gdy aplikacja Flutter wychodzi poza czyste
UI i ma współdziałać z natywnymi możliwościami urządzenia albo zewnętrznymi SDK.

</details>

<details>
<summary>91. Czym jest tree shaking?</summary>

#### Flutter

Tree shaking to proces usuwania nieużywanego kodu z finalnego builda.

#### Główna idea:

Jeśli określony kod nie jest używany, kompilator albo build system nie włącza go
do release builda.

#### Po co jest potrzebny:

1. **Mniejszy rozmiar aplikacji**
2. **Szybsze ładowanie**
3. **Mniej zbędnego kodu na production**

#### Sens praktyczny we Flutterze:

Tree shaking jest szczególnie ważny dla release buildów, bo pomaga zmniejszyć
rozmiar artefaktów i poprawić efektywność dostarczania aplikacji.

</details>

<details>
<summary>92. Jak optymalizować wydajność aplikacji Flutter?</summary>

#### Flutter

Optymalizacja wydajności we Flutterze sprowadza się do zmniejszenia zbędnych
rebuildów, repaintów, kosztownych obliczeń na UI isolate i nadmiernego zużycia
pamięci.

#### Główne kierunki optymalizacji:

1. **Zmniejszać liczbę niepotrzebnych rebuildów**
2. **Nie wykonywać ciężkich CPU-bound zadań w głównym isolate**
3. **Używać leniwych list**
4. **Używać `const`, gdzie to możliwe**
5. **Optymalizować obrazy i zasoby**
6. **Profilować aplikację w profile mode**

#### Praktyczne narzędzia:

- Flutter DevTools
- Performance overlay
- Timeline profiling
- Memory profiler

#### Praktyczny wniosek:

Wydajności we Flutterze nie trzeba "zgadywać", tylko mierzyć. Dobra optymalizacja
prawie zawsze zaczyna się od profilowania, a nie od losowych zmian.

</details>

<details>
<summary>93. Jak zmniejszyć liczbę przebudów widgetów?</summary>

#### Flutter

Żeby zmniejszyć liczbę rebuildów, trzeba lokalizować state i przebudowywać tylko
te części drzewa, które faktycznie zależą od zmian.

#### Główne podejścia:

1. **Wynosić UI do mniejszych widgetów**
2. **Używać `const`**
3. **Lokalizować state jak najniżej**
4. **Nie słuchać zbędnych globalnych stanów**
5. **Używać selector podejść (`select`, selectors, derived state)**

#### Praktyczny przykład myślenia:

Jeśli zmienia się tylko badge w headerze, nie trzeba przebudowywać całego ekranu.

#### Ważne:

Sam rebuild nie zawsze jest problemem. Problem pojawia się wtedy, gdy rebuild
jest kosztowny albo dzieje się zbyt często.

</details>

<details>
<summary>94. Czym jest `RepaintBoundary`?</summary>

#### Flutter

`RepaintBoundary` to widget, który oddziela część render tree do osobnego obszaru
przemalowywania.

#### Po co jest potrzebny:

1. **Żeby nie przemalowywać całego ekranu**
2. **Żeby izolować expensive paint obszary**
3. **Żeby poprawić wydajność w złożonym UI**

#### Główna idea:

Jeśli jedna część drzewa często się zmienia, a inna nie, `RepaintBoundary` może
pomóc zmniejszyć zbędne repainty.

#### Praktyczny niuans:

Nie warto dodawać go wszędzie bezmyślnie. Jak każda optymalizacja, ma sens tam,
gdzie profilowanie pokazało realny problem repaintu.

</details>

<details>
<summary>95. Jak zmniejszyć rozmiar aplikacji Flutter?</summary>

#### Flutter

Rozmiar aplikacji Flutter zmniejsza się przez optymalizację zależności, zasobów i
konfiguracji release builda.

#### Główne podejścia:

1. **Usuwać niepotrzebne pakiety**
2. **Optymalizować assets i obrazy**
3. **Używać tree shaking**
4. **Nie ciągnąć dużych SDK bez potrzeby**
5. **Minimalizować liczbę fontów i locale**

#### Praktyczne kroki:

- budować release, a nie debug
- analizować skład builda
- sprawdzać, które pakiety dodają wagę

#### Praktyczny wniosek:

Rozmiar aplikacji często rośnie nie przez Flutter jako taki, ale przez nadmiarowe
zasoby, SDK i zewnętrzne zależności.

</details>

<details>
<summary>96. Jakie best practices są dla dużych aplikacji Flutter?</summary>

#### Flutter

Dla dużych aplikacji Flutter kluczowe best practices są związane z architekturą,
modułowością, testowalnością i dyscypliną pracy ze stanem.

#### Główne praktyki:

1. **Feature-based albo layered struktura projektu**
2. **Jasny podział UI, domain i data layer**
3. **Przejrzysty state management**
4. **Dependency injection**
5. **Pokrycie testami krytycznej logiki**
6. **Jednolity design system / theme system**
7. **Logowanie, analityka, error reporting**

#### Dodatkowo:

- unikać god-classes
- nie mieszać network, UI i business logic w jednym miejscu
- standaryzować podejścia zespołu

#### Praktyczny wniosek:

Duża aplikacja Flutter prawie zawsze przegrywa bez dyscypliny architektonicznej,
nawet jeśli startowała jako "prosty klient mobilny".

</details>

<details>
<summary>97. Jakie typy testowania istnieją we Flutterze?</summary>

#### Flutter

We Flutterze najczęściej używa się trzech głównych typów testowania.

#### 1. Unit tests

Testują pojedyncze funkcje, serwisy, use cases i business logic.

#### 2. Widget tests

Testują pojedyncze widgety i ich zachowanie w izolowanym środowisku.

#### 3. Integration tests

Testują realne user flows w prawie pełnej aplikacji.

#### Sens praktyczny:

Zdrowa strategia testowa zwykle łączy wszystkie trzy typy, a nie opiera się tylko
na jednym.

</details>

<details>
<summary>98. Czym jest unit testing?</summary>

#### Flutter

Unit testing to testowanie małych izolowanych jednostek kodu bez UI i bez
zależności od realnej aplikacji.

#### Co zwykle się testuje:

1. **Funkcje**
2. **Serwisy**
3. **Use cases**
4. **Parsing**
5. **Walidację**

#### Zalety:

1. **Szybkie wykonanie**
2. **Tani debug**
3. **Dobrze pasuje do logiki biznesowej**

#### Praktyczny wniosek:

Jeśli logikę można przetestować bez Flutter UI, to często jest to najbardziej
stabilny i najtańszy typ testowania.

</details>

<details>
<summary>99. Czym jest widget testing?</summary>

#### Flutter

Widget testing to testowanie widgetów Fluttera w kontrolowanym środowisku bez
uruchamiania pełnej aplikacji na realnym urządzeniu.

#### Co można sprawdzać:

1. **Co widget wyświetla**
2. **Jak reaguje na user interaction**
3. **Czy UI zmienia się po akcji**

#### Przykład scenariusza:

- nacisnąć przycisk
- sprawdzić, że pojawił się nowy tekst

#### Sens praktyczny:

Widget tests dają dobry balans między szybkością i wartością, dlatego we Flutterze
często są uważane za jeden z najprzydatniejszych typów testów.

</details>

<details>
<summary>100. Czym jest integration testing?</summary>

#### Flutter

Integration testing to testowanie pełnych albo prawie pełnych user flows w
aplikacji.

#### Co jest sprawdzane:

1. **Interakcja kilku ekranów**
2. **Nawigacja**
3. **Praca z realnymi serwisami albo ich bliskimi zamiennikami**
4. **Pełne zachowanie scenariusza użytkownika**

#### Przykład:

- login
- otwarcie listy
- przejście do szczegółów
- zakończenie akcji użytkownika

#### Praktyczny minus:

Integration tests są wolniejsze, bardziej kruche i droższe niż unit i widget
tests, dlatego zwykle pokrywają właśnie krytyczne scenariusze.

</details>
