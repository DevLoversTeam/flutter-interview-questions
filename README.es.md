**Read in other languages: [English 🇺🇸](README.en.md),
[Polska 🇵🇱](README.pl.md), [German 🇩🇪](README.de.md), [French 🇫🇷](README.fr.md),
[Spanish 🇪🇸](README.es.md), [Українська 🇺🇦](README.md).**

<h1>
  Flutter <img src="./assets/flutter.svg" width="40" height="40" />
</h1>

<h2>Las preguntas y respuestas más populares de entrevista sobre Flutter</h2>

<details>
<summary>1. ¿Qué es Flutter?</summary>

#### Flutter

Flutter es un toolkit de UI de código abierto de Google para crear aplicaciones
multiplataforma desde una única base de código.

#### Características principales de Flutter:

1. **Multiplataforma:** Permite crear aplicaciones para iOS, Android, Web,
   Windows, macOS y Linux.

2. **Motor de renderizado propio:** Flutter dibuja la interfaz por sí mismo y no
   usa principalmente widgets OEM nativos como base de la UI.

3. **Enfoque basado en widgets:** En Flutter casi todo son widgets: pantalla,
   texto, espacios, botones, animaciones.

4. **Alta velocidad de desarrollo:** Hot Reload permite ver rápidamente cambios
   en el código sin reiniciar por completo la aplicación.

5. **Un único lenguaje de desarrollo:** Todo el código cliente normalmente se
   escribe en Dart.

Flutter se usa con frecuencia para desarrollar MVP rápidamente, aplicaciones
móviles de producto y sistemas corporativos internos.

</details>

<details>
<summary>2. ¿Por qué Flutter se elige a menudo para desarrollo móvil?</summary>

#### Flutter

Flutter se elige a menudo por el equilibrio entre velocidad de desarrollo,
calidad de UI y la posibilidad de mantener una sola base de código para varias
plataformas.

#### Razones principales:

1. **Una sola base de código:** Menos duplicación de lógica entre Android e iOS.

2. **Desarrollo rápido:** Hot Reload acelera las iteraciones del equipo.

3. **UI predecible:** Flutter renderiza la interfaz por su cuenta, por eso el
   diseño luce más consistente entre plataformas.

4. **Buen rendimiento:** Para la mayoría de apps de negocio, Flutter ofrece un
   rendimiento suficiente para nivel de producción.

5. **Ecosistema sólido:** Hay muchos paquetes para navegación, estado, HTTP,
   almacenamiento local, analítica y testing.

6. **Comodidad para UI personalizada:** Si el producto tiene muchas pantallas no
   estándar, animaciones o un sistema de diseño complejo, Flutter suele ganar en
   velocidad de implementación.

#### Cuándo es especialmente conveniente:

- Cuando hay que salir rápido en iOS y Android.
- Cuando el equipo es pequeño y es importante reducir costos de mantenimiento.
- Cuando el producto tiene mucha interfaz personalizada.

</details>

<details>
<summary>3. ¿Qué plataformas soporta Flutter?</summary>

#### Flutter

Flutter soporta varias plataformas desde una sola base de código.

#### Plataformas principales:

1. **Android**
2. **iOS**
3. **Web**
4. **Windows**
5. **macOS**
6. **Linux**

#### Además:

- Flutter también se usa para **soluciones embebidas** y dispositivos
  especializados si existe una integración adecuada con el motor.
- En desarrollo comercial, Flutter se usa con mayor frecuencia para **plataformas
  móviles**, pero web y desktop también están soportados oficialmente.

</details>

<details>
<summary>4. ¿Qué es Dart y por qué Flutter usa precisamente este lenguaje?</summary>

#### Flutter

Dart es un lenguaje de programación desarrollado por Google. Flutter usa Dart
como lenguaje principal para escribir UI, lógica de negocio e interacción con el
framework.

#### Por qué Flutter usa Dart:

1. **Compilación rápida durante el desarrollo:** Esto hace posible Hot Reload.

2. **AOT y JIT:** Dart soporta JIT para desarrollo rápido y compilación AOT para
   builds de producción eficientes.

3. **Sintaxis simple:** Dart es fácil de asimilar para desarrolladores con
   experiencia en Java, JavaScript, C#, Kotlin o Swift.

4. **Buen soporte de asincronía:** `Future`, `Stream`, `async/await` encajan de
   forma natural en desarrollo cliente.

5. **Tipado fuerte:** Mejora mantenibilidad, refactorización y estabilidad en
   proyectos grandes.

#### Razón práctica:

Flutter necesita un lenguaje que funcione bien tanto en modo de desarrollo
rápido como en modo de compilación optimizada. Dart cubre ambos escenarios.

</details>

<details>
<summary>5. ¿Cuál es la estructura de un proyecto Flutter?</summary>

#### Flutter

Un proyecto Flutter típico tiene varias carpetas estándar y archivos de
servicio.

#### Estructura básica:

1. **`lib/`** - código principal de la aplicación.
2. **`test/`** - tests unitarios y de widgets.
3. **`android/`** - parte nativa de Android del proyecto.
4. **`ios/`** - parte nativa de iOS del proyecto.
5. **`web/`** - configuración y punto de entrada para web.
6. **`macos/`, `windows/`, `linux/`** - plataformas de escritorio.
7. **`pubspec.yaml`** - dependencias, recursos y metadatos del proyecto.

#### Lo más importante en la práctica:

- En la mayoría de casos, la lógica principal de producto vive en `lib/`.
- Las carpetas de plataforma se modifican cuando se necesitan ajustes nativos,
  permissions, configuración de SDK o platform channels.

#### Ejemplo de estructura lógica dentro de `lib/`:

```text
lib/
  core/
  features/
  shared/
  app/
  main.dart
```

En proyectos de producción suele ser importante no solo conocer la estructura
estándar de Flutter, sino también tener una arquitectura clara basada en
features o por capas.

</details>

<details>
<summary>6. ¿Qué es el archivo `pubspec.yaml` y para qué se usa?</summary>

#### Flutter

`pubspec.yaml` es el archivo principal de configuración de un proyecto
Dart/Flutter.

#### Para qué se usa:

1. **Gestión de dependencias:** Paquetes que usa la aplicación.

2. **Descripción de recursos:** Conexión de assets, fuentes e íconos.

3. **Metadatos del proyecto:** Nombre, versión, descripción, environment constraints.

4. **Configuración de dependencias de desarrollo:** Por ejemplo, `flutter_test`,
   `build_runner`, `flutter_lints`.

#### Ejemplo:

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

#### Importante:

Después de cambiar `pubspec.yaml`, normalmente se ejecuta `flutter pub get` para
traer las nuevas dependencias.

</details>

<details>
<summary>7. ¿Cuál es el rol de la función `main()` en Flutter?</summary>

#### Flutter

`main()` es el punto de entrada de una aplicación Flutter, desde donde comienza
la ejecución del programa.

#### Rol principal:

1. **Inicio de la aplicación:** Normalmente en `main()` se llama a `runApp()`.

2. **Inicialización primaria:** Aquí se pueden inicializar servicios, contenedor
   DI, Firebase, almacenamiento local o configuración del entorno.

3. **Configuración antes de iniciar la UI:** Si antes del arranque se necesita
   `await`, `main()` se puede declarar como `async`.

#### Ejemplo:

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}
```

#### Ejemplo con inicialización:

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
<summary>8. ¿Qué hace la función `runApp()`?</summary>

#### Flutter

`runApp()` inicia una aplicación Flutter y monta el widget raíz pasado en el
árbol de widgets.

#### Qué sucede en la práctica:

1. **Se crea el nodo raíz de la UI:** Desde él comienza todo el árbol de
   widgets.

2. **Flutter inicia el proceso de construcción de la interfaz:** Luego el
   framework llama a `build()` y renderiza la pantalla.

3. **La aplicación pasa a estar controlada por Flutter framework:** Todas las
   siguientes actualizaciones de UI se procesan mediante el sistema de widgets,
   elements y render objects.

#### Ejemplo:

```dart
void main() {
  runApp(const MyApp());
}
```

#### Importante:

- Normalmente en `runApp()` se pasa `MaterialApp`, `CupertinoApp` o un widget
  raíz `App` propio.
- Una llamada repetida a `runApp()` es posible, pero en el ciclo de vida típico
  de la app normalmente se llama una sola vez.

</details>

<details>
<summary>9. ¿Qué son los widgets en Flutter?</summary>

#### Flutter

Los widgets son los bloques básicos de construcción de UI en Flutter. Describen
cómo debe verse una parte de la interfaz y cómo debe comportarse.

#### Ejemplos de lo que son widgets:

1. **Texto:** `Text`
2. **Botón:** `ElevatedButton`
3. **Espaciado:** `Padding`
4. **Layout:** `Column`, `Row`, `Stack`
5. **Pantalla:** `Scaffold`

#### Características de los widgets:

1. **Declaratividad:** Describes la UI como un conjunto de widgets.

2. **Composición:** Una interfaz compleja se construye a partir de widgets
   simples.

3. **Inmutabilidad:** Los widgets por sí mismos son inmutables; los cambios de
   UI se logran reconstruyendo el árbol.

#### Ejemplo:

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
<summary>10. ¿Cuál es la diferencia entre `StatelessWidget` y `StatefulWidget`?</summary>

#### Flutter

La diferencia está en si el widget tiene estado interno mutable que afecta su
representación.

#### `StatelessWidget`:

Se usa para UI que depende solo de parámetros de entrada y no tiene estado
mutable propio.

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

Se usa cuando el widget tiene estado que puede cambiar durante el ciclo de vida.

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

#### Diferencias principales:

1. **Estado:** `StatelessWidget` no tiene mutable state, `StatefulWidget` sí.

2. **Actualización de UI:** En `StatefulWidget` la UI se actualiza mediante
   `setState()` u otros enfoques de state management.

3. **Escenarios de uso:** Elementos estáticos de UI frente a partes de pantalla
   interactivas o dinámicas.

</details>

<details>
<summary>11. ¿Qué es el árbol de widgets (widget tree)?</summary>

#### Flutter

El árbol de widgets es la jerarquía de todos los widgets que forman la interfaz
de una aplicación Flutter.

#### Cómo funciona:

1. **Cada widget puede contener widgets hijos.**

2. **Toda la pantalla se forma como un árbol de elementos anidados.**

3. **Cuando cambia el estado, Flutter reconstruye partes de este árbol.**

#### Ejemplo:

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

En este ejemplo, `MaterialApp` es la raíz; dentro está `Scaffold`, luego
`AppBar`, `Center` y `Text`.

#### Por qué es importante:

- Entender el widget tree ayuda a construir correctamente la UI.
- Es crítico para depurar, optimizar rebuilds y trabajar con el contexto.

</details>

<details>
<summary>12. ¿Qué es `BuildContext`?</summary>

#### Flutter

`BuildContext` es una referencia al lugar del widget dentro del árbol de
widgets.

#### Para qué sirve:

1. **Acceso a dependencias padre:** Por ejemplo, `Theme`, `MediaQuery`,
   `Navigator`, `ScaffoldMessenger`, `Provider`.

2. **Navegación:** A través de `Navigator.of(context)`.

3. **Obtención de ajustes locales del entorno:** Tamaño de pantalla, tema,
   locale y otras inherited dependencies.

#### Ejemplo:

```dart
final theme = Theme.of(context);
final size = MediaQuery.of(context).size;
```

#### Matiz importante:

`BuildContext` debe pertenecer al lugar correcto del árbol. Por ejemplo, si se
llama `ScaffoldMessenger.of(context)` demasiado pronto o con un contexto que no
tiene el ancestro requerido, obtendrás un error.

#### Regla práctica:

El contexto no debe verse como "acceso global", sino como "posición del widget
en el árbol en este momento".

</details>

<details>
<summary>13. ¿Qué es `Key` en Flutter y para qué se necesita?</summary>

#### Flutter

`Key` es un mecanismo de identificación de widgets en el árbol que ayuda a
Flutter a emparejar correctamente widgets antiguos y nuevos durante un rebuild.

#### Para qué se necesitan las `Key`:

1. **Conservar estado al cambiar el orden de elementos.**

2. **Funcionamiento correcto de listas y colecciones dinámicas.**

3. **Acceso a widgets en tests.**

4. **Control de unicidad de elementos en el árbol.**

#### Ejemplo:

```dart
ListView(
  children: const [
    ListTile(key: ValueKey('user_1'), title: Text('User 1')),
    ListTile(key: ValueKey('user_2'), title: Text('User 2')),
  ],
)
```

#### Tipos principales:

1. **`ValueKey`** - cuando hay un valor identificador estable.
2. **`ObjectKey`** - cuando la key se basa en un objeto.
3. **`UniqueKey`** - cuando se necesita unicidad garantizada.
4. **`GlobalKey`** - para acceder al state o context de un widget específico.

#### Importante:

`GlobalKey` debe usarse con cuidado. Es una herramienta potente, pero
relativamente costosa, que no conviene usar sin necesidad real.

</details>

<details>
<summary>14. ¿Qué son Hot Reload y Hot Restart?</summary>

#### Flutter

Hot Reload y Hot Restart son dos mecanismos de reinicio rápido de la aplicación
durante el desarrollo.

#### Hot Reload:

- Aplica cambios de código casi al instante.
- Conserva el estado actual de la aplicación.
- Es ideal para cambios en UI, estilos y lógica de `build()`.

#### Hot Restart:

- Reinicia el isolate de Dart.
- Restablece el estado actual de la aplicación.
- Ejecuta `main()` nuevamente.
- Se usa cuando Hot Reload ya no es suficiente.

#### Diferencia:

| Criterio          | Hot Reload                     | Hot Restart                                    |
| ----------------- | ------------------------------ | ---------------------------------------------- |
| Velocidad         | Más rápido                     | Más lento                                      |
| Conservación state| Sí                             | No                                             |
| Llamada a `main()`| No                             | Sí                                             |
| Escenarios típicos| Cambios de UI y lógica menor   | Cambios de inicialización o estado global      |

#### Importante:

No todos los cambios se pueden aplicar correctamente mediante Hot Reload. Por
ejemplo, cambios en initialization flow o en algunas construcciones static pueden
requerir Hot Restart.

</details>

<details>
<summary>15. ¿Qué modos de compilación existen en Flutter (Debug, Profile, Release)?</summary>

#### Flutter

En Flutter hay tres modos de compilación principales, y cada uno tiene su
propósito.

#### 1. Debug

- Se usa durante el desarrollo.
- Soporta Hot Reload.
- Incluye verificaciones adicionales, assertions y dev tooling.
- No es adecuado para evaluar rendimiento real.

#### 2. Profile

- Se usa para análisis de rendimiento.
- Es más cercano al comportamiento de producción.
- Permite usar profiling de CPU, GPU, memory y frame rendering.

#### 3. Release

- Se usa para production.
- Está máximamente optimizado.
- Sin herramientas de debug, assertions ni dev overhead.

#### Cuándo usar cada modo:

1. **Debug** - desarrollo diario.
2. **Profile** - performance tuning.
3. **Release** - publicación en store o distribución production.

</details>

<details>
<summary>16. ¿Qué es `MaterialApp`?</summary>

#### Flutter

`MaterialApp` es el widget raíz para aplicaciones que usan Material Design.

#### Qué proporciona:

1. **Navegación**
2. **Tema de la aplicación**
3. **Localización**
4. **Rutas**
5. **Configuración base de Material**

#### Ejemplo:

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

#### Cuándo se usa:

En la mayoría de aplicaciones Flutter, `MaterialApp` es el punto de entrada en
el nivel superior del árbol de widgets.

</details>

<details>
<summary>17. ¿Qué es el widget `Scaffold`?</summary>

#### Flutter

`Scaffold` es un widget base de layout para pantallas de Material Design.

#### Qué suele incluir:

1. **`appBar`** - barra superior.
2. **`body`** - contenido principal de la pantalla.
3. **`floatingActionButton`** - botón de acción flotante.
4. **`drawer`** - menú lateral.
5. **`bottomNavigationBar`** - navegación inferior.
6. **`snackBar` / `bottomSheet` integration** - interacción con Material shell.

#### Ejemplo:

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

#### Rol práctico:

`Scaffold` ofrece un "marco" estándar de pantalla. Sin él, muchos
comportamientos de Material tendrían que organizarse manualmente.

</details>

<details>
<summary>18. ¿Para qué se usa `SafeArea`?</summary>

#### Flutter

`SafeArea` se usa para que el contenido no quede debajo de elementos del sistema
de la interfaz.

#### De qué protege:

1. **Barra de estado**
2. **Notch / Dynamic Island / recortes de pantalla**
3. **Gestos del sistema y safe insets inferiores**
4. **Otras áreas del sistema que no conviene cubrir con contenido**

#### Ejemplo:

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

#### Cuándo es especialmente útil:

- En pantallas con layout personalizado.
- Cuando el contenido se pega a los bordes de la pantalla.
- Cuando se necesita garantizar rápidamente seguridad básica de colocación de UI.

#### Importante:

`SafeArea` no reemplaza un layout bien pensado, pero ayuda a evitar problemas
típicos de solapamiento con zonas del sistema.

</details>

<details>
<summary>19. ¿Qué es el lenguaje de programación Dart?</summary>

#### Flutter

Dart es un lenguaje de programación moderno orientado a objetos, desarrollado
por Google, que se usa como lenguaje principal para desarrollo en Flutter.

#### Características principales de Dart:

1. **Tipado fuerte:** Dart soporta tipado estático, lo que mejora la
   previsibilidad y la seguridad del código.

2. **Compilación JIT y AOT:** Permite combinar desarrollo rápido y un build de
   production eficiente.

3. **Soporte de asincronía:** `Future`, `Stream`, `async/await` son partes
   integradas del lenguaje.

4. **Sintaxis cómoda:** Dart es relativamente fácil de aprender para
   desarrolladores con experiencia en Java, Kotlin, Swift, C# o JavaScript.

5. **Sound null safety:** El lenguaje ayuda a reducir errores relacionados con
   `null` ya en etapa de compilación.

#### Por qué Dart es importante en Flutter:

Dart no es simplemente "un lenguaje junto a Flutter", sino una parte
fundamental del ecosistema. Toda la UI, lógica de negocio, estado, asincronía y
tests en Flutter suelen escribirse en Dart.

</details>

<details>
<summary>20. ¿En qué se diferencian los parámetros posicionales y nombrados en Dart?</summary>

#### Flutter

En Dart, los parámetros de funciones pueden ser **posicionales** o **nombrados**.

#### Parámetros posicionales:

Se pasan por orden.

```dart
void printUser(String name, int age) {
  print('$name is $age years old');
}

printUser('Anna', 25);
```

#### Parámetros nombrados:

Se pasan por nombre, por lo que la llamada resulta más legible.

```dart
void printUser({required String name, required int age}) {
  print('$name is $age years old');
}

printUser(name: 'Anna', age: 25);
```

#### Diferencias principales:

1. **Legibilidad:** Los parámetros nombrados encajan mejor para APIs con muchos
   argumentos.

2. **Orden de paso:** En los posicionales el orden importa; en los nombrados, no.

3. **Flexibilidad:** Los parámetros nombrados suelen escalar mejor cuando crece
   la cantidad de parámetros.

#### Práctica en Flutter:

En Flutter, la mayoría de constructores de widgets usan activamente
**parámetros nombrados**, porque mejora de forma significativa la legibilidad del
código de UI.

</details>

<details>
<summary>21. ¿Cuál es la diferencia entre `var`, `final` y `const`?</summary>

#### Flutter

`var`, `final` y `const` en Dart se usan para declarar variables, pero tienen
semánticas diferentes.

#### `var`

El tipo se infiere automáticamente y el valor se puede cambiar.

```dart
var name = 'Flutter';
name = 'Dart';
```

#### `final`

La variable puede asignarse solo una vez, pero su valor puede conocerse solo en
tiempo de ejecución.

```dart
final currentTime = DateTime.now();
```

#### `const`

El valor debe ser conocido en tiempo de compilación.

```dart
const pi = 3.14159;
const appName = 'Flutter App';
```

#### Diferencia clave:

1. **`var`** - variable normal.
2. **`final`** - asignación única en runtime.
3. **`const`** - constante de compile-time.

#### Matiz práctico:

En Flutter conviene usar `const` donde sea posible, especialmente para widgets,
porque puede reducir la cantidad de objetos innecesarios y el rebuild overhead.

</details>

<details>
<summary>22. ¿Qué son los operadores null-aware?</summary>

#### Flutter

Los operadores null-aware en Dart son operadores especiales para trabajar de
forma segura con `null`.

#### Operadores null-aware principales:

1. **`?.`** - llama un método o accede a una propiedad solo si el objeto no es
   `null`.
2. **`??`** - devuelve el valor de la derecha si el de la izquierda es `null`.
3. **`??=`** - asigna valor solo si la variable es `null`.
4. **`!`** - indica al compilador de forma forzada que el valor no es `null`.

#### Ejemplos:

```dart
String? name;
print(name?.length);

String result = name ?? 'Guest';

name ??= 'Anonymous';
```

#### Operador `!`:

```dart
String? title;
print(title!.length);
```

Este operador debe usarse con cuidado, porque si el valor es `null`, se
producirá un runtime error.

#### Utilidad práctica:

Los operadores null-aware hacen el código más corto, más seguro y eliminan la
necesidad de verificaciones manuales excesivas de `null`.

</details>

<details>
<summary>23. ¿Qué es sound null safety en Dart?</summary>

#### Flutter

Sound null safety es un mecanismo de Dart que permite separar tipos nullable y
non-nullable, y detectar parte de los errores relacionados con `null` ya durante
la compilación.

#### Idea principal:

Si un tipo se declara como no-nullable, no puede contener `null`.

```dart
String name = 'Flutter';
String? nullableName;
```

#### Qué aporta:

1. **Menos errores en runtime**
2. **Contrato de tipos más claro**
3. **Mejor refactorización**
4. **Código de producción más confiable**

#### Cómo se interpreta:

- `String` - el valor obligatoriamente no es `null`
- `String?` - el valor puede ser `null`

#### Significado práctico:

Para proyectos Flutter grandes, sound null safety reduce de forma significativa
la cantidad de bugs relacionados con valores `null` inesperados en UI, modelos
API y state management.

</details>

<details>
<summary>24. ¿Qué son `async` y `await`?</summary>

#### Flutter

`async` y `await` en Dart se usan para trabajar cómodamente con código
asíncrono.

#### `async`

Marca que una función realiza trabajo asíncrono y normalmente retorna `Future`.

#### `await`

Permite esperar el resultado de una operación asíncrona sin callbacks anidados.

#### Ejemplo:

```dart
Future<void> loadUser() async {
  final user = await fetchUser();
  print(user);
}
```

#### Ventajas:

1. **El código se lee como síncrono**
2. **Menos anidamiento**
3. **Manejo de errores más simple con `try/catch`**

#### Ejemplo con manejo de errores:

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
<summary>25. ¿Qué es `Future`?</summary>

#### Flutter

`Future` en Dart es un objeto que representa el resultado de una operación
asíncrona que estará disponible más tarde.

#### En palabras simples:

`Future` es una "promesa" de recibir un valor o un error en el futuro.

#### Ejemplo:

```dart
Future<String> fetchUserName() async {
  await Future.delayed(const Duration(seconds: 1));
  return 'Viktor';
}
```

#### Qué puede completar un `Future`:

1. **Resultado exitoso**
2. **Error**

#### Trabajo con `Future`:

```dart
final name = await fetchUserName();
```

o

```dart
fetchUserName()
    .then((value) => print(value))
    .catchError((error) => print(error));
```

#### Dónde se usa en Flutter:

- Solicitudes HTTP
- Lectura de archivos
- Trabajo con base de datos local
- Inicialización de servicios
- Navegación, diálogos, permission flows

</details>

<details>
<summary>26. ¿Qué es `Stream`?</summary>

#### Flutter

`Stream` es una secuencia de eventos o valores asíncronos que llegan con el
tiempo.

#### Idea principal:

Si `Future` entrega un valor en el futuro, `Stream` puede entregar muchos
valores a lo largo del tiempo.

#### Ejemplo:

```dart
Stream<int> counterStream() async* {
  for (int i = 1; i <= 3; i++) {
    await Future.delayed(const Duration(seconds: 1));
    yield i;
  }
}
```

#### Recepción de valores:

```dart
await for (final value in counterStream()) {
  print(value);
}
```

#### Dónde se usan `Stream`:

1. **WebSocket**
2. **Propagación de estado**
3. **Suscripción a cambios en base de datos**
4. **Eventos de UI o del sistema**

#### En Flutter:

`Stream` se usa con frecuencia en BLoC, en flujos de datos reactivos y en casos
donde importan actualizaciones continuas, no únicas.

</details>

<details>
<summary>27. ¿Cuál es la diferencia entre `Future` y `Stream`?</summary>

#### Flutter

`Future` y `Stream` se usan para asincronía, pero resuelven tareas distintas.

#### Diferencia principal:

| Criterio             | `Future`                              | `Stream`                                   |
| -------------------- | ------------------------------------- | ------------------------------------------ |
| Cantidad de valores  | Un valor o un error                   | Muchos valores en el tiempo                |
| Finalización         | Una vez                               | Puede durar mucho o terminar más tarde     |
| Escenario típico     | Solicitud HTTP, lectura única         | WebSocket, suscripción, live updates       |

#### Ejemplos:

- `Future`: cargar el perfil del usuario una sola vez.
- `Stream`: escuchar actualizaciones de chat en tiempo real.

#### Regla práctica:

Si la respuesta se necesita una vez, normalmente es `Future`. Si se necesita un
flujo de actualizaciones, normalmente es `Stream`.

</details>

<details>
<summary>28. ¿Qué es event loop en Dart?</summary>

#### Flutter

El event loop en Dart es el mecanismo que gestiona la ejecución de tareas
asíncronas dentro de un isolate.

#### Cómo funciona:

1. **El código síncrono se ejecuta de inmediato**
2. **Las tareas asíncronas se colocan en colas**
3. **El event loop toma tareas en orden y las ejecuta**

#### Colas principales:

1. **Microtask queue** - tiene prioridad más alta.
2. **Event queue** - eventos asíncronos normales.

#### Ejemplo:

```dart
void main() {
  print('1');

  Future(() => print('2'));
  scheduleMicrotask(() => print('3'));

  print('4');
}
```

El resultado será:

```text
1
4
3
2
```

#### Por qué es importante:

Entender event loop ayuda a trabajar correctamente con `Future`, `Stream`,
microtasks, UI responsiveness y evitar orden inesperado de ejecución.

</details>

<details>
<summary>29. ¿Qué son los mixins en Dart?</summary>

#### Flutter

Los mixins en Dart son un mecanismo para reutilizar código entre clases sin
herencia múltiple clásica.

#### Para qué se usan:

1. **Reutilización de comportamiento**
2. **Agregar lógica común a varias clases**
3. **Composición de capacidades sin jerarquía rígida**

#### Ejemplo:

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

#### En Flutter, mixins frecuentes:

- `SingleTickerProviderStateMixin`
- `TickerProviderStateMixin`
- `AutomaticKeepAliveClientMixin`

#### Sentido práctico:

Los mixins son útiles cuando hay que compartir comportamiento entre varias
clases, pero ese comportamiento no debe ser una clase base separada.

</details>

<details>
<summary>30. ¿Qué son extension methods?</summary>

#### Flutter

Las extension methods en Dart permiten agregar métodos o getters nuevos a tipos
existentes sin cambiar su código fuente.

#### Ejemplo:

```dart
extension StringX on String {
  bool get isEmail => contains('@');
}
```

Ahora se puede escribir:

```dart
final result = 'test@example.com'.isEmail;
```

#### Para qué es útil:

1. **Mejora de legibilidad**
2. **Mover lógica utility más cerca del tipo**
3. **Eliminar helper classes innecesarias**

#### Ejemplos típicos en Flutter:

- Extensions para `BuildContext`
- Extensions para `String`, `DateTime`, `num`
- Extensions para tema, espaciados y localización

#### Importante:

Las extension methods mejoran la API del código, pero no conviene abusar de
ellas. Si una extension empieza a ocultar lógica de negocio compleja, suele
empeorar la previsibilidad del código.

</details>

<details>
<summary>31. ¿Qué es `typedef` en Dart?</summary>

#### Flutter

`typedef` en Dart se usa para crear alias de tipos, con mayor frecuencia para
funciones.

#### Ejemplo:

```dart
typedef OnUserTap = void Function(String userId);
```

Ahora este tipo se puede usar así:

```dart
class UserTile {
  final OnUserTap onTap;

  UserTile({required this.onTap});
}
```

#### Para qué sirve:

1. **Mejora la legibilidad de API**
2. **Añade significado semántico a tipos funcionales**
3. **Simplifica la reutilización de firmas iguales**

#### Dónde es útil en Flutter:

- Callbacks en widgets
- DI y service contracts
- APIs de state management
- Contratos de stream/listener

</details>

<details>
<summary>32. ¿Qué es un factory constructor?</summary>

#### Flutter

Un factory constructor en Dart es un constructor que no necesariamente crea una
nueva instancia de la clase en cada llamada.

#### Capacidades principales:

1. **Puede devolver un objeto cacheado**
2. **Puede devolver una instancia de una subclase**
3. **Puede contener lógica adicional antes de crear el objeto**

#### Ejemplo:

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

#### Qué ocurre aquí:

En vez de crear un `Logger` nuevo cada vez, el factory constructor devuelve la
instancia ya existente para el mismo `name`.

#### Dónde se usa con frecuencia:

- Escenarios tipo Singleton
- Parsing de modelos
- Abstracciones donde se necesita control sobre la creación de instancias

#### Importante:

Un factory constructor se diferencia del constructor normal en que no tiene
acceso directo a `this`, porque el objeto aún puede no estar creado.

</details>

<details>
<summary>33. ¿Cómo funciona el sistema de layout en Flutter?</summary>

#### Flutter

El sistema de layout en Flutter funciona bajo el principio **constraints go
down, sizes go up, parent sets position**.

#### Cómo se ve en la práctica:

1. **El widget padre pasa constraints hacia abajo**
2. **El widget hijo elige su tamaño dentro de esos constraints**
3. **El widget padre define la posición del elemento hijo**

#### Idea principal:

Flutter no usa un sistema XML-layout como Android View hierarchy. En su lugar,
cada widget participa en un modelo claro de cálculo de tamaño y posición.

#### Por qué es importante:

- Ayuda a entender errores de tipo overflow.
- Permite predecir el comportamiento de `Row`, `Column`, `Expanded`, `Flexible`.
- Es crítico para construir interfaces adaptativas.

#### Regla práctica:

Si el layout "se rompe", casi siempre hay que revisar los constraints que el
widget recibe de su parent.

</details>

<details>
<summary>34. ¿Qué widgets principales se usan para construir layouts?</summary>

#### Flutter

En Flutter, para construir layouts se usan con mayor frecuencia widgets base de
layout que forman casi toda la interfaz.

#### Widgets principales de layout:

1. **`Row`** - disposición horizontal de elementos
2. **`Column`** - disposición vertical de elementos
3. **`Container`** - widget contenedor universal
4. **`SizedBox`** - tamaño fijo o espaciado
5. **`Expanded`** - ocupación del espacio disponible
6. **`Flexible`** - uso flexible del espacio
7. **`Stack`** - superposición de elementos
8. **`Padding`** - espaciado interno
9. **`Align` / `Center`** - alineación
10. **`ListView`** - listas desplazables
11. **`Wrap`** - salto de elementos a nueva fila
12. **`Scaffold`** - estructura base de pantalla

#### Sentido práctico:

En la mayoría de pantallas, el layout de Flutter no se construye con un único
"gran layout", sino con la combinación de widgets simples.

</details>

<details>
<summary>35. ¿Cuál es la diferencia entre `Row` y `Column`?</summary>

#### Flutter

`Row` y `Column` son widgets flex básicos en Flutter, pero trabajan en
direcciones distintas.

#### `Row`

Coloca los elementos hijos **horizontalmente**.

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

Coloca los elementos hijos **verticalmente**.

```dart
Column(
  children: const [
    Text('A'),
    Text('B'),
    Text('C'),
  ],
)
```

#### Diferencia principal:

1. **`Row`** trabaja sobre el eje horizontal
2. **`Column`** trabaja sobre el eje vertical

#### Importante:

Tanto `Row` como `Column` pueden producir overflow si sus elementos hijos no
caben en el espacio disponible.

</details>

<details>
<summary>36. ¿Qué son `mainAxisAlignment` y `crossAxisAlignment`?</summary>

#### Flutter

`mainAxisAlignment` y `crossAxisAlignment` son parámetros de alineación en
widgets flex, como `Row` y `Column`.

#### Lógica principal:

1. **`mainAxisAlignment`** controla la alineación a lo largo del eje principal
2. **`crossAxisAlignment`** controla la alineación a lo largo del eje transversal

#### Para `Row`:

- Main axis = horizontal
- Cross axis = vertical

#### Para `Column`:

- Main axis = vertical
- Cross axis = horizontal

#### Ejemplo:

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

#### Valores comunes:

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
<summary>37. ¿Qué es el widget `Container`?</summary>

#### Flutter

`Container` es un widget contenedor universal que permite definir tamaño,
espaciado, alineación, decoración y otras propiedades de layout.

#### Qué puede hacer:

1. **Definir `width` y `height`**
2. **Agregar `padding` y `margin`**
3. **Aplicar `decoration`**
4. **Alinear el elemento hijo**
5. **Pintar el fondo**

#### Ejemplo:

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

#### Importante:

`Container` es cómodo, pero no siempre óptimo como "widget para todo". Si se
necesita una sola función simple, muchas veces conviene usar un widget
especializado como `Padding`, `ColoredBox`, `SizedBox` o `Align`.

</details>

<details>
<summary>38. ¿Qué es el widget `SizedBox`?</summary>

#### Flutter

`SizedBox` es un widget que define un tamaño fijo para un elemento hijo o se usa
como spacer simple.

#### Escenarios principales:

1. **Ancho o alto fijo**
2. **Espacio vacío entre elementos**
3. **Restricción de tamaño del widget hijo**

#### Ejemplo:

```dart
const SizedBox(height: 16)
```

o

```dart
SizedBox(
  width: 200,
  child: ElevatedButton(
    onPressed: () {},
    child: const Text('Submit'),
  ),
)
```

#### Consejo práctico:

Para separaciones simples entre elementos, `SizedBox` suele ser más legible y
ligero que `Container`.

</details>

<details>
<summary>39. ¿Qué es el widget `Expanded`?</summary>

#### Flutter

`Expanded` es un widget que obliga al elemento hijo a ocupar todo el espacio
libre disponible dentro de `Row`, `Column` o `Flex`.

#### Cómo funciona:

`Expanded` le dice a Flutter: "dale a este elemento todo el espacio libre que
sea posible".

#### Ejemplo:

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

#### Además:

Se puede usar `flex` para controlar proporciones.

```dart
Expanded(
  flex: 2,
  child: Container(color: Colors.red),
)
```

#### Importante:

`Expanded` funciona solo dentro de widgets basados en `Flex`: `Row`, `Column`,
`Flex`.

</details>

<details>
<summary>40. ¿Qué es el widget `Flexible`?</summary>

#### Flutter

`Flexible` es un widget para distribución flexible de espacio dentro de `Row`,
`Column` o `Flex`.

#### Diferencia con `Expanded`:

- `Expanded` obliga al elemento a ocupar todo el espacio disponible.
- `Flexible` permite que el elemento ocupe espacio de forma más flexible.

#### Ejemplo:

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

#### Sentido práctico:

`Flexible` es útil cuando el elemento debe adaptarse al espacio, pero no
necesariamente expandirse al máximo.

</details>

<details>
<summary>41. ¿Qué es el widget `Spacer`?</summary>

#### Flutter

`Spacer` es un widget flex especial que ocupa el espacio libre entre otros
elementos.

#### Ejemplo:

```dart
Row(
  children: const [
    Text('Left'),
    Spacer(),
    Text('Right'),
  ],
)
```

#### Para qué se usa:

1. **Separar elementos**
2. **Construir espacio adaptativo en `Row` o `Column`**
3. **Mejorar legibilidad del código en lugar de cálculos manuales de espaciado**

#### Importante:

`Spacer` funciona básicamente como `Expanded` con un hijo vacío.

</details>

<details>
<summary>42. ¿Qué es el widget `Stack`?</summary>

#### Flutter

`Stack` es un widget de layout que permite colocar elementos uno encima de otro.

#### Cuándo se usa:

1. **Interfaces overlay**
2. **Badges sobre imágenes**
3. **Botones sobre contenido**
4. **Composiciones de UI complejas**

#### Ejemplo:

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

#### Importante:

En `Stack`, el orden de los hijos importa: los elementos posteriores se dibujan
encima de los anteriores.

</details>

<details>
<summary>43. ¿Qué es `Positioned`?</summary>

#### Flutter

`Positioned` es un widget que se usa dentro de `Stack` para posicionar con
precisión un elemento hijo.

#### Qué se puede definir:

1. **`top`**
2. **`bottom`**
3. **`left`**
4. **`right`**
5. **`width`**
6. **`height`**

#### Ejemplo:

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

#### Importante:

`Positioned` funciona solo como direct child dentro de `Stack`.

</details>

<details>
<summary>44. ¿Qué es `LayoutBuilder`?</summary>

#### Flutter

`LayoutBuilder` es un widget que permite construir UI basándose en los
constraints recibidos del widget padre.

#### Cuándo es útil:

1. **Layout adaptativo**
2. **Comportamiento distinto para pantallas estrechas y anchas**
3. **Casos donde hay que conocer el espacio disponible durante build**

#### Ejemplo:

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

#### Sentido práctico:

`LayoutBuilder` es especialmente útil cuando la decisión debe tomarse no por el
tamaño de toda la pantalla, sino por el espacio real disponible para un widget
concreto.

</details>

<details>
<summary>45. ¿Qué es `MediaQuery`?</summary>

#### Flutter

`MediaQuery` es un mecanismo para acceder a información del entorno de
visualización actual: tamaño de pantalla, orientación, padding, text scale
factor y otras métricas.

#### Qué se puede obtener con `MediaQuery`:

1. **Tamaño de pantalla**
2. **Orientación**
3. **Safe area insets**
4. **Ajustes de escala de texto**

#### Ejemplo:

```dart
final size = MediaQuery.of(context).size;
final width = size.width;
```

#### Importante:

`MediaQuery` funciona bien para adaptación a nivel de pantalla, pero si se trata
de constraints locales de un widget concreto, a menudo es más correcto usar
`LayoutBuilder`.

</details>

<details>
<summary>46. ¿Qué es `SingleChildScrollView`?</summary>

#### Flutter

`SingleChildScrollView` es un widget de scroll para un único hijo que permite
desplazar contenido si no cabe en la pantalla.

#### Cuándo se usa:

1. **Formularios**
2. **Pantallas pequeñas con contenido vertical**
3. **Contenido que normalmente cabe, pero a veces puede hacer overflow**

#### Ejemplo:

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

#### Importante:

Para listas grandes, `SingleChildScrollView` no encaja tan bien como `ListView`,
porque renderiza todo el contenido hijo de una vez.

</details>

<details>
<summary>47. ¿Qué es `ListView.builder`?</summary>

#### Flutter

`ListView.builder` es una forma eficiente de crear listas grandes o dinámicas en
Flutter.

#### Por qué es importante:

A diferencia de un `ListView(children: [...])` estático, `ListView.builder`
crea elementos de forma lazy, según se necesitan.

#### Ejemplo:

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

#### Ventajas:

1. **Mejor rendimiento en listas grandes**
2. **Menor consumo de memoria**
3. **Trabajo cómodo con datos dinámicos**

</details>

<details>
<summary>48. ¿Qué es `AspectRatio`?</summary>

#### Flutter

`AspectRatio` es un widget que mantiene una relación dada entre ancho y alto.

#### Ejemplo:

```dart
AspectRatio(
  aspectRatio: 16 / 9,
  child: Container(
    color: Colors.blue,
  ),
)
```

#### Cuándo se usa:

1. **Imágenes**
2. **Reproductores de video**
3. **Tarjetas con proporciones fijas**
4. **Bloques de UI adaptativos**

#### Sentido práctico:

`AspectRatio` simplifica la construcción de elementos que deben verse
proporcionales en distintas pantallas.

</details>

<details>
<summary>49. ¿Qué es `Visibility`?</summary>

#### Flutter

`Visibility` es un widget que permite controlar la visualización de un elemento
hijo.

#### Escenario principal:

Mostrar u ocultar un elemento según una condición.

#### Ejemplo:

```dart
Visibility(
  visible: isLoading,
  child: const CircularProgressIndicator(),
)
```

#### Qué es importante saber:

`Visibility` tiene parámetros adicionales que permiten controlar si se conserva
el tamaño, state, animation y semantic information del elemento oculto.

#### Matiz práctico:

Si se necesita renderizado condicional simple, a veces es más legible usar un
`if` normal o una expresión ternaria. `Visibility` es útil cuando se necesita un
control más fino del comportamiento del widget oculto.

</details>

<details>
<summary>50. ¿Qué es state en Flutter?</summary>

#### Flutter

State en Flutter son los datos de los que depende cómo se ve o se comporta la UI
en un momento concreto.

#### En palabras simples:

Si un valor cambia y por eso debe actualizarse la interfaz, eso es state.

#### Ejemplos de state:

1. **Valor de contador**
2. **Texto en un campo de entrada**
3. **Estado de carga**
4. **Tab seleccionado**
5. **Lista de datos recibidos de una API**

#### Por qué es importante:

Flutter es un framework declarativo. Esto significa que la UI se describe como
una función del state actual.

#### Sentido práctico:

Trabajar con Flutter se reduce en gran medida a responder correctamente: "dónde
debe vivir este state, quién lo posee y quién debe reaccionar a él?".

</details>

<details>
<summary>51. ¿Cuál es la diferencia entre estado local (ephemeral state) y estado de aplicación (app state)?</summary>

#### Flutter

La diferencia entre ephemeral state y app state está en el alcance de
responsabilidad y la duración de vida de esos datos.

#### Ephemeral state:

Es el estado local de un widget concreto o de una parte pequeña de la UI.

#### Ejemplos:

1. **Valor actual de un checkbox**
2. **Estado de abrir/cerrar una sección**
3. **Índice actual en `PageView`**

#### App state:

Es el estado que es importante para una parte significativa de la aplicación o
que debe vivir más tiempo que un solo widget.

#### Ejemplos:

1. **Autorización del usuario**
2. **Tema de la aplicación**
3. **Carrito en e-commerce**
4. **Perfil del usuario**

#### Diferencia principal:

| Criterio   | Ephemeral state                 | App state                              |
| ---------- | ------------------------------- | -------------------------------------- |
| Alcance    | Un widget o bloque pequeño de UI| Varias pantallas o toda la aplicación  |
| Duración   | Corta                           | Más larga                              |
| Ejemplos   | Animation, selection, input     | Auth, cart, settings, user data        |

#### Regla práctica:

No conviene elevar estado local al nivel global sin motivo. Eso solo complica la
arquitectura.

</details>

<details>
<summary>52. ¿Cómo funciona `setState()`?</summary>

#### Flutter

`setState()` es un método en `StatefulWidget` que notifica a Flutter que el
estado cambió y que la parte correspondiente de la UI debe reconstruirse.

#### Cómo funciona:

1. **Cambias el state local**
2. **Envuelves ese cambio en `setState()`**
3. **Flutter marca el widget como dirty**
4. **El framework vuelve a llamar a `build()`**

#### Ejemplo:

```dart
setState(() {
  counter++;
});
```

#### Importante entender:

`setState()` no "dibuja UI por sí mismo". Solo dispara un rebuild para ese
objeto `State`.

#### Cuándo encaja:

- Estado local simple
- Elementos interactivos pequeños
- Prototipos rápidos

#### Cuándo no encaja:

Si el estado se usa en muchas pantallas o tiene un ciclo de vida complejo, es
mejor aplicar un enfoque de state management separado.

</details>

<details>
<summary>53. ¿Qué enfoques de gestión de estado se usan en Flutter?</summary>

#### Flutter

En Flutter existen varios enfoques populares para state management. La elección
depende de la escala del proyecto, la complejidad del dominio y los requisitos
de mantenibilidad.

#### Enfoques principales:

1. **`setState()`** - para estado local simple
2. **`InheritedWidget`** - mecanismo base para propagar dependencias en el árbol
3. **`Provider`** - wrapper simple y popular sobre `InheritedWidget`
4. **BLoC / Cubit** - separación de UI y lógica de negocio mediante flujos o classes de estado
5. **Riverpod** - enfoque más moderno con mejor testability y dependency graph
6. **Redux** - store de estado centralizado
7. **`ValueNotifier` / `ChangeNotifier`** - modelos reactivos lightweight

#### Enfoque práctico:

- Para una pantalla pequeña suele bastar `setState()`
- Para apps medianas, a menudo encaja `Provider` o Riverpod
- Para lógica de negocio compleja, se elige con frecuencia BLoC o Riverpod

#### Idea principal:

No existe un state management "único y correcto". La elección correcta es la que
hace el código claro, predecible y mantenible.

</details>

<details>
<summary>54. ¿Qué es `Provider`?</summary>

#### Flutter

`Provider` es una biblioteca popular para dependency injection y state management
en Flutter, construida sobre `InheritedWidget`.

#### Qué ofrece:

1. **Acceso a objetos más arriba en el árbol**
2. **Actualización de UI cuando cambia el state**
3. **API más simple que con `InheritedWidget` puro**

#### Ejemplo:

```dart
ChangeNotifierProvider(
  create: (_) => CounterNotifier(),
  child: const MyApp(),
)
```

Luego, en un widget:

```dart
final counter = context.watch<CounterNotifier>();
```

#### Por qué `Provider` se volvió popular:

- Barrera de entrada baja
- Encaja bien para aplicaciones pequeñas y medianas
- Es simple para equipos que no quieren una arquitectura reactiva compleja

#### Limitaciones:

En proyectos grandes con dependency graph complejo y muchos estados, `Provider`
puede volverse menos cómodo que Riverpod o BLoC.

</details>

<details>
<summary>55. ¿Qué es la arquitectura BLoC?</summary>

#### Flutter

BLoC (Business Logic Component) es un enfoque de arquitectura donde la lógica de
negocio se separa de la UI e interactúa con ella mediante eventos y estados.

#### Idea principal:

1. **La UI envía un event**
2. **BLoC procesa la lógica**
3. **BLoC entrega un state nuevo**
4. **La UI reacciona al state**

#### Ventajas:

1. **Separación clara de responsabilidades**
2. **Flujo de datos predecible**
3. **Buena testability**
4. **Cómodo para lógica compleja**

#### Elementos típicos:

- `Event`
- `State`
- `Bloc`
- `BlocBuilder`
- `BlocListener`

#### Sentido práctico:

BLoC encaja bien para aplicaciones medianas y grandes, donde importan la
disciplina de arquitectura, la separación de lógica de dominio y un data flow
controlado.

</details>

<details>
<summary>56. ¿Qué es Riverpod?</summary>

#### Flutter

Riverpod es una biblioteca moderna para state management y dependency injection
en Flutter, creada como evolución de las ideas de `Provider`.

#### Qué aporta Riverpod:

1. **Mejor control de dependencias**
2. **Ausencia de acoplamiento rígido a `BuildContext`**
3. **Mejor testability**
4. **API más segura y declarativa**

#### Idea principal:

El estado y las dependencias se describen con providers, y la UI o los servicios
se suscriben a ellos de forma explícita.

#### Por qué se elige con frecuencia:

- Es más fácil escalar código grande
- Hay menos magia oculta del árbol de widgets
- Es más cómodo trabajar con async state

#### Observación práctica:

En proyectos Flutter modernos, Riverpod suele considerarse una de las opciones
más sólidas para mantenimiento de producto a largo plazo.

</details>

<details>
<summary>57. ¿Qué es Redux en Flutter?</summary>

#### Flutter

Redux en Flutter es un enfoque de gestión de estado con un store centralizado
único, donde el estado cambia mediante actions y reducers.

#### Elementos principales de Redux:

1. **Store** - fuente única de verdad
2. **Action** - descripción de la intención de cambiar el estado
3. **Reducer** - función que calcula el state nuevo
4. **Middleware** - lugar para lógica async y side effects

#### Ventajas:

1. **Data flow predecible**
2. **State centralizado**
3. **Transparencia de cambios**

#### Desventajas:

1. **Mucho boilerplate**
2. **Puede ser excesivo para UI de Flutter**
3. **A menudo pierde frente a enfoques modernos en comodidad**

#### Conclusión práctica:

Redux tiene valor histórico y buena disciplina, pero en proyectos Flutter
modernos se usa menos que Riverpod, Provider o BLoC.

</details>

<details>
<summary>58. ¿Qué es `ValueNotifier`?</summary>

#### Flutter

`ValueNotifier<T>` es una clase reactiva simple en Flutter que guarda un valor y
notifica a los listeners cuando ese valor cambia.

#### Ejemplo:

```dart
final counter = ValueNotifier<int>(0);

counter.value++;
```

#### Para qué se usa:

1. **State local simple o a nivel de pantalla**
2. **Escenarios reactivos minimalistas**
3. **Cuando no se quiere incorporar state management completo**

#### Con qué se usa:

Lo más común es junto con `ValueListenableBuilder`.

```dart
ValueListenableBuilder<int>(
  valueListenable: counter,
  builder: (context, value, child) {
    return Text('$value');
  },
)
```

#### Sentido práctico:

`ValueNotifier` es una buena herramienta lightweight cuando el state es simple y
no requiere arquitectura compleja.

</details>

<details>
<summary>59. ¿Qué es `InheritedWidget`?</summary>

#### Flutter

`InheritedWidget` es el mecanismo base de Flutter para pasar datos hacia abajo en
el árbol de widgets y actualizar widgets dependientes cuando esos datos cambian.

#### Rol principal:

1. **Propagación de datos compartidos en un subárbol**
2. **Acceso a dependencias mediante `BuildContext`**
3. **Actualización optimizada solo de widgets suscritos**

#### Dónde se usa:

- `Theme`
- `MediaQuery`
- `Directionality`
- `Provider` y otras bibliotecas por debajo

#### Por qué es importante:

`InheritedWidget` es un mecanismo fundamental de Flutter. Aunque el equipo no lo
escriba a mano, muchas bibliotecas populares se basan en él.

</details>

<details>
<summary>60. ¿Cuál es la diferencia entre `Provider` e `InheritedWidget`?</summary>

#### Flutter

`InheritedWidget` es un mecanismo base de Flutter, y `Provider` es una
abstracción de biblioteca más cómoda construida sobre él.

#### Diferencia principal:

| Criterio    | `InheritedWidget`                           | `Provider`                        |
| ----------- | ------------------------------------------- | --------------------------------- |
| Nivel       | API base de bajo nivel                      | High-level abstraction            |
| Comodidad   | Requiere mucho código manual                | Mucho más simple de usar          |
| Boilerplate | Más                                          | Menos                             |
| Escalado    | Poco cómodo directo para la mayoría de equipos | Mejor para aplicaciones reales |

#### Conclusión práctica:

- Si necesitas entender bases de Flutter, debes conocer `InheritedWidget`
- Si necesitas construir app-level state rápido y cómodo, suele usarse `Provider`

#### Idea clave:

`Provider` no reemplaza el concepto de `InheritedWidget`; lo hace más cómodo para
el desarrollo diario.

</details>

<details>
<summary>61. ¿Cómo funciona la navegación en Flutter?</summary>

#### Flutter

La navegación en Flutter está construida alrededor de una pila de rutas
(routes). Cuando el usuario pasa a una nueva pantalla, se agrega una nueva route
a la pila; y al volver, se quita la route superior.

#### Idea principal:

1. **La pantalla actual es el elemento superior de la pila**
2. **Una nueva transición agrega una nueva route**
3. **Volver elimina la route superior**

#### Cómo se ve en la práctica:

- Ir adelante: `push`
- Volver atrás: `pop`

#### Opciones de navegación:

1. **Imperative navigation** mediante `Navigator`
2. **Named routes**
3. **Router API / declarative navigation**
4. **Paquetes como `go_router` o `auto_route`**

#### Conclusión práctica:

Para apps simples, a menudo basta con `Navigator` básico. Para productos grandes
con deep links, web navigation y routing complejo, se suele elegir un enfoque
basado en router.

</details>

<details>
<summary>62. ¿Qué es `Navigator`?</summary>

#### Flutter

`Navigator` es el mecanismo core de Flutter para gestionar transiciones entre
pantallas.

#### Qué hace:

1. **Guarda la pila de rutas**
2. **Agrega nuevas pantallas**
3. **Quita pantallas actuales**
4. **Devuelve resultados a la pantalla anterior**

#### Ejemplo del rol de `Navigator`:

Se puede imaginar como una pila de páginas, donde la última abierta es la
activa.

#### Ejemplo:

```dart
Navigator.of(context).push(
  MaterialPageRoute(
    builder: (_) => const DetailsPage(),
  ),
);
```

#### Importante:

`Navigator` está estrechamente ligado a `BuildContext`, por eso debe llamarse con
un contexto que tenga acceso al árbol de navegación necesario.

</details>

<details>
<summary>63. ¿Qué hacen los métodos `Navigator.push()` y `Navigator.pop()`?</summary>

#### Flutter

`Navigator.push()` agrega una pantalla nueva a la pila de navegación, y
`Navigator.pop()` vuelve atrás eliminando la pantalla superior de la pila.

#### `Navigator.push()`

Abre una route nueva.

```dart
Navigator.push(
  context,
  MaterialPageRoute(
    builder: (_) => const DetailsPage(),
  ),
);
```

#### `Navigator.pop()`

Cierra la route actual.

```dart
Navigator.pop(context);
```

#### Además:

`pop()` puede devolver un valor:

```dart
Navigator.pop(context, 'success');
```

#### Sentido práctico:

Son métodos base de navegación en la mayoría de apps Flutter y una de las
primeras APIs que hay que conocer bien en entrevistas.

</details>

<details>
<summary>64. ¿Cómo pasar datos entre pantallas en Flutter?</summary>

#### Flutter

Los datos entre pantallas en Flutter, por lo general, se pasan por el
constructor de la route de pantalla o por el resultado devuelto desde
`Navigator.pop()`.

#### Pasar hacia adelante por constructor:

```dart
Navigator.push(
  context,
  MaterialPageRoute(
    builder: (_) => DetailsPage(userId: '42'),
  ),
);
```

#### Pantalla receptora:

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

#### Devolver datos hacia atrás:

```dart
final result = await Navigator.push<String>(
  context,
  MaterialPageRoute(
    builder: (_) => const DetailsPage(),
  ),
);
```

Y de regreso:

```dart
Navigator.pop(context, 'done');
```

#### Otras opciones:

1. **Named routes arguments**
2. **Global/app state**
3. **State management con Provider, Riverpod, BLoC**

#### Regla práctica:

Los datos puntuales de pantalla a pantalla conviene pasarlos explícitamente por
constructor. No hace falta llevarlos a global state de inmediato.

</details>

<details>
<summary>65. ¿Qué es `ModalBottomSheet`?</summary>

#### Flutter

`ModalBottomSheet` es un panel modal inferior que aparece sobre el contenido
actual y bloquea la interacción con el fondo hasta que se cierre.

#### Para qué se usa:

1. **Acciones sobre contenido**
2. **Selección de opciones**
3. **Filtros**
4. **Formularios de interacción corta**

#### Ejemplo:

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

#### Importante:

- Es un componente **modal**
- Se puede cerrar con gesto o con `Navigator.pop(context)`

#### Sentido práctico:

`ModalBottomSheet` se usa mucho en mobile UI en lugar de una pantalla separada o
un diálogo, cuando se necesita una interacción contextual rápida.

</details>

<details>
<summary>66. ¿Qué es el tema (`Theme`) en Flutter?</summary>

#### Flutter

El tema en Flutter es un conjunto centralizado de ajustes visuales de la
aplicación: colores, tipografía, estilos de botones, campos input, app bar y
otros componentes.

#### Para qué sirve:

1. **Estilo visual unificado**
2. **Cambio simple de diseño en un solo lugar**
3. **Soporte de light/dark mode**
4. **Consistencia de UI en toda la app**

#### Ejemplo:

```dart
MaterialApp(
  theme: ThemeData(
    colorScheme: ColorScheme.fromSeed(seedColor: Colors.blue),
    useMaterial3: true,
  ),
  home: const HomePage(),
)
```

#### Acceso al tema:

```dart
final theme = Theme.of(context);
```

#### Conclusión práctica:

En aplicaciones de production, el tema es una parte importante del design
system, no solo un conjunto de colores.

</details>

<details>
<summary>67. ¿Cuál es la diferencia entre widgets Material y Cupertino?</summary>

#### Flutter

Material y Cupertino son dos conjuntos distintos de componentes UI en Flutter
que corresponden a diferentes sistemas de diseño de plataforma.

#### Material:

- Enfocado en **Google Material Design**
- Suele usarse como enfoque por defecto en Flutter
- Widgets principales: `MaterialApp`, `Scaffold`, `AppBar`, `ElevatedButton`

#### Cupertino:

- Enfocado en **Apple Human Interface Guidelines**
- Ofrece aspecto y comportamiento estilo iOS
- Widgets principales: `CupertinoApp`, `CupertinoPageScaffold`, `CupertinoButton`,
  `CupertinoNavigationBar`

#### Diferencia principal:

| Criterio          | Material                    | Cupertino       |
| ----------------- | --------------------------- | --------------- |
| Diseño            | Google Material             | Apple iOS style |
| Componentes       | Android-first style         | iOS-first style |
| Use case típico   | Default UI multiplataforma  | iOS-native feel |

#### Enfoque práctico:

Muchos equipos usan Material como base incluso para apps multiplataforma. Pero
si el producto busca sensación iOS lo más nativa posible, Cupertino se vuelve
importante.

</details>

<details>
<summary>68. ¿Cómo implementar una interfaz adaptativa en Flutter?</summary>

#### Flutter

Una interfaz adaptativa en Flutter se implementa con una combinación de
responsive layout, widgets flexibles y lógica que considera tamaño y
características de pantalla.

#### Herramientas principales:

1. **`LayoutBuilder`**
2. **`MediaQuery`**
3. **`Expanded` / `Flexible`**
4. **`Wrap`**
5. **`AspectRatio`**
6. **Renderizado condicional para distintos breakpoints**

#### Ejemplo de enfoque:

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

#### Principios prácticos:

- No fijar todo rígidamente en píxeles
- Considerar portrait y landscape
- Considerar tablet, foldable, desktop y web
- Extraer breakpoint logic a una estructura clara

#### Conclusión práctica:

La adaptatividad en Flutter no es un único widget, sino una disciplina de layout
para que la UI escale correctamente en distintos form factors.

</details>

<details>
<summary>69. ¿Qué es `FittedBox`?</summary>

#### Flutter

`FittedBox` es un widget que escala y posiciona el elemento hijo para que encaje
en el espacio disponible según el `fit` elegido.

#### Para qué se usa:

1. **Escalar texto o iconos**
2. **Adaptar contenido al contenedor**
3. **Evitar overflow en ciertos escenarios de layout**

#### Ejemplo:

```dart
FittedBox(
  fit: BoxFit.scaleDown,
  child: Text(
    'Very long title',
    style: TextStyle(fontSize: 32),
  ),
)
```

#### Importante:

`FittedBox` no "cura" todos los problemas de layout. Debe aplicarse cuando
realmente se necesita escalar contenido, y no en lugar de un manejo correcto de
constraints.

#### Sentido práctico:

Es una herramienta útil para edge cases en responsive UI, pero no la base de la
arquitectura de layout.

</details>

<details>
<summary>70. ¿Qué son los isolates (Isolates) en Flutter?</summary>

#### Flutter

Los isolates en Dart/Flutter son unidades de ejecución separadas con su propia
memoria y su propio event loop.

#### Idea principal:

A diferencia de los threads clásicos con memoria compartida, los isolates no
comparten estado entre sí de forma directa.

#### Qué significa esto:

1. **Cada isolate tiene su propio heap**
2. **Cada isolate se ejecuta de forma independiente**
3. **Los datos no se comparten directamente entre isolates**

#### Por qué es importante:

Este enfoque reduce el riesgo de race conditions y problemas de memoria
compartida.

#### Sentido práctico en Flutter:

La UI normalmente se ejecuta en el isolate principal. Los cálculos pesados se
pueden mover a otro isolate para no bloquear la interfaz.

</details>

<details>
<summary>71. ¿Para qué se usan los isolates?</summary>

#### Flutter

Los isolates se usan para sacar tareas pesadas o de larga duración del isolate
principal, donde corre la UI.

#### Escenarios típicos:

1. **Cálculos pesados**
2. **Parsing de JSON grandes**
3. **Procesamiento de archivos**
4. **Cifrado o decodificación de datos**
5. **CPU-intensive business logic**

#### Por qué se necesita:

Si se ejecuta trabajo síncrono pesado en el isolate principal, la UI puede
empezar a ir lenta, perder frames o "congelarse".

#### Conclusión práctica:

Los isolates no son para cualquier operación async, sino específicamente para
tareas CPU-bound. Para solicitudes HTTP normales o I/O, en la mayoría de casos
basta con `Future` y `async/await`.

</details>

<details>
<summary>72. ¿Cómo interactúan los isolates entre sí?</summary>

#### Flutter

Los isolates interactúan entre sí mediante paso de mensajes, no mediante memoria
compartida.

#### Mecanismos principales:

1. **`SendPort`** - para enviar mensajes
2. **`ReceivePort`** - para recibir mensajes

#### Idea de ejemplo:

Un isolate envía datos a otro isolate en forma de message passing.

#### Importante:

- Los isolates no pueden modificar directamente un objeto compartido
- Los datos se transmiten como mensajes serializados o transferibles

#### Sentido práctico:

Este modelo es más complejo que llamadas async normales, pero hace la ejecución
paralela más segura y predecible.

</details>

<details>
<summary>73. ¿Qué tipos de Streams existen en Dart?</summary>

#### Flutter

En Dart, normalmente se distinguen dos tipos principales de streams:
**single-subscription** y **broadcast streams**.

#### 1. Single-subscription stream

Este stream está pensado para un solo listener.

#### Características:

1. **Tiene un único subscriber**
2. **Es adecuado para flujo de datos secuencial**
3. **Se usa con frecuencia para file I/O o async data pipelines**

#### 2. Broadcast stream

Este stream permite que varios listeners se suscriban al mismo tiempo.

#### Características:

1. **Tiene múltiples subscribers**
2. **Es adecuado para eventos**
3. **Se parece a un event bus / signal source**

#### Conclusión práctica:

Si la fuente de datos tiene un solo consumidor, normalmente basta un
single-subscription stream. Si hay que difundir eventos a varios listeners, se
usa broadcast stream.

</details>

<details>
<summary>74. ¿Qué es `FutureBuilder`?</summary>

#### Flutter

`FutureBuilder` es un widget de Flutter que construye UI en función del estado de
un `Future`.

#### Para qué se usa:

1. **Mostrar carga**
2. **Mostrar resultado exitoso**
3. **Mostrar error**

#### Ejemplo:

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

#### Qué aporta `snapshot`:

1. **`connectionState`**
2. **`hasData`**
3. **`hasError`**
4. **`data`**
5. **`error`**

#### Matiz práctico:

No conviene crear el `Future` directamente dentro de `build()` sin necesidad, o
puede ejecutarse de nuevo en cada rebuild.

</details>

<details>
<summary>75. ¿Qué es `StreamBuilder`?</summary>

#### Flutter

`StreamBuilder` es un widget de Flutter que construye UI en función de valores
que llegan desde un `Stream`.

#### Diferencia principal frente a `FutureBuilder`:

- `FutureBuilder` trabaja con un resultado único
- `StreamBuilder` trabaja con un flujo de actualizaciones en el tiempo

#### Ejemplo:

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

#### Escenarios típicos:

1. **WebSocket updates**
2. **Live data**
3. **BLoC state streams**
4. **Eventos reactivos**

#### Sentido práctico:

`StreamBuilder` es cómodo para UI reactiva, pero hay que controlar bien el ciclo
de vida de los streams para evitar suscripciones innecesarias o memory leaks.

</details>

<details>
<summary>76. ¿Cómo funcionan las animaciones en Flutter?</summary>

#### Flutter

Las animaciones en Flutter funcionan mediante el cambio secuencial de valores en
el tiempo y el redibujado de la UI en cada frame.

#### Idea principal:

1. **Hay un valor inicial**
2. **Hay un valor final**
3. **Flutter calcula estados intermedios**
4. **La UI se actualiza frame a frame**

#### Componentes principales:

1. **`AnimationController`** - controla el tiempo de la animación
2. **`Tween`** - define el rango de valores
3. **`CurvedAnimation`** - define la curva de movimiento
4. **Builder o Animated widget** - actualiza la UI

#### Dos enfoques principales:

1. **Implicit animations** - animaciones simples sin control manual
2. **Explicit animations** - control total mediante controller

#### Sentido práctico:

Flutter tiene un sistema de animación muy sólido, porque la UI se dibuja con su
propio rendering engine, lo que da mucha flexibilidad para smooth transitions y
custom motion.

</details>

<details>
<summary>77. ¿Qué es `AnimationController`?</summary>

#### Flutter

`AnimationController` es un objeto que controla el ciclo de vida de una
animación explícita: inicio, parada, reverse y progreso actual.

#### Qué hace:

1. **Guarda la duración de la animación**
2. **Se mueve en una escala de valores, normalmente de `0.0` a `1.0`**
3. **Permite lanzar `forward()`, `reverse()`, `repeat()`**

#### Ejemplo:

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

#### Importante:

Normalmente hay que hacer `dispose()` de `AnimationController`, o se puede
producir fuga de recursos.

</details>

<details>
<summary>78. ¿Qué es una animación Tween?</summary>

#### Flutter

Una animación Tween es una animación en la que el valor cambia suavemente entre
dos puntos: `begin` y `end`.

#### Idea principal:

Tween describe **cómo interpolar el valor**.

#### Ejemplo:

```dart
final animation = Tween<double>(
  begin: 0,
  end: 100,
).animate(controller);
```

#### Qué se puede animar con Tween:

1. **Números**
2. **Colores**
3. **Espaciados**
4. **Tamaños**
5. **Alignment**

#### Sentido práctico:

Tween no inicia la animación por sí mismo. Solo describe la transición de
valores, y quien la mueve es `AnimationController`.

</details>

<details>
<summary>79. ¿Qué es `vsync`?</summary>

#### Flutter

`vsync` es un mecanismo de sincronización de la animación con la frecuencia de
actualización de la pantalla.

#### Para qué se necesita:

1. **Para no calcular frames cuando el widget no es visible**
2. **Para reducir carga innecesaria**
3. **Para sincronizar animaciones con el rendering pipeline**

#### Cómo se ve:

En `State` se usa con frecuencia `SingleTickerProviderStateMixin` y se pasa
`this` al `AnimationController`.

```dart
controller = AnimationController(
  vsync: this,
  duration: const Duration(milliseconds: 300),
);
```

#### Sentido práctico:

Sin `vsync`, las animaciones podrían seguir ejecutándose incluso cuando no hace
falta renderizarlas, lo que empeora el rendimiento.

</details>

<details>
<summary>80. ¿Qué es un ticker en Flutter?</summary>

#### Flutter

Ticker en Flutter es un objeto que genera un callback en cada frame de la
animación.

#### Rol principal:

1. **Notifica cada frame**
2. **Permite avanzar la animación en el tiempo**
3. **Se usa internamente en `AnimationController`**

#### En palabras simples:

Ticker es un "metrónomo" para la animación.

#### Sentido práctico:

Cuando trabajas con `AnimationController`, casi siempre trabajas también, de
forma indirecta, con ticker.

</details>

<details>
<summary>81. ¿Qué es `AnimatedBuilder`?</summary>

#### Flutter

`AnimatedBuilder` es un widget que reconstruye una parte de la UI en respuesta a
cambios del valor animado.

#### Para qué sirve:

1. **Reaccionar a `Animation`**
2. **Actualizar solo la parte necesaria de la UI**
3. **Construir explicit animations sin boilerplate extra**

#### Ejemplo:

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

#### Ventaja:

Se puede pasar un `child` que no se reconstruirá en cada frame.

</details>

<details>
<summary>82. ¿Qué es `AnimatedContainer`?</summary>

#### Flutter

`AnimatedContainer` es un widget para implicit animation que anima
automáticamente los cambios de sus propiedades.

#### Qué puede animar:

1. **Tamaño**
2. **Color**
3. **Padding**
4. **Margin**
5. **Alignment**
6. **Decoration**

#### Ejemplo:

```dart
AnimatedContainer(
  duration: const Duration(milliseconds: 300),
  width: isExpanded ? 200 : 100,
  color: isExpanded ? Colors.blue : Colors.red,
)
```

#### Sentido práctico:

`AnimatedContainer` es una de las formas más cómodas de añadir UI fluida
rápidamente sin controlar controllers manualmente.

</details>

<details>
<summary>83. ¿Cuál es la diferencia entre animaciones implicit y explicit?</summary>

#### Flutter

La diferencia entre implicit y explicit animation está en el nivel de control.

#### Implicit animations:

Flutter gestiona la animación cuando cambian las propiedades del widget.

#### Ejemplos:

- `AnimatedContainer`
- `AnimatedOpacity`
- `AnimatedAlign`

#### Explicit animations:

El desarrollador controla la animación manualmente con `AnimationController`.

#### Ejemplos:

- `AnimatedBuilder`
- `FadeTransition`
- `ScaleTransition`

#### Diferencia principal:

| Criterio    | Implicit animations      | Explicit animations          |
| ----------- | ------------------------ | ---------------------------- |
| Control     | Menor                    | Total                        |
| Complejidad | Más baja                 | Más alta                     |
| Use case    | Transiciones UI simples  | Escenarios custom complejos  |

#### Conclusión práctica:

Para animaciones simples conviene empezar por widgets implicit. Para escenarios
de motion complejos y sincronización de varias animaciones, hacen falta explicit
animations.

</details>

<details>
<summary>84. ¿Qué es la arquitectura de Flutter?</summary>

#### Flutter

La arquitectura de Flutter consta de varias capas clave: framework, engine,
embedder y plataforma.

#### Capas principales:

1. **Framework** - widgets, rendering, gestures, animation, foundation
2. **Engine** - renderizado, texto, compositing, integración Skia/gráficos
3. **Embedder** - integración con Android, iOS, desktop o web
4. **Platform** - SO nativo y sus APIs

#### Idea principal:

Flutter no solo envuelve componentes UI nativos, sino que construye su propio
stack de UI de arriba abajo.

#### Sentido práctico:

Gracias a esta arquitectura, Flutter ofrece alta consistencia de UI entre
plataformas, aunque a veces requiere integración específica con código nativo.

</details>

<details>
<summary>85. ¿Qué es el rendering pipeline en Flutter?</summary>

#### Flutter

El rendering pipeline en Flutter es la secuencia de etapas por las que pasa la
UI desde un cambio de state hasta mostrar un frame en pantalla.

#### Simplificado, el pipeline se ve así:

1. **State change**
2. **Build**
3. **Layout**
4. **Paint**
5. **Compositing**
6. **Rasterization**

#### Qué significa:

- `build` forma el widget tree
- `layout` calcula tamaños y posiciones
- `paint` dibuja el resultado visual
- el engine convierte eso en un frame

#### Sentido práctico:

Entender el rendering pipeline ayuda a depurar jank, rebuilds innecesarios,
repintados y problemas de rendimiento.

</details>

<details>
<summary>86. ¿Qué son Widgets, Elements y RenderObjects?</summary>

#### Flutter

Son tres niveles clave del modelo de UI de Flutter.

#### Widgets

Widgets son configuraciones inmutables de UI.

#### Elements

Elements son los vínculos "vivos" entre el widget tree y el render tree.

#### RenderObjects

RenderObjects se encargan de layout, paint y low-level rendering.

#### En palabras simples:

1. **Widget** - qué queremos mostrar
2. **Element** - vínculo y ciclo de vida en el árbol
3. **RenderObject** - cómo se mide y se dibuja realmente

#### Sentido práctico:

Este modelo explica por qué Flutter puede actualizar la UI de forma eficiente
sin reconstruir todo desde cero a bajo nivel.

</details>

<details>
<summary>87. ¿Qué es `FlutterEngine`?</summary>

#### Flutter

`FlutterEngine` es la parte de bajo nivel de Flutter responsable de ejecutar
código Dart y renderizar frames.

#### Qué incluye su responsabilidad:

1. **Dart runtime**
2. **Renderizado**
3. **Text layout**
4. **Compositing**
5. **Interacción con plataforma a bajo nivel**

#### Sentido práctico:

El framework ofrece una API cómoda para widgets, y el engine se encarga de que
todo funcione realmente en la pantalla del dispositivo.

</details>

<details>
<summary>88. ¿Qué es `WidgetsBinding`?</summary>

#### Flutter

`WidgetsBinding` es una capa de binding que conecta el framework de Flutter con
el engine y coordina el ciclo de vida de la app a nivel de widgets.

#### Para qué sirve:

1. **Inicialización del framework**
2. **Trabajo con frame callbacks**
3. **Acceso al binding lifecycle**
4. **Coordinación entre framework y engine**

#### Ejemplo:

```dart
WidgetsFlutterBinding.ensureInitialized();
```

#### Sentido práctico:

Es uno de los mecanismos centrales de Flutter runtime, aunque en código típico
el desarrollador suele verlo de forma indirecta.

</details>

<details>
<summary>89. ¿Qué es `WidgetsBindingObserver`?</summary>

#### Flutter

`WidgetsBindingObserver` es una interfaz que permite escuchar cambios del ciclo
de vida de la app y otros framework events.

#### Para qué se usa:

1. **Seguimiento de `AppLifecycleState`**
2. **Reacción a `resumed`, `paused`, `inactive`, `detached`**
3. **Manejo de cambios a nivel de plataforma**

#### Ejemplo de use case:

- detener video cuando la app pasa a background
- actualizar datos cuando la app vuelve a foreground

#### Sentido práctico:

Es una herramienta importante para ciclo de vida, especialmente en apps con
media, analytics, conexiones socket o lógica sensible a background.

</details>

<details>
<summary>90. ¿Qué son platform channels?</summary>

#### Flutter

Platform channels son un mecanismo de interacción entre código Flutter en Dart y
código nativo de plataforma, como Kotlin/Java en Android o Swift/Objective-C en
iOS.

#### Para qué se necesitan:

1. **Acceso a APIs nativas**
2. **Trabajo con SDKs de plataforma**
3. **Integración con funcionalidad que Flutter no tiene directamente**

#### Tipos principales:

1. **`MethodChannel`**
2. **`EventChannel`**
3. **`BasicMessageChannel`**

#### Sentido práctico:

Platform channels son necesarios cuando una app Flutter va más allá de UI pura y
debe interactuar con capacidades nativas del dispositivo o SDKs de terceros.

</details>

<details>
<summary>91. ¿Qué es tree shaking?</summary>

#### Flutter

Tree shaking es el proceso de eliminar código no utilizado del build final.

#### Idea principal:

Si cierto código no se utiliza, el compilador o el sistema de build no lo incluye
en la compilación de release.

#### Para qué sirve:

1. **Menor tamaño de la aplicación**
2. **Carga más rápida**
3. **Menos código innecesario en production**

#### Sentido práctico en Flutter:

Tree shaking es especialmente importante para builds de release, porque ayuda a
reducir el tamaño de los artefactos y mejorar la eficiencia de entrega de la app.

</details>

<details>
<summary>92. ¿Cómo optimizar el rendimiento de una app Flutter?</summary>

#### Flutter

La optimización de rendimiento en Flutter se centra en reducir rebuilds y
repaints innecesarios, cálculos costosos en el UI isolate y consumo excesivo de
memoria.

#### Principales líneas de optimización:

1. **Reducir la cantidad de rebuilds innecesarios**
2. **No ejecutar tareas CPU-bound pesadas en el isolate principal**
3. **Usar listas lazy**
4. **Usar `const` cuando sea posible**
5. **Optimizar imágenes y recursos**
6. **Perfilar la app en profile mode**

#### Herramientas prácticas:

- Flutter DevTools
- Performance overlay
- Timeline profiling
- Memory profiler

#### Conclusión práctica:

El rendimiento en Flutter no se debe "adivinar", se debe medir. Una buena
optimización casi siempre comienza con profiling y no con cambios aleatorios.

</details>

<details>
<summary>93. ¿Cómo reducir la cantidad de rebuilds de widgets?</summary>

#### Flutter

Para reducir la cantidad de rebuilds, hay que localizar el state y reconstruir
solo las partes del árbol que realmente dependen de cambios.

#### Enfoques principales:

1. **Dividir la UI en widgets más pequeños**
2. **Usar `const`**
3. **Localizar el state lo más abajo posible**
4. **No escuchar estados globales innecesarios**
5. **Usar enfoques selector (`select`, selectors, derived state)**

#### Ejemplo práctico de razonamiento:

Si cambia solo el badge en el header, no hace falta reconstruir toda la pantalla.

#### Importante:

Un rebuild por sí mismo no siempre es un problema. El problema aparece cuando el
rebuild es costoso o ocurre demasiado seguido.

</details>

<details>
<summary>94. ¿Qué es `RepaintBoundary`?</summary>

#### Flutter

`RepaintBoundary` es un widget que separa una parte del render tree en una región
de repintado independiente.

#### Para qué sirve:

1. **Para no repintar toda la pantalla**
2. **Para aislar zonas de paint costosas**
3. **Para mejorar el rendimiento en UI complejas**

#### Idea principal:

Si una parte del árbol cambia con frecuencia y otra no, `RepaintBoundary` puede
ayudar a reducir repaints innecesarios.

#### Matiz práctico:

No conviene agregarlo en todas partes sin pensar. Como cualquier optimización,
tiene sentido donde el profiling mostró un problema real de repaint.

</details>

<details>
<summary>95. ¿Cómo reducir el tamaño de una app Flutter?</summary>

#### Flutter

El tamaño de una app Flutter se reduce optimizando dependencias, recursos y la
configuración de build de release.

#### Enfoques principales:

1. **Eliminar paquetes innecesarios**
2. **Optimizar assets e imágenes**
3. **Usar tree shaking**
4. **No arrastrar SDKs grandes sin necesidad**
5. **Minimizar cantidad de fuentes y locales**

#### Pasos prácticos:

- compilar release, no debug
- analizar la composición del build
- revisar qué paquetes agregan peso

#### Conclusión práctica:

El tamaño de la app suele crecer no por Flutter en sí, sino por recursos
excesivos, SDKs y dependencias de terceros.

</details>

<details>
<summary>96. ¿Cuáles son las best practices para apps Flutter grandes?</summary>

#### Flutter

Para apps Flutter grandes, las best practices clave están relacionadas con la
arquitectura, la modularidad, la capacidad de prueba y la disciplina al trabajar
con el estado.

#### Prácticas principales:

1. **Estructura del proyecto feature-based o por capas**
2. **Separación clara entre UI, domain y data layer**
3. **State management transparente**
4. **Dependency injection**
5. **Cobertura con tests de la lógica crítica**
6. **Un único design system / theme system**
7. **Logging, analítica y error reporting**

#### Además:

- evitar god-classes
- no mezclar network, UI y business logic en un solo lugar
- estandarizar los enfoques del equipo

#### Conclusión práctica:

Una app Flutter grande casi siempre pierde sin disciplina arquitectónica, incluso
si empezó como un "cliente móvil simple".

</details>

<details>
<summary>97. ¿Qué tipos de testing existen en Flutter?</summary>

#### Flutter

En Flutter, con mayor frecuencia se usan tres tipos principales de testing.

#### 1. Unit tests

Prueban funciones, servicios, use cases y business logic por separado.

#### 2. Widget tests

Prueban widgets individuales y su comportamiento en un entorno aislado.

#### 3. Integration tests

Prueban user flows reales en una app casi completa.

#### Sentido práctico:

Una estrategia de testing saludable normalmente combina los tres tipos y no
depende solo de uno.

</details>

<details>
<summary>98. ¿Qué es unit testing?</summary>

#### Flutter

Unit testing es probar pequeñas unidades aisladas de código, sin UI y sin
dependencia de la app real.

#### Qué suele probarse:

1. **Funciones**
2. **Servicios**
3. **Use cases**
4. **Parsing**
5. **Validación**

#### Ventajas:

1. **Ejecución rápida**
2. **Debug barato**
3. **Muy adecuado para la business logic**

#### Conclusión práctica:

Si la lógica puede probarse sin Flutter UI, este suele ser el tipo de testing más
estable y más económico.

</details>

<details>
<summary>99. ¿Qué es widget testing?</summary>

#### Flutter

Widget testing es probar widgets de Flutter en un entorno controlado, sin ejecutar
la app completa en un dispositivo real.

#### Qué se puede verificar:

1. **Qué muestra el widget**
2. **Cómo reacciona a la user interaction**
3. **Si cambia la UI después de una acción**

#### Ejemplo de escenario:

- pulsar un botón
- comprobar que apareció un nuevo texto

#### Sentido práctico:

Los widget tests dan un buen equilibrio entre velocidad y valor, por eso en
Flutter suelen considerarse uno de los tipos de tests más útiles.

</details>

<details>
<summary>100. ¿Qué es integration testing?</summary>

#### Flutter

Integration testing es probar user flows completos o casi completos dentro de la
app.

#### Qué se verifica:

1. **Interacción de varias pantallas**
2. **Navegación**
3. **Trabajo con servicios reales o sus sustitutos cercanos**
4. **Comportamiento completo del escenario del usuario**

#### Ejemplo:

- login
- apertura de una lista
- transición a detalles
- finalización de la acción del usuario

#### Desventaja práctica:

Los integration tests son más lentos, más frágiles y más costosos que unit y
widget tests, por eso normalmente cubren escenarios críticos.

</details>

<details>
<summary>101. ¿Cómo probar un widget individual en Flutter?</summary>

#### Flutter

Un widget individual en Flutter normalmente se prueba con un widget test usando
`testWidgets`, `WidgetTester` y `pumpWidget()`.

#### Ejemplo:

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

#### Proceso típico:

1. **Construir el widget con `pumpWidget()`**
2. **Encontrar elementos con `find`**
3. **Ejecutar interaction**
4. **Verificar el resultado esperado**

#### Sentido práctico:

Para la mayoría de componentes UI, esta es la forma básica y correcta de
comprobar el comportamiento.

</details>

<details>
<summary>102. ¿Cómo realizar solicitudes HTTP en Flutter?</summary>

#### Flutter

Las solicitudes HTTP en Flutter normalmente se hacen con paquetes como `http` o
`dio`.

#### Enfoques principales:

1. **Paquete `http`**: una opción simple y básica
2. **Paquete `dio`**: una opción más potente con interceptors, retries y config

#### Ejemplo con `http`:

```dart
final response = await http.get(
  Uri.parse('https://example.com/api/users'),
);
```

#### Enfoque práctico en production:

- API client separado
- modelos de datos
- error handling
- estrategia de timeout/retry
- logging de solicitudes

#### Conclusión práctica:

La llamada HTTP en sí es simple, pero un networking production-ready ya es una
zona arquitectónica aparte dentro de la app.

</details>

<details>
<summary>103. ¿Qué bases de datos se pueden usar con Flutter?</summary>

#### Flutter

Con Flutter se pueden usar varios tipos de bases de datos locales y remotas.

#### Opciones locales:

1. **SQLite**
2. **Hive**
3. **Isar**
4. **SharedPreferences / key-value storage**

#### Opciones remotas:

1. **Firebase Firestore**
2. **Supabase / servicios basados en PostgreSQL**
3. **Cualquier backend con API REST o GraphQL**

#### Elección práctica:

- **Hive / Isar**: almacenamiento local rápido
- **SQLite**: datos locales estructurados
- **Firestore**: datos cloud en tiempo real

#### Conclusión práctica:

La elección de la base depende no de Flutter, sino del modelo de datos, de los
requisitos offline-first, de la sincronización y de la complejidad del dominio.

</details>

<details>
<summary>104. ¿Qué son los Flutter plugins?</summary>

#### Flutter

Los Flutter plugins son paquetes que proporcionan una API de Flutter para acceder
a capacidades nativas de la plataforma.

#### Qué aportan:

1. **Acceso a la cámara**
2. **Acceso a geolocalización**
3. **Push notifications**
4. **Bluetooth, sensors, storage, permissions**

#### Idea principal:

Un plugin tiene API en Dart y implementaciones de plataforma para Android, iOS y
en algunos casos otras plataformas.

#### Sentido práctico:

Los plugins permiten no escribir platform channels manualmente cada vez, sino
usar una integración ya lista.

</details>

<details>
<summary>105. ¿Cómo integrar Flutter en una app nativa ya existente?</summary>

#### Flutter

Flutter se puede integrar en una app Android o iOS existente como un módulo
separado.

#### Idea principal:

Flutter no tiene que ser necesariamente "toda la app". Se puede incrustar solo en
pantallas o features concretas.

#### Cómo suele funcionar:

1. **Se crea un Flutter module**
2. **La app nativa conecta este módulo**
3. **Ciertas pantallas se abren mediante `FlutterActivity`, `FlutterFragment` o
   integración iOS**

#### Escenarios prácticos:

- migración gradual de una app nativa a Flutter
- lanzamiento de una feature nueva en Flutter sin reescribir todo

#### Conclusión práctica:

El enfoque add-to-app es útil cuando el negocio no está listo para reescribir
todo, pero quiere usar Flutter de forma gradual en el producto.

</details>

<details>
<summary>106. ¿Cómo implementar código dependiente de la plataforma en Flutter?</summary>

#### Flutter

El código dependiente de la plataforma en Flutter se implementa de varias maneras
según el nivel de la tarea.

#### Enfoques principales:

1. **Platform channels**: cuando se necesita código nativo
2. **Plugins listos**: cuando ya existe un paquete para la función necesaria
3. **`Platform.isAndroid` / `Platform.isIOS`**: para ramas de lógica por
   plataforma
4. **`defaultTargetPlatform`**: para comportamiento de UI

#### Ejemplo:

```dart
if (Platform.isIOS) {
  // iOS-specific logic
} else if (Platform.isAndroid) {
  // Android-specific logic
}
```

#### Conclusión práctica:

Si existe un plugin listo y probado, es mejor usarlo. Si no existe, entonces ya
toca escribir un platform channel o un plugin propio.

</details>
