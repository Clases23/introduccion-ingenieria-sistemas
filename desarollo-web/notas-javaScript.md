
# Notas de Clase: Introducción a JavaScript para Desarrollo Web

## Introducción a JavaScript

JavaScript (JS) es un **lenguaje de programación interpretado** que se ejecuta en el navegador web. Se utiliza principalmente para crear **páginas web dinámicas e interactivas** en el lado del cliente. Esto significa que con JavaScript podemos lograr que una página web reaccione a las acciones del usuario (clics de mouse, teclas presionadas, envío de formularios, etc.) y cambie su contenido sin tener que recargar la página completa. JavaScript es un lenguaje **multi-paradigma** (soporta programación orientada a objetos, funcional, event-driven, etc.) y **dinámicamente tipado** (las variables no tienen un tipo fijo). 

> **Nota:** A pesar de su nombre, **JavaScript no es lo mismo que Java**. Son lenguajes diferentes; comparten cierta sintaxis básica, pero JavaScript fue creado originalmente para ejecutarse dentro de navegadores web, mientras que Java es un lenguaje compilado independiente. JavaScript tampoco requiere una compilación previa; el navegador interpreta el código JavaScript directamente.

**¿Cómo ejecutar código JavaScript?** Al ser un lenguaje pensado para la web, normalmente se inserta en páginas HTML. Hay dos formas comunes de usar JavaScript en un entorno de navegador:

- **Incluir código JavaScript en HTML:** Se utiliza la etiqueta `<script>` dentro del archivo HTML. El código JavaScript puede ir directamente entre las etiquetas `<script> ... </script>` o bien en un archivo externo. Por ejemplo, podemos tener en el HTML: 

  ```html
  <!DOCTYPE html>
  <html lang="es">
  <head>
    <meta charset="UTF-8">
    <title>Ejemplo JS</title>
  </head>
  <body>
    <h1>Mi página</h1>
    <p id="demo">Contenido inicial</p>

    <!-- Código JavaScript embebido -->
    <script>
      console.log("¡Hola desde la consola!");
      alert("¡Hola Mundo desde una alerta!"); // muestra un mensaje emergente
    </script>

    <!-- O bien enlazar un archivo JavaScript externo -->
    <!-- <script src="app.js"></script> -->
  </body>
  </html>
  ```

  En el ejemplo anterior, el primer script escribe un mensaje en la **consola del navegador** y muestra una ventana de alerta con un saludo. La última línea (comentada) muestra cómo incluir un archivo JS externo (`app.js`). Al cargar la página en un navegador, se ejecutará el código JavaScript.

- **Usar la consola del navegador:** Los navegadores web incluyen herramientas de desarrollador. En prácticamente cualquier navegador moderno (Chrome, Firefox, Edge, etc.), podemos abrir la consola de JavaScript (generalmente con tecla F12 o Ctrl+Shift+I, y luego la pestaña "Console"). Allí es posible escribir instrucciones JavaScript y ejecutarlas inmediatamente. Esto es útil para hacer pruebas rápidas o depurar nuestro código.

**Características clave de JavaScript:**

- Es **case-sensitive** (distingue mayúsculas y minúsculas). Por ejemplo, `variable` y `Variable` son identificadores distintos.
- Los programas de JavaScript (a veces llamados *scripts*) están compuestos por **instrucciones** o sentencias que se ejecutan secuencialmente, a menos que usemos estructuras de control para cambiar ese flujo.
- Tiene una sintaxis similar a C/Java en cuanto a uso de llaves `{}` para bloques de código, punto y coma `;` para separar sentencias (el punto y coma al final de cada instrucción es opcional en muchos casos, pero es buena práctica usarlo para evitar ambigüedades).
- Cuenta con un conjunto de **palabras reservadas** (como `if`, `else`, `for`, `function`, etc.) que no pueden usarse como nombres de variables o funciones.
- El estándar que define al lenguaje se llama **ECMAScript**. JavaScript ha ido evolucionando: la versión ES6 (ECMAScript 2015) introdujo mejoras importantes (como `let`, `const`, clases, funciones flecha, promesas, módulos, etc.) que utilizaremos en estas notas.

**Nuestro enfoque:** Nos centraremos en usar JavaScript **en el navegador**. No abordaremos aquí entornos como Node.js. Usaremos la consola del navegador y archivos HTML con `<script>` como nuestro entorno de ejecución. A medida que avancemos, veremos ejemplos prácticos y ejercicios para afianzar cada concepto.

### Ejercicios

1. **Hola Mundo:** Crea una página HTML mínima que muestre un mensaje de "Hola Mundo" usando JavaScript. Puedes hacerlo de dos formas: usando `alert("Hola Mundo");` para que aparezca una ventana emergente, o usando `console.log("Hola Mundo");` para que el mensaje aparezca en la consola del navegador. Abre la página en tu navegador y verifica el resultado (si usaste `console.log`, abre la consola para ver el mensaje).
2. **Interactuando con la consola:** Abre la consola de tu navegador e intenta escribir algunas operaciones simples en JavaScript. Por ejemplo, escribe `2+2` y presiona Enter (deberías ver el resultado `4`). Prueba también a definir una variable escribiendo `let x = 5;` y luego `x + 10` para ver el resultado de esa expresión.
3. **Modificando el DOM desde la consola:** En la página HTML que creaste en el ejercicio 1, agrega un elemento HTML con un id (por ejemplo, `<p id="texto">Texto inicial</p>`). Luego, abre la consola y escribe `document.getElementById("texto").textContent = "Texto cambiado desde la consola";`. Observa cómo cambia el contenido de la página. (No te preocupes si no entiendes aún `document.getElementById` y `.textContent`; los veremos más adelante en la sección del DOM).

---

## Variables y Tipos de Datos

Una **variable** es un contenedor que nos permite almacenar datos (números, texto, etc.) en la memoria para poder utilizarlos más tarde en nuestro programa. En JavaScript podemos crear (declarar) una variable usando las palabras clave `var`, `let` o `const`. Veamos cómo funcionan:

### Declaración de variables: `var`, `let` y `const`

- **var:** Era la forma tradicional de declarar variables en JavaScript. Ejemplo: `var nombre = "Ana";`. Sin embargo, su uso hoy día es menos recomendado en favor de `let` y `const`, porque `var` tiene un comportamiento de *ámbito (scope)* diferente (ámbito de función) y permite volver a declarar la misma variable involuntariamente en el mismo ámbito. Aun así, es útil conocerlo porque existe mucho código antiguo que lo usa.
- **let:** Introducido en ES6, se usa para declarar variables **mutables** (que pueden cambiar su valor). Tiene **ámbito de bloque**, lo que significa que solo existe dentro del bloque `{ ... }` en el que se declara (por ejemplo, dentro de una función, un loop `for` o una estructura `if`). No permite volver a declarar la misma variable en ese mismo ámbito. Ejemplo: `let edad = 20;`.
- **const:** También introducido en ES6, se usa para declarar **constantes**, es decir, variables cuyo valor no debe cambiar una vez asignado. Al igual que `let`, `const` tiene ámbito de bloque y no permite redeclaración. Además, una `const` **debe inicializarse** en el momento de su declaración. Ejemplo: `const PI = 3.1416;`.

**Resumen – Diferencias entre var, let y const:**

- **Ámbito (scope):** `var` tiene ámbito global (si se declara fuera de funciones) o de función (si se declara dentro de una función), mientras que `let` y `const` tienen ámbito de bloque (delimitado por `{}`).
- **Redeclaración:** Con `var` es posible redeclarar la misma variable en el mismo ámbito sin error (lo cual puede causar confusiones). Con `let` y `const` no se puede declarar dos veces una variable con el mismo nombre en el mismo bloque; el intentar hacerlo produce un error.
- **Reasignación:** Las variables declaradas con `var` o `let` pueden reasignar su valor (ej: hacer `edad = 21;` después de `let edad = 20;`). Las declaradas con `const` **no pueden** reasignarse; el valor queda fijo (aunque si ese valor es un objeto o array, sus *propiedades o elementos internos* sí podrían modificarse, pero no se puede cambiar la referencia del objeto).
- **Hoisting:** Todas las declaraciones (`var`, `let`, `const`) son "hoisted" (elevadas al inicio del ámbito durante la compilación interna), pero con diferencias. Las variables `var` quedan inicializadas con `undefined` en un principio, por eso si accedemos a una variable `var` antes de su línea de declaración no da error (aunque su valor será `undefined`, lo cual no es deseable). En cambio, las variables `let` y `const` no están disponibles antes de su declaración (esto se llama **Temporal Dead Zone**); si intentamos usarlas antes de la línea donde se declaran, obtendremos un error de referencia. En buenas prácticas, siempre declararemos las variables antes de usarlas, así que normalmente no tendremos que preocuparnos de esto.

**Buenas prácticas:** En código moderno se recomienda usar `const` por defecto para todas las variables que no necesiten reasignarse, y usar `let` solo cuando sepamos que el valor va a cambiar. El uso de `var` se reserva para casos especiales o por compatibilidad con código antiguo.

Veamos ejemplos de declaración de variables:

```js
// Declaración de variables usando let
let nombre = "Carlos";    // variable tipo cadena (string)
let edad = 25;            // variable tipo número (number)
let isStudent = true;     // variable booleana (true/false)

// Podemos declarar múltiples variables a la vez
let x = 5, y = 10, z;     // z se declara pero queda undefined (sin valor asignado)

console.log(nombre);      // Imprime "Carlos" en la consola
console.log(x + y);       // Imprime 15

// Declaración de una constante
const PI = 3.14159;
console.log("El valor de PI es " + PI); // "El valor de PI es 3.14159"

// PI = 3.15;  <-- Esto produciría un error porque PI es constante

// Ejemplo de var (no recomendado, solo para ilustrar)
var mensaje = "Hola";
console.log(mensaje); // "Hola"
var mensaje = "Adiós";
console.log(mensaje); // "Adiós"  (con var se pudo redeclarar la misma variable mensaje)
```

En el ejemplo anterior, notamos que `nombre`, `edad`, `isStudent`, `x`, `y` y `z` fueron declaradas con `let`. La variable `z` no recibió un valor inicial, por lo que si tratamos de usarla obtendremos `undefined`. Luego definimos `PI` como constante. Intentar asignar otro valor a `PI` generaría un error. También se muestra cómo `var` permite redeclarar `mensaje` sin error, cosa que con `let` o `const` no podríamos hacer (el intérprete lanzaría un `SyntaxError` si intentáramos `let mensaje = "Adiós";` después de `let mensaje = "Hola";` en el mismo bloque).

### Tipos de datos primitivos

JavaScript maneja diferentes **tipos de datos**. Los tipos *primitivos* (básicos) en JavaScript son:

- **Número (Number):** Representa tanto enteros como decimales. Ejemplos: `42`, `3.14`, `-8`. En JavaScript, todos los números (excepto los BigInt) se manejan como *números de coma flotante de doble precisión* (formato IEEE 754). También hay valores numéricos especiales: `Infinity` (infinito, por ejemplo el resultado de 1/0), `-Infinity`, y `NaN` (*Not a Number*, que indica un resultado matemático inválido, por ejemplo `0/0` o intentar convertir a número algo que no tiene formato numérico).
- **Cadena de texto (String):** Es una secuencia de caracteres, usada para representar texto. Se puede definir con comillas dobles `"texto"`, comillas simples `'texto'`, o **backticks** \` (acento grave). Ejemplos: `"Hola"`, `'JavaScript'`. Las comillas dobles o simples funcionan igual, solo deben venir en pares iguales. Las **comillas invertidas (backticks)** permiten además interpolar variables o expresiones dentro de la cadena usando la sintaxis `${...}` (a estos se les llama *template strings* o plantillas literales). Ejemplo: `` let saludo = `Hola, ${nombre}`; `` pondrá en `saludo` el texto "Hola, Carlos" si la variable `nombre` vale `"Carlos"`.
- **Booleano (Boolean):** Representa valores lógicos `true` (verdadero) o `false` (falso). Suele usarse en condiciones y comparaciones.
- **Null:** Es un valor especial que indica "ausencia intencional de cualquier valor". Es decir, podemos asignar `null` a una variable para indicar que está vacía o sin valor por elección. `null` es un literal (tipo primitivo) en JS.
- **Undefined:** Indica que algo **no está definido**. Una variable declarada a la que no se le ha asignado valor tiene el valor `undefined` automáticamente. También, si una función no retorna nada, su resultado es `undefined`. Es diferente de `null`: `null` lo asigna el programador para indicar "sin valor", `undefined` lo asigna JavaScript para indicar "no inicializado" o "no existe".
- **BigInt:** Es un tipo numérico especial introducido en ES2020 para representar enteros de tamaño arbitrario (muy grandes) que no pueden representarse con el tipo Number (que tiene un máximo alrededor de 1.8e308 y precisión de 53 bits para enteros). Se define agregando una `n` al final de un número entero. Ejemplo: `let granNumero = 9007199254740993n;`. Para operaciones aritméticas entre BigInt, ambos operandos deben ser BigInt.
- **Symbol:** Introducido en ES6, los símbolos son valores únicos que se suelen usar como identificadores únicos. Cada símbolo creado es diferente de cualquier otro, incluso si tienen la misma descripción. Se crean con `Symbol("descripcion")`. Son un tipo más avanzado y menos común en programación básica, así que no profundizaremos aquí.

Además de estos tipos primitivos, existe el **tipo Objeto (Object)**, que no es primitivo. Los objetos son colecciones de pares clave-valor y los veremos en detalle más adelante (incluyendo arrays, funciones y otros que en JavaScript son tratados como objetos). 

Es importante notar que JavaScript es de **tipado dinámico**: las variables no tienen un tipo fijo, y una misma variable puede contener primero un número, luego una cadena, etc. El tipo está asociado al *valor*, no a la variable. Podemos verificar el tipo de un valor o variable usando el operador `typeof`. 

Ejemplos de distintos tipos y `typeof`:

```js
let a = 10;
console.log(typeof a); // "number"

a = "Ahora soy un texto";
console.log(typeof a); // "string"

let b;
console.log(typeof b); // "undefined" (b está declarada pero sin valor)

let c = null;
console.log(typeof c); // "object"  (dato curioso: por un legado histórico, typeof null da "object")

let d = true;
console.log(typeof d); // "boolean"

let e = 123n;
console.log(typeof e); // "bigint"

let f = Symbol("desc");
console.log(typeof f); // "symbol"
```

En el ejemplo anterior, se ve cómo la misma variable `a` pasó de ser número a cadena sin problemas. También notamos que `typeof null` retorna "object" debido a una particularidad del lenguaje (aunque null no es un objeto, sino un tipo especial primitivo, `typeof` lo identifica erróneamente así; es un detalle que a veces causa confusión, simplemente recordemos que null es "vacío"). 

**Valores "truthy" y "falsy":** En JavaScript, al usar valores en contextos lógicos (por ejemplo en un `if`), los tipos se convierten a booleano implícitamente. Algunos valores se consideran verdaderos (*truthy*) y otros falsos (*falsy*). Los valores **falsy** (que cuentan como `false` en un booleano) son: `false`, `0` (y -0), `""` (cadena vacía), `null`, `undefined`, y `NaN`. Cualquier otro valor (incluyendo cadenas no vacías, números distintos de 0, objetos, arrays vacíos, etc.) son **truthy** (se evalúan como true). Ejemplo: `if ("hola") { ... }` se ejecutará porque "hola" es truthy, mientras que `if (0) { ... }` no se ejecutará porque 0 es falsy.

### Conversión de tipos (casting)

A veces necesitaremos convertir de un tipo a otro manualmente:

- **A número:** Podemos usar las funciones `Number(valor)`, `parseInt(cadena)` o `parseFloat(cadena)` para convertir cadenas a números. `Number("10")` devuelve 10 (number), `Number("10.5")` devuelve 10.5. `parseInt("10px")` devolverá 10 (intenta extraer un entero inicial de la cadena), `parseFloat("3.14es")` devolverá 3.14. Si la conversión falla, `Number` devuelve `NaN`. También podemos usar el operador unario `+` antes de una cadena para intentar convertirla a número: por ejemplo, `+"123"` resulta en número 123.
- **A string:** Usando la función `String(valor)` o llamando al método `.toString()` de un valor (si existe). Por ejemplo, `String(123)` produce `"123"`. Sumarle una cadena vacía también convierte a string: `valor + ""`. Otra forma más moderna es usar *template strings*: `` `${valor}` `` produce una cadena con la representación de `valor`.
- **A booleano:** Casi cualquier valor se convierte a booleano en un contexto lógico automáticamente (siguiendo la regla de truthy/falsy mencionada). Pero explícitamente, se puede usar `Boolean(valor)` para obtener el booleano equivalente.

**Ejemplos de conversión:**

```js
let numStr = "45";
let num = Number(numStr);         // num = 45 (number)
let num2 = +"7.5";                // num2 = 7.5 (number) usando + unario
let cadena = String(100);         // cadena = "100"
let cadena2 = 200..toString();    // cadena2 = "200" (nota: 200.. para poder acceder al método toString del número)
let truth = Boolean(1);           // truth = true (1 es truthy)
let falsedad = Boolean("");       // falsedad = false ("" es falsy)
```

En general, JavaScript hace **coerciones de tipo implícitas** en algunas operaciones. Por ejemplo, al sumar un número y una cadena, el número se convertirá a cadena automáticamente (concatenación). Al usar el operador `==` (igualdad no estricta), si los operandos son de distinto tipo, JavaScript intentará convertir uno al tipo del otro para compararlos, lo que puede llevar a resultados inesperados. Por eso es mejor usar siempre la igualdad estricta `===`, que no hace conversiones implícitas (veremos más en la sección de Operadores).

### Ejercicios

1. **Variables y tipos básicos:** Declara variables usando `let` o `const` para almacenar los siguientes valores: tu nombre, tu edad, una calificación booleana que indique si eres estudiante, y una variable sin asignarle valor. Imprime cada una en la consola con `console.log` indicando su tipo (puedes usar `typeof`). Por ejemplo: "nombre: ... tipo: ...".
2. **Conversión de temperatura:** Escribe un programa que convierta una temperatura dada en grados Celsius a grados Fahrenheit. Declara una variable para la temperatura en Celsius, luego calcula la Fahrenheit con la fórmula `F = C * 9/5 + 32` y muestra el resultado. Por ejemplo, 20°C debería convertirse a 68°F.
3. **Intercambio de valores:** Declara dos variables `a` y `b` con valores iniciales (números o cadenas). Luego, escribe código para **intercambiar** los valores de manera que lo que estaba en `a` pase a `b` y viceversa. Muestra los valores antes y después del intercambio. *(Pista: puedes usar una variable auxiliar temporal o aprovechar es6 con sintaxis de desestructuración: `[a, b] = [b, a]`.)*
4. **Coerción inesperada:** ¿Qué valores crees que resultan de las siguientes expresiones? (Escríbelos en código o papel y luego compruébalos en la consola):
   - `"5" + 3`  
   - `"5" - 3`  
   - `true + 2`  
   - `false + "hola"`  
   - `0 == "0"` vs `0 === "0"`  
   Explica brevemente por qué obtienes esos resultados (qué conversiones implícitas ocurrieron en cada caso).
5. **Constantes y error:** Crea una constante `MI_EDAD` con tu edad como número. Luego, intenta asignarle otro valor a esa constante (por ejemplo `MI_EDAD = MI_EDAD + 1`). Abre la consola y observa qué sucede. ¿Qué tipo de error arroja?

---

## Operadores en JavaScript

Los **operadores** son símbolos que nos permiten realizar operaciones con los valores (operandos). JavaScript tiene operadores aritméticos, de asignación, de comparación, lógicos, entre otros. Veamos los más importantes:

### Operadores aritméticos

Estos operadores realizan operaciones matemáticas básicas:

- `+` **Suma** (también sirve para concatenar cadenas). Ej: `5 + 3` resulta `8`. `"Hola" + " Mundo"` resulta `"Hola Mundo"`.
- `-` **Resta.** Ej: `10 - 4` resulta `6`.
- `*` **Multiplicación.** Ej: `6 * 7` resulta `42`.
- `/` **División.** Ej: `20 / 5` resulta `4`.
- `%` **Módulo** (residuo de división). Ej: `7 % 3` resulta `1` (ya que 7 dividido 3 es 2 con residuo 1). Útil para determinar si un número es par (n % 2 == 0) o impar, etc.
- `**` **Exponenciación** (potencia). Ej: `2 ** 3` resulta `8` (2 elevado a 3). *Nota:* En versiones antiguas de JS se usaba `Math.pow(2,3)` para 2^3.
- `++` **Incremento** (suma 1). Puede usarse en forma **postfija** `i++` (retorna el valor original y luego incrementa) o **prefija** `++i` (incrementa primero y retorna el valor incrementado). Ej: `let i=5; console.log(i++);` muestra 5 pero luego i vale 6; en cambio `let j=5; console.log(++j);` muestra 6 y j vale 6.
- `--` **Decremento** (resta 1). Análogo al incremento, en forma postfija `j--` o prefija `--j`.

Ejemplos:

```js
let a = 10, b = 3;
console.log(a + b);    // 13
console.log(a - b);    // 7
console.log(a * b);    // 30
console.log(a / b);    // 3.333...
console.log(a % b);    // 1  (residuo de 10/3)
console.log(2 ** 4);   // 16 (2^4)
a++;                   // ahora a es 11 (post-incremento)
console.log(a);        // 11
++b;                   // pre-incremento, b pasa de 3 a 4
console.log(b);        // 4
```

### Operadores de asignación

Sirven para asignar valores a variables. El operador básico es `=` (asignación simple). Además hay operadores de asignación combinados con aritmética:

- `=` **Asignación:** `x = 5` asigna el valor 5 a x.
- `+=` **Asignación aditiva:** `x += 3` es equivalente a `x = x + 3`.
- `-=` **Asignación sustractiva:** `x -= 2` es equivalente a `x = x - 2`.
- `*=` **Asignación multiplicativa:** `x *= 4` es `x = x * 4`.
- `/=` **Asignación divisiva:** `x /= 2` es `x = x / 2`.
- `%=` **Asignación de módulo:** `x %= 5` es `x = x % 5`.
- `**=` **Asignación de potencia:** `x **= 3` es `x = x ** 3` (eleva x a la 3).

Ejemplo:

```js
let n = 10;
n += 5;  // n = n + 5, ahora n vale 15
n *= 2;  // n = n * 2, ahora n vale 30
console.log(n); // 30
```

### Operadores de comparación

Estos operadores comparan dos valores y devuelven un booleano (`true` o `false`) dependiendo de la relación:

- `==` **Igualdad débil (no estricta):** Devuelve true si los valores son iguales, **después** de realizar conversión de tipo si son distintos. Ej: `5 == "5"` es `true` (la cadena "5" se convierte a número 5 para comparar). **No recomendado** por posibles confusiones.
- `===` **Igualdad estricta:** Devuelve true si los valores son exactamente iguales **y del mismo tipo**. Ej: `5 === "5"` es `false` (porque uno es número y otro cadena, no hay conversión implícita). Siempre que comparemos dos valores, es mejor usar `===` para evitar sorpresas.
- `!=` **Desigualdad débil:** Verdadero si los valores son diferentes (haciendo conversión de tipos si es necesario). Ej: `5 != "7"` es true (5 != 7).
- `!==` **Desigualdad estricta:** Verdadero si los valores son diferentes **o** de distinto tipo. Ej: `5 !== "5"` es true (aunque 5 == "5" sería true, pero al ser estricto, los tipos difieren).
- `>` **Mayor que:** True si el operando izquierdo es mayor que el derecho. Ej: `7 > 3` es true.
- `<` **Menor que:** True si izquierdo es menor que derecho. Ej: `7 < 3` es false.
- `>=` **Mayor o igual:** True si izquierdo es mayor o igual a derecho. Ej: `3 >= 3` es true.
- `<=` **Menor o igual:** True si izquierdo es menor o igual a derecho. Ej: `5 <= 8` es true.

Ejemplos:

```js
console.log(5 == "5");   // true  (evitar ==, aquí hace conversión implícita)
console.log(5 === "5");  // false (distinto tipo)
console.log(0 == false); // true  (0 es falsy, se considera igual a false)
console.log(0 === false);// false (0 es number, false es boolean)
console.log(4 != "4");   // false (son equivalentes tras conversión)
console.log(4 !== "4");  // true  (distinto tipo)
console.log(10 > 2);     // true
console.log(10 < 2);     // false
console.log(5 >= 5);     // true
console.log(6 <= 5);     // false
```

**¡Atención con `==` y `===`!** El operador `==` puede llevar a resultados inesperados debido a la conversión automática. Por ejemplo, `"0" == false` es true, porque `"0"` se convierte a 0 y 0 es falsey. En general, **usa `===`** a menos que tengas una razón específica para usar `==`. Lo mismo aplica para `!=` (usar mejor `!==`).

### Operadores lógicos

Se usan para combinar o invertir expresiones booleanas:

- `&&` **AND (Y lógico):** `expr1 && expr2` es true solo si **ambas** expresiones son true. Si la primera es false, ya no evalúa la segunda (técnica *short-circuit*).
- `||` **OR (O lógico):** `expr1 || expr2` es true si **al menos una** de las expresiones es true. Si la primera es true, no evalúa la segunda (short-circuit).
- `!` **NOT (negación lógica):** `!expr` es true si `expr` es false, y viceversa. Invierte el valor booleano.

Estas expresiones también admiten operandos no booleanos (usando las reglas de truthy/falsy). Además, debido al *short-circuit*, pueden usarse para proporcionar valores por defecto. Por ejemplo, `let resultado = valor || "Por defecto";` asignará "Por defecto" a resultado solo si `valor` es falsy (null, undefined, "", 0, etc.), en caso contrario asigna `valor`.

Ejemplos:

```js
let a = 5, b = 0;
console.log(a > 0 && b > 0);    // false (b > 0 es false, así que todo es false)
console.log(a > 0 || b > 0);    // true  (a > 0 es true, OR da true sin evaluar b>0)
console.log(!(a > 0));          // false (a > 0 es true, negado es false)

let nombreUsuario;
let nombreMostrar = nombreUsuario || "Invitado";
console.log(nombreMostrar);     // "Invitado", porque nombreUsuario es undefined (falsy)

let x = 10;
(x > 5) && console.log("x es mayor que 5"); 
// En este último ejemplo, como x > 5 es true, se evalúa la segunda parte y se ejecuta el console.log.
```

### Otros operadores útiles

- **Operador ternario (condicional):** Tiene la forma `condicion ? expr_si_true : expr_si_false`. Es una forma condensada de un if/else simple que produce un valor. Ej: `let estado = (edad >= 18) ? "Adulto" : "Menor";`.
- **Operador coma (,):** Permite evaluar múltiples expresiones en una sola instrucción, devolviendo el valor de la última. No es muy usado salvo en casos específicos.
- **typeof:** (ya mencionado) devuelve el tipo de un operando en forma de cadena.
- **delete:** Se usa para eliminar propiedades de un objeto (lo veremos en Objetos).
- **new:** Operador para crear instancias de objetos/clases.
- **instanceof:** Verifica si un objeto es instancia de cierta clase. Ej: `obj instanceof Array` es true si obj fue creado con Array.
- **spread ... (operador de propagación)** y **rest ...**: Son los tres puntos `...` que sirven para expandir arreglos/objetos o reunir parámetros, respectivamente. (Los explicaremos un poco en las secciones de Arrays y Funciones).

### Ejercicios

1. **Operaciones matemáticas:** Crea un archivo JS y define variables `a = 8`, `b = 5`. Calcula e imprime (con `console.log`) los resultados de: suma, resta, multiplicación, división, módulo y exponenciación (`a^b`). Luego incrementa la variable `a` en 1 usando `++` y disminuye `b` en 1 usando `--`, imprimiendo los nuevos valores.
2. **Comparaciones:** Declara dos variables numéricas `x` e `y` con valores distintos. Escribe expresiones que comprueben: si `x` es mayor que `y`, si son iguales (estrictamente), si `x` no es igual a `y` (estricto). Imprime el resultado de cada comparación. Luego asigna a `y` una cadena con el mismo valor numérico que tenía antes (por ejemplo, si y era 5, ahora `y = "5"`), y compara `x == y` y `x === y` explicando la diferencia.
3. **Par o impar:** Pide al usuario (con `prompt`) un número entero e infórmale con un `alert` si es par o impar. Para saberlo, puedes usar el operador `%` y comprobar si `numero % 2 === 0`.
4. **Acceso condicional:** Declara una variable `nivel` con un valor numérico del 1 al 5. Usando el operador ternario, asigna a una variable `acceso` el valor `"Permitido"` si `nivel` es mayor o igual a 3, o `"Denegado"` si es menor. Imprime `acceso`.
5. **Lógica booleana:** Declara 3 variables booleanas: `estaLloviendo`, `tieneParaguas`, `vaATrabajar`. Asigna valores true/false según escenarios (por ejemplo: está lloviendo, tiene paraguas, va a trabajar). Luego, utilizando operadores lógicos, determina si la persona *puede salir* (por ejemplo, puede salir si no está lloviendo **o** si está lloviendo **pero** tiene paraguas). Experimenta diferentes combinaciones y muestra el resultado (true/false) de tus condiciones en la consola.

---

## Estructuras de Control de Flujo

Las estructuras de control permiten desviar el flujo de ejecución de las instrucciones, ya sea para tomar decisiones (condicionales) o repetir bloques de código (bucles). JavaScript ofrece las típicas estructuras presentes en muchos lenguajes: `if/else`, `switch` para decisiones, y `for`, `while`, `do...while` para bucles, entre otras.

### Condicionales: `if`, `else` y `switch`

**if/else:** La estructura `if` ejecuta un bloque de código solo si una condición booleana es verdadera. Opcionalmente puede incluir un bloque `else` (sino) que se ejecuta si la condición es falsa. También se pueden encadenar múltiples condiciones usando `else if`. Formato básico:

```js
if (condicion) {
  // código si condicion es true
} else {
  // código si condicion es false
}
```

Y con else if:

```js
if (condicion1) {
  // si condicion1 es true
} else if (condicion2) {
  // si condicion1 es false *y* condicion2 es true
} else {
  // si ninguna de las condiciones anteriores fue true
}
```

La condición es usualmente una comparación o expresión booleana. Ejemplo:

```js
let edad = 18;
if (edad >= 18) {
  console.log("Eres mayor de edad");
} else {
  console.log("Eres menor de edad");
}

// Ejemplo con else if:
let nota = 75;
if (nota >= 90) {
  console.log("Calificación: A");
} else if (nota >= 80) {
  console.log("Calificación: B");
} else if (nota >= 70) {
  console.log("Calificación: C");
} else if (nota >= 60) {
  console.log("Calificación: D");
} else {
  console.log("Calificación: F");
}
```

En el ejemplo, dependiendo del valor de `nota`, se imprime una calificación. Solo uno de los bloques se ejecutará, el primero cuyo `if` o `else if` resulte verdadero.

**switch:** Es otra estructura condicional útil cuando se quiere comparar el mismo valor contra distintas posibilidades (casos). Evita escribir muchos `else if`. Su sintaxis:

```js
switch(expresion) {
  case valor1:
    // código si expresion === valor1
    break;
  case valor2:
    // código si expresion === valor2
    break;
  default:
    // código si ninguno de los casos anteriores coincide
}
```

El flujo entra en el `case` que coincida con la expresión dada y ejecuta las instrucciones a partir de ahí. La instrucción `break` es importante para que el flujo salga del switch después de ejecutar el caso correspondiente; sin `break`, la ejecución *continuaría* con los siguientes casos (comportamiento llamado *fall-through*), lo cual solo se desea en situaciones específicas. El bloque `default` es opcional y se ejecuta si ningún caso coincide.

Ejemplo de uso de `switch`:

```js
let opcion = 2;
switch(opcion) {
  case 1:
    console.log("Elegiste el opción 1");
    break;
  case 2:
    console.log("Elegiste el opción 2");
    break;
  case 3:
    console.log("Elegiste el opción 3");
    break;
  default:
    console.log("Opción no válida");
}
```

Si `opcion` vale 2, se ejecutará el código del `case 2`. Si la variable contiene un valor distinto de 1,2,3, se ejecutará el `default`. 

Ten en cuenta que `switch` usa comparación estricta (`===`) para comparar la expresión con cada `case`. Por lo tanto, si la expresión es una cadena `"5"` y uno de los casos es el número `5`, no coincidirán. Asegúrate de que los tipos concuerden o convierte la expresión previamente.

### Bucles (loops): `for`, `while`, `do...while`

Los bucles nos permiten repetir un bloque de código varias veces, ya sea un número determinado de veces o mientras se cumpla cierta condición.

**Bucle for (para):** Se usa típicamente cuando conocemos de antemano cuántas iteraciones queremos realizar (por ejemplo, recorrer un rango de números o iterar sobre un array con índice). La sintaxis del `for` incluye tres partes: inicialización; condición de continuación; actualización. Por ejemplo:

```js
for (inicializacion; condicion; actualizacion) {
  // bloque de código a repetir
}
```

- La **inicialización** suele declarar e inicializar una variable de control (p.ej., `let i = 0`).
- La **condición** se evalúa antes de cada iteración; mientras sea true, el bucle continúa. Cuando sea false, el bucle termina.
- La **actualización** se ejecuta al final de cada iteración, usualmente para cambiar el valor de la variable de control (p.ej., `i++`).

Ejemplo clásico: imprimir números del 1 al 5:

```js
for (let i = 1; i <= 5; i++) {
  console.log("Número: " + i);
}
// Salida: 
// Número: 1
// Número: 2
// ...
// Número: 5
```

En cada iteración, `i` toma los valores 1,2,3,4,5 secuencialmente. Al llegar a 6, la condición `i <= 5` falla y el bucle termina.

**Bucle while (mientras):** Repite un bloque **mientras** una condición sea verdadera. Es útil cuando no sabes cuántas iteraciones se necesitarán, y en su lugar dependes de una condición para parar.

```js
while (condicion) {
  // código a ejecutar repetidamente
}
```

Antes de cada repetición, evalúa la condición; si es true, ejecuta el bloque y vuelve a comprobar; si es false de entrada, no entra ni una vez.

Ejemplo: usar while para contar hacia atrás:

```js
let cuenta = 5;
while (cuenta > 0) {
  console.log(cuenta);
  cuenta--;  // decrementamos para evitar bucle infinito
}
console.log("Despegue!");

// Salida: 5,4,3,2,1 luego "Despegue!"
```

Si no se modifica la variable dentro del while de modo que eventualmente la condición sea false, obtendríamos un **bucle infinito** (la condición nunca se vuelve falsa, y el loop no termina). Por eso es importante actualizar las variables implicadas en la condición dentro del bucle.

**Bucle do...while:** Similar a `while`, pero garantiza al menos **una** ejecución del bloque, ya que la condición se evalúa **después** de ejecutar el bloque. Sintaxis:

```js
do {
  // código que se ejecuta al menos una vez
} while (condicion);
```

Ejemplo:

```js
let valor = 0;
do {
  console.log("Valor es " + valor);
  valor--;
} while (valor > 0);

// En este caso, aunque la condición inicial (valor > 0) es false desde el comienzo (valor=0 no es >0), 
// el bloque se ejecuta una vez, imprimiendo "Valor es 0".
```

**for...of:** ES6 introdujo una forma simplificada de iterar sobre elementos de una colección (como un array) sin tener que manejar índices manualmente. `for...of` itera sobre los *valores* de un objeto iterable (arrays, strings, mapas, etc.):

```js
let numeros = [10, 20, 30];
for (let num of numeros) {
  console.log(num);
}
// Salida: 10, 20, 30 (imprime cada valor del array)
```

Lo veremos más a fondo al hablar de Arrays, pero conviene saber que existe esta sintaxis más simple para ciertos casos.

**for...in:** Este iterador recorre las **propiedades enumerables** de un objeto. En arrays también iterará por sus índices (como cadenas "0", "1", ...). Se suele usar más para objetos, como veremos en la sección de Objetos. Ejemplo rápido: 

```js
let persona = { nombre: "Ana", edad: 30 };
for (let clave in persona) {
  console.log(clave + ": " + persona[clave]);
}
// Salida:
// nombre: Ana
// edad: 30
```

**Palabras clave `break` y `continue`:**

- `break`: Termina inmediatamente el bucle en curso. La ejecución salta a la primera línea después del bloque del bucle.
- `continue`: Salta a la siguiente iteración, omitiendo el resto del bloque actual. Es decir, vuelve a evaluar la condición/incremento sin completar las líneas que le siguen en el cuerpo del loop.

Ejemplo usando `break` y `continue`:

```js
// Buscar un número en un array y terminar cuando se encuentra
let numeros = [3, 7, 11, 15, 19];
let objetivo = 15;
for (let i = 0; i < numeros.length; i++) {
  if (numeros[i] === objetivo) {
    console.log("Encontrado", objetivo, "en índice", i);
    break;  // salimos del bucle for
  }
}

// Saltar números impares y solo imprimir pares
for (let j = 1; j <= 10; j++) {
  if (j % 2 !== 0) continue;  // si j es impar, ir a siguiente iteración
  console.log(j);  // esto solo se ejecuta cuando j es par
}
// Salida: 2, 4, 6, 8, 10
```

En el primer loop, usamos `break` para dejar de buscar una vez hallamos el número deseado, evitando iteraciones innecesarias. En el segundo, `continue` hace que para valores impares no se ejecute el `console.log`, pasando directamente al siguiente número.

### Ejercicios

1. **Positivo, Negativo o Cero:** Pídele al usuario (usando `prompt`) que ingrese un número. Usando un `if...else`, muestra mediante `alert` si el número es positivo, negativo o cero.
2. **Número mayor:** Escribe un programa que defina dos variables con números y use una estructura condicional (`if`/`else`) para imprimir cuál de los dos es mayor, o si son iguales.
3. **Días de la semana:** Utilizando `prompt`, pide al usuario un número del 1 al 7 que representa un día de la semana. Usando un `switch`, muestra en consola o alerta el nombre del día correspondiente (1->Lunes, 2->Martes, ..., 7->Domingo). Si el número no está en el rango 1-7, muestra un mensaje de error.
4. **Sumatoria con for:** Escribe un programa que calcule la suma de los números del 1 al 100 usando un bucle `for`. (Debería resultar 5050).
5. **Factorial:** Crea una página con un `prompt` que le pida al usuario un número entero positivo, y mediante un loop `for` o `while`, calcula el factorial de ese número (n! = 1*2*3*...*n). Muestra el resultado con `alert` o en consola. (Asegúrate de manejar el caso de 0!, que por definición es 1).
6. **Adivinar el número (while):** Escribe un código que genere un número aleatorio del 1 al 10 (pista: `Math.floor(Math.random()*10)+1`) y luego use un bucle `while` para pedir al usuario que adivine el número (usando prompt en cada iteración). Si el usuario adivina, felicítalo y termina; si no, infórmale si su conjetura es mayor o menor que el número secreto y pide otro intento. (Ten cuidado de convertir la entrada de prompt a Number).
7. **Tabla de multiplicar (do...while):** Pídele al usuario un número del 1 al 10. Luego, usando un `do...while`, muestra la tabla de multiplicar de ese número (es decir, multiplicarlo por 1,2,...10). Asegúrate de que se ejecute al menos una vez incluso si el usuario ingresara, por ejemplo, un número fuera de rango (en cuyo caso podrías romper el bucle con un break tras una iteración).
8. **Números primos:** (Ejercicio desafiante) Escribe un programa que imprima en la consola todos los números primos entre 2 y 100. Para ello puedes usar anidados un `for` dentro de otro: el externo itera de 2 a 100, y el interno verifica si el número actual tiene algún divisor entre 2 y sqrt(n). Si no tiene divisores, es primo.

---

## Funciones en JavaScript

Una **función** es un bloque de código reutilizable que realiza una tarea específica. Podemos definir una función, darle un nombre (opcional si es anónima) y luego "invocarla" o "llamarla" para ejecutar ese código cuando lo necesitemos, incluso múltiples veces con diferentes datos. Las funciones pueden recibir **parámetros** (datos de entrada) y pueden **retornar** un resultado.

### Declaración y llamada de funciones

La forma clásica de declarar una función es:

```js
function nombreFuncion(param1, param2, ...) {
  // bloque de código
  // opcionalmente, retornar un valor con return
}
```

- **nombreFuncion** es el identificador de la función (siguiendo las mismas reglas de nomenclatura que las variables).
- **param1, param2, ...** son parámetros que la función espera recibir (pueden usarse como variables dentro del bloque).
- Dentro del cuerpo, podemos usar los parámetros y definir variables locales.
- Si la función debe dar un resultado, se usa la palabra clave `return` seguida de la expresión a retornar. Si no se pone `return`, la función retornará `undefined` por defecto cuando se invoque.

Ejemplo simple:

```js
function saludar(nombre) {
  console.log("Hola, " + nombre + "!");
}

saludar("María");  // Llama a la función con el argumento "María". Imprime "Hola, María!"
saludar("Juan");   // Imprime "Hola, Juan!"
```

La función `saludar` toma un parámetro `nombre` y cada vez que se invoca, muestra un saludo personalizado. Observa cómo la reutilización evita escribir console.log varias veces.

Ejemplo con retorno:

```js
function sumar(a, b) {
  let resultado = a + b;
  return resultado;
}

let suma1 = sumar(5, 3);      // suma1 recibe 8
let suma2 = sumar(10, -2);    // suma2 recibe 8
console.log(suma1, suma2);    // "8 8"
console.log(sumar(1, 2) + 5); // Podemos usar directamente la función en una expresión, aquí imprime 8 (3 + 5)
```

Aquí la función `sumar` devuelve la suma de sus dos parámetros. Usamos `return` para enviar el resultado al código que la llamó.

**Parámetros y argumentos:** Los *parámetros* son las variables definidas en la declaración de la función. Los *argumentos* son los valores concretos que pasamos al llamar a la función. En JavaScript no es un error llamar a una función con menos o más argumentos de los que espera:
- Si pasas **menos** argumentos, los parámetros faltantes tendrán valor `undefined`.
- Si pasas **más** argumentos, los extras serán simplemente ignorados (aunque dentro de la función hay formas de acceder a todos los argumentos mediante `arguments` o parámetros rest, que comentaremos luego).

**Parámetros por defecto:** Podemos asignar valores por defecto a los parámetros para que tomen ese valor si el argumento correspondiente está ausente o es `undefined` al llamar. Ejemplo:

```js
function elevar(base, exponente = 2) {
  // Si no se pasa exponente, tomará 2 (elevar al cuadrado por defecto)
  return base ** exponente;
}
console.log(elevar(5));    // 25 (5^2)
console.log(elevar(5, 3)); // 125 (5^3)
```

En `elevar`, si no damos el segundo argumento, `exponente` será 2 por defecto.

**Funciones que no retornan nada explícitamente:** Como mencionamos, retornan `undefined`. Por ejemplo:

```js
function imprimirMensaje(msg) {
  console.log("Mensaje: " + msg);
}
let x = imprimirMensaje("Probando");
console.log(x); // undefined, ya que la función no retornó algo
```

### Expresiones de función y funciones anónimas

Además de la declaración clásica, podemos definir funciones como **expresiones** y asignarlas a variables. Ejemplo:

```js
const multiplicar = function(x, y) {
  return x * y;
};
console.log(multiplicar(4, 3)); // 12
```

Aquí no nombramos la función (es *anónima*), sino que la asignamos a la constante `multiplicar`. A partir de ahí, podemos usar `multiplicar(...)` para llamarla. Funciona igual que si hubiésemos declarado `function multiplicar(x,y) { ... }`, con la diferencia de que la función expresada de esta forma no existe hasta que la línea de asignación se ejecuta (no hay *hoisting* completo del nombre `multiplicar` como ocurre con la declaración clásica, donde podemos invocar la función incluso antes de su definición en el código fuente debido a hoisting).

También podemos definir funciones dentro de otras funciones o pasar funciones como argumentos a otras (lo cual nos lleva al concepto de *callbacks* que veremos más adelante). En JavaScript, las funciones son ciudadanos de primera clase, es decir, se tratan como cualquier otro valor: pueden almacenarse en variables, pasarse a funciones, retornarse de funciones, etc.

### Ámbito (scope) de las variables en funciones

Las variables declaradas **dentro** de una función (con `var`, `let` o `const`) tienen **ámbito local** a esa función. No se pueden acceder desde fuera de la función; existen solo durante la ejecución de esa llamada a la función. Distinto es el caso de variables definidas fuera, en el **ámbito global** o en ámbitos superiores: una función puede leer (y modificar, si no son constantes) variables globales o de su entorno externo (clausuras), aunque eso no es siempre buena práctica porque puede generar dependencias ocultas. En general, conviene preferir pasar valores como parámetros y retornar resultados.

Ejemplo ilustrando scope:

```js
let m = 5;
function ejemplo() {
  let m = 10;
  console.log("Dentro de la función, m =", m);
}
ejemplo();  
console.log("Fuera de la función, m =", m);

// Salida:
// Dentro de la función, m = 10
// Fuera de la función, m = 5
```

Aquí la variable `m` fuera de la función permanece con valor 5. Dentro de la función creamos otra variable `m` (con `let`, ámbito local a la función) que sombreó a la global mientras duró la función. Al terminar, la `m` local desaparece. Si en lugar de `let m = 10;` hubiéramos simplemente hecho `m = 10;` dentro de la función (sin declarar una nueva variable local), entonces se estaría modificando la variable global `m` (esto es posible pero generalmente hay que tener cuidado al modificar variables externas dentro de funciones).

**Hoisting en funciones:** Las **declaraciones de función** (usando `function nombre() {}`) son "hoisted" enteras, es decir, puedes llamar a la función incluso antes de su aparición en el código, porque el intérprete las registra al inicio. Sin embargo, las funciones definidas como expresión (asignadas a variables) no se pueden usar antes de la línea donde se definen, porque en ese caso estarías accediendo a la variable antes de su inicialización (dará error con `let/const` o undefined con `var`). Ejemplo:

```js
saludo(); // Esto funciona aunque la declaración esté abajo, por hoisting

function saludo() {
  console.log("Hola!");
}

try {
  multiplicacion(2,3); // Esto DARÁ ERROR porque multiplicacion es const, no inicializada aún
} catch(e) {
  console.log("Error:", e.message);
}
const multiplicacion = function(a, b) {
  return a * b;
};
```

### Funciones flecha (arrow functions)

Introducidas en ES6, las **arrow functions** son una sintaxis más compacta para escribir funciones anónimas. Hablaremos de ellas en detalle en una sección independiente más adelante, pero mencionamos aquí que son útiles para funciones cortas. Por ejemplo, la función expresada `const multiplicar = function(x,y){ return x*y; }` se puede escribir como `const multiplicar = (x,y) => x * y;` en una sola línea. Las arrow functions también tienen diferencias en cuanto al manejo del `this`, lo cual veremos luego.

### Ejercicios

1. **Funciones básicas:** Escribe una función `cuadrado(x)` que reciba un número y retorne el cuadrado de ese número. Prueba llamarla con varios valores y mostrando los resultados. Luego, escribe una función `saludo(nombre)` que retorne una cadena del tipo `"Hola, [nombre]"`. Úsala para saludar a tres nombres diferentes.
2. **Conversión de unidades:** Crea una función `celsiusAFahrenheit(c)` que convierta grados Celsius a Fahrenheit, y una función `fahrenheitACelsius(f)` para la conversión inversa. Fórmulas: F = C*9/5 + 32, C = (F-32)*5/9. Muestra en consola algunas conversiones de ejemplo (p.ej., 0°C a F, 100°C a F, 212°F a C, etc.).
3. **Número mayor con función:** Reutiliza la lógica del ejercicio "Número mayor" anterior, pero ahora encerrándola en una función `maximo(a, b)` que devuelva el mayor de dos números (o uno de ellos si son iguales). Invoca la función con diferentes pares de números para probarla.
4. **Función factorial:** Crea una función `factorial(n)` que calcule el factorial de un número entero `n` (recuerda: 0! = 1, y n! = n * (n-1) * ... * 1). Puedes hacerlo con un bucle `for` dentro o incluso usando recursividad (que es cuando una función se llama a sí misma, si ya has visto ese concepto). Prueba la función con varios valores (por ejemplo, factorial(5) = 120).
5. **Sumar arreglo:** Escribe una función `sumarArray(arr)` que reciba un arreglo de números y retorne la suma de todos sus elementos. Por ejemplo, `sumarArray([1,2,3,4])` debería devolver 10. Para recorrer el arreglo, puedes usar un `for` tradicional o un `for...of`. Prueba la función con distintos conjuntos de números.
6. **Ámbito local vs global:** Declara una variable global llamada `contador` e inicialízala en 0. Luego escribe una función `incrementarContador()` que incremente esa variable global en 1 cada vez que se llame. Llama a la función tres veces y luego muestra el valor de `contador`. Después, modifica la función para que use una variable local interna en lugar de la global (por ejemplo, declara `let contador = 0` dentro de la función y la incrementa), y observa cómo cambia el comportamiento al llamar varias veces. Explica la diferencia.

---

## Arrays (Arreglos)

Un **array** es una estructura que nos permite almacenar múltiples valores (de cualquier tipo) en una sola variable, organizados en un **orden** particular (por índice). En JavaScript, los arrays son objetos especiales que tienen propiedades y métodos útiles para manejar colecciones de datos.

### Creación y acceso a arrays

Se definen usando corchetes `[]` con los elementos separados por comas:

```js
let numeros = [10, 20, 30, 40];
let mezclado = [1, "dos", true, null]; // pueden tener distintos tipos
```

También se pueden crear con el constructor `Array`, aunque es menos usado: `let arr = new Array(5);` (crea un array de longitud 5 vacío).

Los arrays en JS son **de tamaño dinámico**, se pueden agregar o quitar elementos en tiempo de ejecución.

Cada elemento del array tiene un **índice** empezando desde 0. Para acceder a un elemento usamos la notación de corchetes con el índice:

```js
let frutas = ["Manzana", "Banana", "Cereza"];
console.log(frutas[0]); // "Manzana"
console.log(frutas[2]); // "Cereza"
```

Podemos asignar para cambiar un elemento existente o añadir uno nuevo:

```js
frutas[1] = "Mango";       // reemplaza "Banana" por "Mango"
frutas[3] = "Naranja";     // agrega "Naranja" como nuevo elemento en índice 3 (ahora el array tiene 4 elementos)
console.log(frutas);       // ["Manzana", "Mango", "Cereza", "Naranja"]
```

Si asignamos un índice mucho mayor que la longitud actual, el array se expandirá dejando posiciones vacías (undefined) en medio, pero esto raramente se necesita.

La **propiedad** `length` del array indica la cantidad de elementos que contiene:

```js
console.log(frutas.length); // 4
```

> **Nota:** `length` no necesariamente es el índice máximo + 1 siempre, pero en arrays no es asociativo (como en objetos) sino secuencial, así que generalmente sí lo es. Si se crean "agujeros" en el array con índices salteados, length será índice_más_alto + 1. También, modificar la propiedad length puede truncar o expandir el array (p.ej., `frutas.length = 2;` cortaría el array a los primeros 2 elementos).

### Recorrido de arrays

Para procesar todos los elementos de un array podemos usar un bucle. Los métodos comunes son:

- **for con índice:** usar un `for` tradicional iterando `i` desde 0 hasta `length-1`:

  ```js
  for (let i = 0; i < frutas.length; i++) {
    console.log(frutas[i]);
  }
  ```

- **for...of:** más moderno y legible para iterar directamente sobre valores:

  ```js
  for (let fruta of frutas) {
    console.log(fruta);
  }
  ```

- **forEach (método):** es un método del array que recibe una función *callback* y la ejecuta para cada elemento, pasando el elemento y opcionalmente el índice y el array completo:

  ```js
  frutas.forEach(function(elemento, indice) {
    console.log(indice, elemento);
  });
  // Esto imprimiría:
  // 0 "Manzana"
  // 1 "Mango"
  // 2 "Cereza"
  // 3 "Naranja"
  ```

  Veremos callbacks más adelante, pero ten en cuenta que `forEach` es útil para ejecutar algo con cada elemento.

### Métodos principales de arrays

JavaScript provee muchos métodos (funciones) que podemos invocar sobre arrays para manipularlos. Algunos de los más usados:

- **push(elemento):** Agrega `elemento` al **final** del array. Retorna la nueva longitud.
- **pop():** Remueve el **último** elemento del array y lo retorna.
- **unshift(elemento):** Agrega `elemento` al **inicio** del array (desplaza los existentes). Retorna la nueva longitud.
- **shift():** Remueve el **primer** elemento y lo retorna (desplaza hacia abajo los restantes).
- **indexOf(valor):** Retorna el índice de la primera ocurrencia de `valor` en el array, o -1 si no está. (Hay también `lastIndexOf` para buscar desde el final).
- **includes(valor):** Retorna true si el valor está en el array (usando igualdad estricta), false si no.
- **slice(inicio, fin):** Extrae una sección del array sin modificar el original. `inicio` es índice de inicio (inclusive), `fin` es índice final (exclusivo). Retorna un nuevo array con los elementos copiados. Si omites `fin`, toma hasta el final.
- **splice(inicio, cantidad, items...):** Modifica el array removiendo `cantidad` de elementos desde el índice `inicio`, y opcionalmente insertando otros `items` en ese lugar. Este es muy poderoso para inserciones/eliminaciones internas. Retorna los elementos removidos.
- **join(separador):** Une todos los elementos en una sola cadena, separándolos con el `separador` dado (por defecto coma). Ej: `["a","b","c"].join("-")` -> `"a-b-c"`.
- **reverse():** Invierte el orden del array *in place* (modifica el array).
- **sort(comparador?):** Ordena los elementos del array alfabéticamente (conversión a string por defecto) o numéricamente si se le pasa una función de comparación. *Cuidado:* modifica el array original.
- **concat(array2,...):** Retorna un nuevo array resultado de concatenar el array original con el/los que se indiquen (no modifica los originales).
- **map(función):** Retorna un nuevo array donde cada elemento es el resultado de aplicar la función dada al elemento correspondiente del array original. (Veremos funciones callback pronto, pero este es muy útil para transformar arrays).
- **filter(función):** Retorna un nuevo array con los elementos que cumplan la condición de la función (los que la función devuelve true).
- **reduce(función, valorInicial):** Aplica una función acumulativa a todos los elementos para reducirlos a un único valor (por ejemplo, sumar todos los elementos, etc.).

No es necesario memorizar todos de golpe; con el tiempo y práctica vas sabiendo cuál usar según la situación. Inicialmente, nos bastará con push, pop, etc., pero es bueno saber que existen métodos funcionales como map, filter, reduce, que junto con las funciones flecha facilitan operaciones complejas de forma concisa.

Ejemplos de algunos métodos:

```js
let nums = [1, 2, 3];
nums.push(4);
console.log(nums);        // [1,2,3,4]
nums.pop();
console.log(nums);        // [1,2,3] (quitó el 4)
nums.unshift(0);
console.log(nums);        // [0,1,2,3] (agregó 0 al inicio)
nums.shift();
console.log(nums);        // [1,2,3] (removió el primer elemento que era 0)

console.log(nums.indexOf(2));    // 1 (el valor 2 está en índice 1)
console.log(nums.includes(5));   // false (5 no está en el array)

let copia = nums.slice(1,3);
console.log(copia);       // [2,3] (elementos de índice 1 hasta 2)
console.log(nums);        // [1,2,3] (array original intacto)

nums.splice(1, 1, 9, 8);
console.log(nums);        // [1,9,8,3]
// Explicación: en índice 1 quitó 1 elemento (el 2) y en su lugar insertó 9 y 8.

let nombres = ["Ana", "Luis", "Miguel"];
console.log(nombres.join(", ")); // "Ana, Luis, Miguel"

nombres.sort();
console.log(nombres);     // ["Ana", "Luis", "Miguel"] (ya estaba ordenado alfabéticamente)
let numerosDesordenados = [10, 3, 25, 7];
numerosDesordenados.sort();
console.log(numerosDesordenados); // [10, 25, 3, 7] ¡No ordenó como esperabas!
// Por defecto sort convierte a string, por eso "10" < "3". Para ordenar números correctamente:
numerosDesordenados.sort((a,b) => a - b);
console.log(numerosDesordenados); // [3, 7, 10, 25]

let cuadrados = nums.map(x => x*x);
console.log(cuadrados);   // [1,81,64,9] (tomó [1,9,8,3] de nums actual y elevó al cuadrado cada uno)
let pares = nums.filter(x => x % 2 === 0);
console.log(pares);       // [8] (de [1,9,8,3], solo 8 es par)
let sumaTotal = nums.reduce((acum, x) => acum + x, 0);
console.log(sumaTotal);   // 21 (suma de 1+9+8+3)
```

En el código anterior, se muestran varios métodos en acción. No te preocupes si algunos como sort con función, map, filter, reduce, parecen avanzados; los comprenderás mejor una vez cubramos funciones flecha y callbacks. Lo principal es saber que los arrays tienen muchas operaciones útiles disponibles.

### Arrays multidimensionales y anidados

En JavaScript no hay tipos de datos específicos para matrices 2D o similares, pero como los arrays pueden contener cualquier tipo, es posible tener arrays que contengan a su vez otros arrays, creando estructuras de múltiples dimensiones.

Ejemplo, una matriz 3x3 (array de arrays):

```js
let matriz = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
];
console.log(matriz[1][2]); // 6 (fila 1, columna 2: recuerda que indexa desde 0)
matriz[2][0] = 99;
console.log(matriz[2]);    // [99, 8, 9]
```

O también objetos dentro de arrays y viceversa (p.ej., lista de estudiantes donde cada estudiante es un objeto con sus datos). Estas combinaciones permiten estructurar datos de manera poderosa.

### Ejercicios

1. **Operaciones básicas con array:** Crea un array con los números `[10, 20, 30]`. Luego:
   - Agrega el número 40 al final (push).
   - Quita el primer elemento (shift).
   - Agrega el número 5 al inicio (unshift).
   - Quita el último elemento (pop).
   - Al final, muestra el array resultante y su longitud.
2. **Recorrer array:** Crea un array con algunos nombres de personas. Recorre el array con un `for` tradicional y con un `for...of` imprimiendo cada nombre. Haz lo mismo usando el método `forEach` con una función flecha.
3. **Buscar en array:** Dado el array `let valores = [3, 50, 75, 100, 120];`, escribe código para encontrar el índice del valor 100 (usa `indexOf`) y verificar si el valor 30 está incluido (usa `includes`). Muestra los resultados.
4. **Sumar elementos:** Escribe una función (o simplemente código en el script) que sume todos los números en un array dado. Por ejemplo, con `[5, 7, 10, 2]` debe dar 24. Implementa esto con un bucle `for`. (Pista: inicializa una variable `suma` en 0 y recorre acumulando).
5. **Invertir un array:** Dado un array, por ejemplo `let original = [1,2,3,4,5]`, genera un nuevo array que sea la versión invertida, es decir, `[5,4,3,2,1]`. Puedes hacerlo iterando de atrás hacia adelante o usando métodos como `reverse` (pero ten cuidado si no quieres modificar el original).
6. **Filtro simple:** Crea un array con varios números, algunos pares y otros impares. Utilizando un bucle (o si te animas, el método `filter` con una función), construye un nuevo array que contenga solo los números pares del original.
7. **Arrays de objetos:** Crea un array de objetos, donde cada objeto represente a un estudiante con propiedades `nombre` y `edad`. Por ejemplo: `let estudiantes = [ { nombre: "Ana", edad: 22}, { nombre: "Luis", edad: 20}, ... ];`. Recorre el array y por cada estudiante imprime un mensaje como `"Ana tiene 22 años"`. Luego, agrega un nuevo estudiante al array y vuelve a imprimir para verificar que se agregó correctamente.

---

## Objetos en JavaScript

En JavaScript, un **objeto** es una colección de pares **clave-valor**. Las claves (también llamadas propiedades) suelen ser cadenas (o símbolos) que sirven como identificador, y los valores pueden ser de cualquier tipo (números, strings, booleanos, funciones, incluso otros objetos). Los objetos permiten representar entidades complejas con múltiples atributos.

### Creación de objetos literales

La forma más sencilla de crear un objeto es usando la notación literal con llaves `{}`. Dentro de las llaves definimos pares `clave: valor` separados por comas:

```js
let persona = {
  nombre: "Juan",
  edad: 30,
  estudiante: true
};
```

Este objeto `persona` tiene tres propiedades:
- `"nombre"` con valor `"Juan"`
- `"edad"` con valor `30`
- `"estudiante"` con valor `true`

Las claves (propiedades) en notación literal se suelen escribir sin comillas si son identificadores válidos (letras, números, _ y $ sin iniciar con número). Si la clave tiene espacios o caracteres especiales, deben ir entre comillas (pero es poco común usar espacios en claves). Por ejemplo: `{ "nombre completo": "Ana Pérez" }` es válido, aunque para acceder habría que usar notación de corchetes.

### Acceso y modificación de propiedades

Hay dos formas de acceder a las propiedades de un objeto:

- **Notación de punto:** `obj.propiedad`. Por ejemplo: `persona.nombre` nos daría `"Juan"`.
- **Notación de corchetes:** `obj["propiedad"]`. Por ejemplo: `persona["edad"]` nos daría `30`.

La notación de punto es más concisa y clara, pero la de corchetes es útil cuando el nombre de la propiedad está en una variable o no es un identificador válido. Ejemplo:

```js
console.log(persona.nombre);         // "Juan"
console.log(persona['edad']);        // 30

let prop = 'estudiante';
console.log(persona[prop]);         // persona['estudiante'] -> true (propiedad vía variable)
```

Para **modificar o agregar** propiedades:

- Asignar con notación de punto o corchetes funciona tanto para cambiar un valor existente como para agregar una nueva propiedad si no existía.

```js
persona.edad = 31;              // modifica edad
persona.ciudad = "Bogotá";      // agrega una nueva propiedad 'ciudad'
console.log(persona);
// { nombre: "Juan", edad: 31, estudiante: true, ciudad: "Bogotá" }
```

Para **eliminar** propiedades se usa el operador `delete`:

```js
delete persona.estudiante;
console.log(persona);
// { nombre: "Juan", edad: 31, ciudad: "Bogotá" } ('estudiante' fue removida)
```

Si intentamos acceder a una propiedad que no existe, obtendremos `undefined` (no error, a menos que intentemos usar algo de `undefined`). Esto nos permite comprobar si algo existe: por ejemplo, `if(persona.estudiante === undefined) { ... }` o usar el operador `'prop' in objeto` para verificar. Ej: `'nombre' in persona` sería true en este caso.

### Métodos: funciones dentro de objetos

Una propiedad de un objeto puede ser una función. En tal caso la llamamos **método** del objeto. Esto permite que el objeto tenga comportamientos asociados.

Ejemplo:

```js
let calculadora = {
  a: 5,
  b: 3,
  sumar: function() {
    return this.a + this.b;
  }
};

console.log(calculadora.sumar()); // 8
```

Aquí `calculadora` tiene propiedades `a` y `b`, y un método `sumar` que devuelve la suma de `a` y `b`. Fíjate en el uso de `this`: dentro de un método, `this` hace referencia al objeto sobre el cual se llamó el método. Es decir, `this.a` dentro de `calculadora.sumar()` es equivalente a `calculadora.a`. Usamos `this` para que el método funcione con *el objeto actual*, lo cual es útil si en el futuro copiamos el objeto o usamos el método con contextos distintos.

Desde ES6 hay una sintaxis abreviada para definir métodos dentro de objetos literales:

```js
let calculadora = {
  a: 5,
  b: 3,
  sumar() {    // <<---- en ES6+ podemos definir métodos así en objetos literales
    return this.a + this.b;
  }
};
```

Ambas formas (sumar: function(){} o sumar(){}) son equivalentes en este contexto.

### Objetos anidados y arrays de objetos

Las propiedades de un objeto pueden ser cualquier tipo, incluso otros objetos o arrays. Por ejemplo:

```js
let estudiante = {
  nombre: "Luis",
  edad: 21,
  carrera: "Ingeniería",
  direccion: {
    ciudad: "Medellín",
    pais: "Colombia"
  },
  calificaciones: [4.5, 3.8, 4.2]  // un array dentro del objeto
};

console.log(estudiante.direccion.ciudad);  // "Medellín"
console.log(estudiante.calificaciones[1]); // 3.8
```

También podemos tener arrays cuyos elementos sean objetos, como parcialmente hicimos en un ejercicio anterior. Esto es muy común: por ejemplo un array de productos donde cada producto es un objeto con propiedades (nombre, precio, etc.).

### Iterar propiedades de objetos

Para recorrer todas las propiedades de un objeto, podemos usar el bucle `for...in`:

```js
for (let clave in estudiante) {
  console.log(clave, ":", estudiante[clave]);
}
```

Esto imprimirá cada clave y valor correspondiente. El orden de iteración de `for...in` no está garantizado (aunque suele ser el de inserción para propiedades normales, pero no se confíe para lógica que dependa del orden).

También existen métodos utilitarios:
- `Object.keys(obj)` devuelve un array de las claves del objeto.
- `Object.values(obj)` devuelve un array de los valores del objeto.
- `Object.entries(obj)` devuelve un array de pares `[clave, valor]` para el objeto.

Ejemplo:

```js
console.log(Object.keys(estudiante));   // ["nombre", "edad", "carrera", "direccion", "calificaciones"]
console.log(Object.values(estudiante)); // ["Luis", 21, "Ingeniería", {…}, Array(3)]
```

### Copia y referencia de objetos

Hay que tener presente que los objetos (y arrays) en JS se manejan por **referencia**. Si asignamos un objeto a otra variable, ambos referencian el mismo objeto en memoria.

```js
let persona2 = persona;
persona2.nombre = "Carlos";
console.log(persona.nombre); // "Carlos" - también cambió, porque persona y persona2 apuntan al mismo objeto.
```

Si se desea copiar un objeto de forma independiente (clonar), hay técnicas como `Object.assign({}, objeto)` o el operador **spread** `{ ...objeto }` para crear una copia superficial. Esto tal vez excede el alcance inmediato, pero es bueno saber que asignar objetos no crea duplicados.

### Uso de objetos en situaciones prácticas

Los objetos son la base de **JSON** (JavaScript Object Notation), que es un formato de datos muy usado. Un objeto JS puede serializarse a JSON con `JSON.stringify(obj)` y volver a objeto con `JSON.parse(cadena)`.

También en programación web, muchos datos que obtenemos de APIs o enviamos son objetos.

Más adelante veremos cómo crear múltiples objetos similares usando **clases** (sintaxis moderna) o funciones constructoras, para evitar repetir manualmente la creación de objetos con las mismas propiedades.

### Ejercicios

1. **Objeto persona:** Crea un objeto llamado `persona` con propiedades: `nombre` (string), `edad` (number), `ciudad` (string) y `profesion` (string). Asigna valores iniciales a esas propiedades. Luego:
   - Imprime el nombre y edad de la persona.
   - Modifica la edad de la persona.
   - Agrega una nueva propiedad `hobbies` que sea un array de strings (por ejemplo, `["leer", "viajar", "música"]`).
   - Elimina la propiedad `profesion`.
   - Recorre todas las propiedades del objeto imprimiendo clave y valor (usando `for...in`).
2. **Método en objeto:** Crea un objeto `cuentaBancaria` con propiedades `saldo` (number) inicializado, y métodos `depositar(cantidad)` y `retirar(cantidad)`. Los métodos deben ajustar el saldo según corresponda y mostrar el nuevo saldo por consola. Asegúrate de manejar que no se pueda retirar más de lo que hay en saldo (por ejemplo, imprimirá "Fondos insuficientes" en ese caso). Prueba llamar a los métodos varias veces.
3. **Array de objetos:** Crea un array llamado `biblioteca` que contenga varios objetos, cada uno representando un libro con propiedades `titulo`, `autor` y `año`. Por ejemplo: `{ titulo: "1984", autor: "George Orwell", año: 1949 }`, etc. Luego recorre ese array e imprime un listado con los títulos de los libros publicados después del año 2000.
4. **Objeto anidado:** Crea un objeto `curso` que tenga propiedades: `nombre` (nombre del curso, string), `duracion` (en horas, number), `docente` (objeto con propiedades `nombre` y `email`), y `estudiantes` (array de nombres de estudiantes). Imprime el nombre del docente y la cantidad de estudiantes inscritos (el length del array `estudiantes`).
5. **Actualización dinámica:** Escribe una función `actualizarPropiedad(obj, prop, valor)` que reciba un objeto y actualice una propiedad dada con el valor dado, creando la propiedad si no existía. Prueba la función con diferentes objetos y propiedades, incluyendo el caso de modificar una existente y agregar una nueva.

---

## Manipulación del DOM (Document Object Model)

El **DOM (Document Object Model)** es la representación en forma de árbol de nodos de una página HTML. Cuando un navegador carga un documento HTML, crea este modelo en memoria, donde cada elemento HTML es un nodo que puede ser accedido y manipulado mediante JavaScript. En otras palabras, el DOM permite a JavaScript *hablar* con el contenido HTML para modificarlo dinámicamente.

Para trabajar con el DOM, JavaScript nos proporciona el objeto global `document`, que representa la página. A través de `document` podemos buscar elementos, crear nuevos, modificar atributos, estilos, etc.

### Selección de elementos del DOM

Lo primero para manipular un elemento es **seleccionarlo** (obtener una referencia a él). Existen varios métodos para buscar elementos:

- `document.getElementById(id)` – Devuelve el elemento que tenga el atributo `id` igual al valor dado. Si no existe, retorna `null`. **Ejemplo:** `let titulo = document.getElementById("titulo");`
- `document.getElementsByClassName(nombreClase)` – Devuelve una colección (HTMLCollection) de todos los elementos que tengan esa clase CSS. Es **like** un array (tiene índices y propiedad length) pero no exactamente un array completo (aunque se puede iterar similar). **Ejemplo:** `let items = document.getElementsByClassName("item");`
- `document.getElementsByTagName(nombreEtiqueta)` – Devuelve una colección de elementos por su etiqueta (tag name), por ejemplo todos los `<p>`, todos los `<div>`, etc. **Ejemplo:** `let parrafos = document.getElementsByTagName("p");`
- `document.querySelector(selector)` – Devuelve **el primer elemento** que coincida con un selector CSS dado. Este es muy flexible porque el selector puede ser complejo. Por ejemplo, `document.querySelector("#menu li.active")` podría buscar el primer `<li class="active">` dentro del elemento con id "menu".
- `document.querySelectorAll(selector)` – Devuelve **todos los elementos** que coincidan con un selector CSS dado, como una NodeList (que es similar a un array). **Ejemplo:** `let elementos = document.querySelectorAll("ul > li");`

Los métodos `querySelector` y `querySelectorAll` son muy versátiles y modernos, en muchos casos reemplazan el uso de los anteriores. Sin embargo, getElementById sigue siendo muy común por su sencillez y eficiencia para ID únicos.

También podemos llamar estos métodos *no solo en document*, sino en cualquier nodo elemento para buscar dentro de un subárbol. Por ejemplo: `let seccion = document.getElementById("seccion1"); let destacados = seccion.getElementsByClassName("destacado");` buscaría elementos con clase "destacado" dentro del elemento con id "seccion1".

**Ejemplo de HTML para ilustrar manipulación:**

Supongamos un HTML básico:

```html
<body>
  <h1 id="titulo">Bienvenido</h1>
  <p class="texto">Este es un párrafo.</p>
  <p class="texto destacado">Este es otro párrafo destacado.</p>
  <ul id="lista">
    <li>Elemento 1</li>
    <li>Elemento 2</li>
  </ul>
  <button id="boton">Haz clic</button>
</body>
```

En nuestro script JS (dentro de `<script>` o archivo .js incluido), podríamos hacer selecciones como:

```js
let encabezado = document.getElementById("titulo");            // h1
let parrafos = document.getElementsByClassName("texto");       // HTMLCollection de <p> (los dos párrafos)
let parrafoDestacado = document.querySelector("p.destacado");  // primer <p class="destacado">
let items = document.querySelectorAll("#lista li");            // NodeList de todos los <li> dentro de #lista
let boton = document.getElementById("boton");                  // <button id="boton">
```

### Modificación de contenido y atributos

Una vez tenemos una referencia a un nodo, podemos modificar sus propiedades:

- **Cambiar texto interno:** Cada nodo de elemento (p. ej., un `<p>`) tiene la propiedad `textContent` que representa el texto dentro de él (sin incluir etiquetas HTML hijas, solo texto plano). Asignar a `element.textContent` cambia ese texto. Ejemplo: `encabezado.textContent = "Bienvenido al sitio";`
  
  Otra propiedad similar es `innerText`, que en muchos casos funciona parecido a `textContent` pero puede diferir en cómo maneja estilos CSS (por ejemplo, no incluye texto oculto via CSS). En general, `textContent` es preferible para contenido puramente textual.

- **Cambiar HTML interno:** La propiedad `innerHTML` contiene el *contenido HTML* dentro de un elemento como una cadena. Podemos asignarle una cadena con nuevas etiquetas para cambiar por completo su interior. Ej: `encabezado.innerHTML = "<span style='color:red'>Bienvenido</span>"`. Esto reemplazará el contenido del h1 con un span rojo. **¡Cuidado!:** usar `innerHTML` con cadenas construidas dinámicamente puede exponer a riesgos de seguridad (inyección de HTML) si esas cadenas provienen de usuarios o externos. En contextos controlados (ejemplo: tu propio código) está bien, pero hay que ser precavido si se inserta HTML arbitrario.

- **Modificar atributos:** Podemos acceder a cualquier atributo HTML de un elemento a través de propiedades homónimas. Por ejemplo, un elemento `<img>` tiene atributos como `src`, `alt`, `width`, etc. En JS, si tenemos `let imagen = document.getElementById("logo");` podemos hacer `imagen.src = "nueva_ruta.png";` para cambiar su fuente, o `imagen.alt = "Nuevo texto alternativo";`. Esto funciona para la mayoría de atributos comunes. También existe un método general `element.setAttribute(nombreAttr, valor)` y su contraparte `element.getAttribute(nombreAttr)` para manejar atributos arbitrarios, por ejemplo `element.setAttribute("data-id", "123")` para establecer un atributo personalizado data-*.

- **Modificar clases y estilo:** Cada elemento tiene una propiedad `className` que contiene su(s) clase(s) CSS como una cadena separada por espacios. Podemos reasignarla para cambiar completamente las clases. Por ejemplo: `parrafoDestacado.className = "texto grande";` (esto reemplazaría cualquier clase previa con exactamente "texto grande").

  Para manipular clases individuales sin sobrescribir todas, es mejor usar `element.classList`, que es una lista con métodos útiles:
  - `element.classList.add("nuevaClase")`
  - `element.classList.remove("claseExistente")`
  - `element.classList.toggle("clase")` (la quita si está o la pone si no está)
  - `element.classList.contains("clase")` (devuelve true/false si tiene la clase)

  Para estilos en línea, cada elemento tiene una propiedad `style` que a su vez tiene propiedades para cada regla CSS *en formato camelCase*. Ejemplo: `parrafoDestacado.style.color = "blue";`, `parrafoDestacado.style.fontSize = "20px";`. Esto aplica estilos en línea (modificando el atributo style del elemento). Ten en cuenta que solo afecta esa instancia y que los nombres de propiedades CSS como `background-color` pasan a ser `backgroundColor` en JS.

  Es generalmente preferible tener clases CSS predefinidas y solo añadir o quitar clases en JS para aplicar estilos, en lugar de manipular cada estilo manualmente con `.style`, excepto para cambios muy específicos o calculados.

### Creación y eliminación de elementos del DOM

JavaScript puede crear nuevos nodos y añadirlos al DOM, así como eliminar existentes.

- **Crear un elemento:** Se usa `document.createElement("tag")` para crear un nuevo elemento vacío de la etiqueta especificada. Ej: `let nuevoParrafo = document.createElement("p");`.

- **Crear nodos de texto:** Si solo quieres un nodo de texto (sin estar envuelto en un elemento), puedes usar `document.createTextNode("texto")`, aunque generalmente es más cómodo luego usar `textContent` en el elemento.

- **Agregar un nodo al DOM:** Para insertar un nodo creado (o mover uno existente) en el DOM, se utilizan métodos sobre un nodo **padre**:
  - `parent.appendChild(nodo)` – agrega el `nodo` como último hijo del elemento `parent`.
  - `parent.prepend(nodo)` – agrega el nodo como primer hijo (no soportado en IE, pero ampliamente en navegadores modernos).
  - `parent.insertBefore(nuevoNodo, nodoReferencia)` – inserta el nuevoNodo como hijo de `parent`, antes de `nodoReferencia` (que también debe ser hijo de parent).
  - También hay `parent.replaceChild(nuevo, viejo)` para reemplazar un nodo hijo por otro.

- **Eliminar un nodo:** Llamamos `parent.removeChild(nodo)` para remover un nodo hijo de su padre. O más moderno: `nodo.remove()` directamente en el elemento a borrar (no soportado en IE11, pero sí en modernos).

Ejemplo práctico:

```js
// Crear un nuevo item para la lista
let lista = document.getElementById("lista");        // <ul id="lista">
let nuevoItem = document.createElement("li");
nuevoItem.textContent = "Elemento 3";
lista.appendChild(nuevoItem);  // ahora la lista tendrá un tercer <li> "Elemento 3"

// Eliminar el primer párrafo
let primerParrafo = document.querySelector("p.texto");
primerParrafo.remove();  // elimina ese párrafo del DOM

// Crear un elemento destacado antes del botón
let destacado = document.createElement("span");
destacado.textContent = "¡Nuevo!";
destacado.style.backgroundColor = "yellow";
let btn = document.getElementById("boton");
document.body.insertBefore(destacado, btn);
```

En este ejemplo, agregamos un nuevo `<li>` a la lista, eliminamos el primer párrafo que tenía clase "texto", y creamos un `<span>` amarillo con texto "¡Nuevo!" que insertamos justo antes del botón.

### Evento DOMContentLoaded y ubicación del script

Algo importante: Si tu script corre antes de que el DOM exista (por ejemplo, si incluyes el `<script>` en la cabecera `<head>` sin `defer` o antes del cuerpo), tus llamadas a `document.getElementById` etc. pueden devolver null porque los elementos aún no se han construido. Dos estrategias comunes para evitar esto:

- Colocar el `<script>` justo antes de cerrar el `</body>`, así se ejecuta después de cargar el HTML.
- O usar el evento `DOMContentLoaded` para ejecutar tu código cuando el DOM esté listo:

  ```js
  document.addEventListener("DOMContentLoaded", function() {
    // Todo el código de manipulación DOM va aquí...
  });
  ```

Con la palabra clave `defer` en la etiqueta script, se logra un efecto similar a ponerlo al final, permitiendo mantenerlo en el head pero ejecutándose después del parsing del HTML.

### Ejercicios

*(Para probar estos ejercicios, puedes crear un archivo HTML con elementos apropiados y enlazar tu script JS, o usar la consola con `document` si la página ya tiene esos elementos.)*

1. **Modificar contenido:** Supón que tienes en tu HTML un elemento `<p id="descripcion">Texto original</p>`. Usando JavaScript, cambia el texto de ese párrafo por "Texto modificado desde JS". Luego, cambia su color de texto a rojo.
2. **Contador dinámico:** En el HTML, coloca un `<div id="contador">0</div>` y un botón con id "incrementar". Escribe un script que al hacer clic en el botón, tome el contenido numérico del div contador, lo incremente en 1 y actualice el div con el nuevo valor. *(Nota: necesitarás conocimientos de eventos; si aún no lo has visto en estas notas, puedes adelantarte o dejar la funcionalidad de clic para después de leer la sección de Eventos.)*
3. **Añadir elementos a la lista:** Dada una lista `<ul id="listaTareas"></ul>` vacía en HTML y un input de texto con id "nuevaTarea" y un botón "Agregar", haz que al presionar el botón se tome el texto del input, se cree un nuevo `<li>` con ese texto y se añada a la lista. Tras eso, limpia el input. *(Requiere manejar evento de clic, similar al ejercicio 2.)*
4. **Cambiar imagen:** Supón que tienes `<img id="foto" src="imagen1.jpg" alt="Foto">` en tu página. Crea un script que después de 3 segundos de cargar la página (usa `setTimeout` para retrasar 3000ms) cambie la imagen mostrada (`src`) a otra diferente y también cambie el texto alternativo (`alt`).
5. **Destacar párrafos:** Escribe un código que seleccione todos los párrafos (`<p>`) de la página (por ejemplo con `document.querySelectorAll("p")`) y les aplique la clase `"resaltado"` (supón que esa clase está definida en CSS con un fondo amarillo). Pista: puedes iterar la NodeList resultante con for...of o forEach y usar `element.classList.add("resaltado")`.
6. **Eliminar elemento con delay:** Añade dinámicamente (con `createElement`) un mensaje de aviso en la página, por ejemplo un div con texto "Este mensaje desaparecerá en 5 segundos". Luego, usando `setTimeout`, remueve ese elemento del DOM pasados 5000ms.

---

## Manejo de Eventos en JavaScript

Un **evento** es una acción o suceso en la página, al cual podemos responder con código. Por ejemplo, cuando el usuario hace clic en un botón, cuando mueve el mouse, cuando una página termina de cargar, cuando se envía un formulario, etc., se generan eventos. JavaScript permite **escuchar** esos eventos y ejecutar funciones (denominadas manejadores o listeners) cuando ocurran.

### Modelo de eventos

Cada elemento del DOM (así como el objeto `window` y `document`) puede emitir distintos tipos de eventos. Para reaccionar a ellos, debemos **registrar** funciones manejadoras para un tipo de evento en particular sobre un elemento en particular.

Los tipos de eventos comunes incluyen:

- Eventos de mouse: `click`, `dblclick` (doble clic), `mouseenter` (cuando el puntero entra al elemento), `mouseleave`, `mousedown` (botón presionado), `mouseup` (botón soltado), `mousemove`, etc.
- Eventos de teclado (normalmente escuchados en inputs o en el documento global): `keydown` (al presionar una tecla), `keyup` (al soltarla), `keypress` (cuando se pulsa, obsoleto en algunos casos).
- Eventos de formulario: `submit` (al enviar formulario), `change` (en input/select cuando cambia valor), `input` (mientras se va cambiando el valor de un input), `focus`/`blur` (cuando un elemento recibe o pierde el foco).
- Eventos de ventana/documento: `DOMContentLoaded` (cuando se cargó el DOM), `load` (cuando toda la página, imágenes incluidas, cargó), `resize` (cambio de tamaño ventana), `scroll`, etc.

### Asignar manejadores de eventos

Hay varias formas de asociar código a un evento:

1. **Atributo HTML inline (no recomendado):** Por ejemplo, en HTML `<button onclick="alert('Hola')">Haz clic</button>`. Este método embebe código JS en la marca HTML. Funciona, pero se considera una mala práctica porque mezcla mucho JS en HTML, hace difícil mantener el código, y solo permite una acción por evento (si definimos otra, machaca la anterior).
2. **Propiedad `onevent` en DOM:** Cada elemento DOM tiene propiedades como `onclick`, `onmouseover`, etc. Podemos asignarles una función. Ejemplo:
   ```js
   let btn = document.getElementById("miBoton");
   btn.onclick = function() {
     alert("¡Botón clickeado!");
   };
   ```
   Esto asigna una función anónima para ejecutarse en el click. Si luego volvemos a hacer `btn.onclick = otraFuncion`, reemplazará la previa. Es un método más limpio que el inline, pero aún permite solo un handler por evento por elemento (aunque ese handler podría llamar a otras cosas).
3. **addEventListener (recomendado):** Es la forma más versátil y moderna. Podemos adjuntar múltiples listeners a un mismo evento y elemento, no se pisarán entre sí. Sintaxis:
   ```js
   element.addEventListener(tipoEvento, funcionManejadora);
   ```
   Por ejemplo:
   ```js
   btn.addEventListener("click", function() {
     alert("¡Botón clickeado!");
   });
   ```
   Aquí `function() { ... }` es el manejador (callback) que se ejecutará al hacer click en `btn`. Podemos agregar más `addEventListener("click", ...)` sobre el mismo `btn` y ambos se ejecutarán en orden de registro.
   
   Con `addEventListener` también podemos más tarde quitar el manejador con `removeEventListener` si tenemos referencia a la misma función.

**Ejemplo de uso de eventos:**

Supongamos un HTML:
```html
<button id="saludarBtn">Saludar</button>
<input type="text" id="nombreInput" placeholder="Escribe tu nombre">
```

Podemos hacer:
```js
let boton = document.getElementById("saludarBtn");
let input = document.getElementById("nombreInput");

boton.addEventListener("click", function() {
  let nombre = input.value;
  alert("Hola, " + nombre + "!");
});
```

Aquí, al hacer clic en el botón, tomamos el valor actual del campo de texto y mostramos un saludo con alert.

### El objeto Event

Cuando ocurre un evento y nuestra función manejadora se ejecuta, el navegador pasa a esa función un objeto que contiene información sobre el evento. Por ejemplo, en un evento de click, ese objeto tendrá información como la posición del mouse, qué botón se pulsó, el elemento objetivo, etc.

En `addEventListener`, podemos definir el manejador con un parámetro para recibir ese objeto, comúnmente llamado `event` o `e`:

```js
boton.addEventListener("click", function(event) {
  console.log("Se hizo clic en:", event.target);
});
```

`event.target` suele ser el elemento DOM que originó el evento (por ejemplo, el botón en sí mismo). En eventos de teclado, el objeto evento tendrá propiedades como `key` (tecla presionada), `code`, etc. En eventos de formulario, puede tener detalles del cambio.

Por ejemplo, manejando entrada de teclado:
```js
document.addEventListener("keydown", function(e) {
  console.log("Tecla:", e.key, "Código:", e.code);
});
```
Esto registraría a nivel documento, de modo que cualquier tecla presionada se loguea.

### Propagación de eventos (burbuja y captura)

Cuando un elemento dentro de otro es clickeado, el evento por defecto **burbujea** hacia los ancestros. Por ejemplo, si tengo un `<div>` que contiene un `<button>` y hago clic en el botón, primero se dispara el evento click del botón, luego el del div contenedor (si tiene listener), luego podría subir más arriba, hasta `document` y `window`. Esto se llama **event bubbling** (burbuja). Existe también una fase de captura (que va de arriba hacia abajo) pero por defecto los listeners con `addEventListener` sin tercer argumento se asocian a la fase burbuja, que es generalmente suficiente.

A veces es útil detener esa propagación, por ejemplo cuando un manejador de un elemento padre no debería ejecutarse si se hizo clic en un elemento hijo con un comportamiento específico. Para eso, dentro del manejador, se puede llamar `event.stopPropagation()` para frenar que siga subiendo.

También está `event.preventDefault()`, que sirve para cancelar la acción por defecto de ciertos eventos. Ej: en un `<a href="#">` al hacer click normalmente navega (o en `#` hace scroll al top), con `event.preventDefault()` evitas eso. En un form, `submit` recarga la página por defecto; si interceptamos el evento `submit` en JS y hacemos `e.preventDefault()`, podemos evitar el envío para manejarlo vía AJAX o validar antes, etc.

Ejemplo:
```js
let enlace = document.getElementById("enlace");
enlace.addEventListener("click", function(e) {
  e.preventDefault(); // cancela que el enlace navegue
  console.log("Enlace clickeado, pero no navegamos gracias a preventDefault.");
});
```

### Ejemplos comunes de eventos

- **Clic en botón:** Ya vimos arriba cómo manejar click de un botón para ejecutar acción.
- **Cambio en input:** Podemos hacer `input.addEventListener("input", (e) => { ... });` para capturar cada tecla en un campo de texto (por ejemplo para validar en vivo o mostrar sugerencias).
- **Submit de formulario:** `form.addEventListener("submit", (e) => { e.preventDefault(); ... })` para validar datos y luego, si todo bien, enviar manualmente o permitir el envío.
- **Eventos de teclado globales:** Mover algo en pantalla con flechas (capturar keydown y si e.key === "ArrowRight" por ej, mover un elemento).
- **Eventos de mouse sobre elementos:** Cambiar estilo on hover: en lugar de CSS `:hover`, podrías usar `element.addEventListener("mouseenter", ...)` y `element.addEventListener("mouseleave", ...)` para efectos personalizados con JS.
- **Evento `load` de window:** `window.addEventListener("load", ...)` se ejecuta cuando toda la página (incluyendo imágenes, etc.) cargó. A veces se usa para iniciar cosas una vez todo listo.
- **Evento `DOMContentLoaded`:** Ya mencionado, cuando DOM está listo, antes de imágenes completas.
- **Timers como eventos:** No son eventos DOM, pero hay funciones `setTimeout` y `setInterval` que ejecutan código después de cierto tiempo o cada intervalo respectivamente (similar a eventos temporales).

### Ejercicios

1. **Click contador:** Crea un botón con el texto "Clics: 0". Cada vez que se haga clic en el botón, incrementa un contador y actualiza el texto del botón mostrando el número de clics. *(Hint: almacenamos un contador en una variable externa o usamos dataset, y usamos `button.textContent = "Clics: " + contador;` en cada click.)*
2. **Validar input en tiempo real:** En el HTML, crea un campo `<input type="text" id="usuario">` y un `<p id="aviso" style="color:red"></p>` vacío debajo. Escribe un script que escuche el evento `"input"` del campo de texto. Cada vez que el usuario escriba, si la longitud del texto excede 8 caracteres, mostrar en el párrafo de aviso un mensaje "Máximo 8 caracteres" y cortar el contenido (por ejemplo, puedes setear `input.value = input.value.slice(0,8)`). Si la longitud es <= 8, borrar cualquier mensaje en `#aviso`. (Esto practica manipulación de valor de input y eventos).
3. **Galería simple:** Imagina que tienes tres imágenes pequeñas (thumbnails) y una imagen grande principal. Al hacer clic en cualquiera de las pequeñas, la imagen grande debe actualizarse para mostrar esa imagen (puedes lograrlo cambiando su atributo `src`). Implementa este comportamiento usando eventos. (HTML: tres `<img class="thumb">` de tamaño pequeño y un `<img id="grande">` para la principal).
4. **Teclas de dirección:** Crea un div cuadrado de 50px por lado, con fondo, posicionado relativo o absoluto en algún lugar. Utiliza eventos del teclado (`keydown`) sobre `document` para mover ese div: por ejemplo, flecha arriba reduce su posición top, flecha abajo la aumenta, izquierda/derecha modificar left. Asegúrate de prevenir la acción por defecto de la página que hace scroll con las flechas (usando `e.preventDefault()` para esas teclas) para que solo mueva el elemento.
5. **Mostrar/Ocultar contraseña:** Crea un campo input de tipo "password" y un checkbox con la etiqueta "Mostrar contraseña". Usando eventos, haz que al marcar el checkbox, el input cambie su tipo a "text" (para revelar la contraseña) y al desmarcar vuelva a "password". (Pista: `inputPassword.type = "text";`).
6. **Detener propagación:** Crea un div grande con fondo claro y padding, y dentro de él un botón. Asigna un manejador de click al div que muestre un mensaje (por ejemplo `console.log("Div clickeado")`) y otro manejador de click al botón que muestre otro mensaje (`console.log("Botón clickeado")`). Prueba hacer clic en el botón y observa en consola qué ocurre (verás ambos mensajes por la propagación). Luego, modifica el manejador del botón para que use `event.stopPropagation()`. Comprueba de nuevo que al clicar el botón ahora solo se ve el mensaje del botón y no el del div.

---

## Funciones Flecha (Arrow Functions) en JavaScript

Las **funciones flecha** (arrow functions) son una sintaxis más concisa para escribir funciones anónimas, introducida en ES6 (2015). Se denominan así por el uso de la "flecha" `=>`. Estas funciones a menudo permiten un código más claro y manejan el contexto de `this` de forma diferente a las funciones tradicionales.

### Sintaxis básica

Una función flecha se define utilizando la sintaxis:

```js
(param1, param2, ...) => {
  // cuerpo de la función
  return valor;
}
```

Si la función tiene **un solo parámetro**, se pueden omitir los paréntesis alrededor del mismo. Si no tiene parámetros, se usan paréntesis vacíos `()`.

Si el cuerpo de la función es una sola expresión, se puede omitir las llaves y la palabra `return`: esa expresión se evaluará y retornará implícitamente.

Veamos equivalencias:

- Función clásica:
  ```js
  const doblar = function(n) {
    return n * 2;
  };
  ```
  Función flecha equivalente:
  ```js
  const doblar = (n) => {
    return n * 2;
  };
  ```
  O más concisa aún:
  ```js
  const doblar = n => n * 2;
  ```
  (Aquí omitimos paréntesis de `n` porque es único param, omitimos `{}` y `return` porque es una expresión simple.)

- Función clásica sin parámetros:
  ```js
  let saludar = function() {
    return "Hola";
  };
  ```
  Flecha:
  ```js
  let saludar = () => "Hola";
  ```

- Con múltiples parámetros:
  ```js
  let sumar = function(a, b) { return a + b; };
  // flecha
  let sumar = (a, b) => a + b;
  ```

- Con cuerpo más complejo (múltiples líneas):
  ```js
  let calcular = (a, b) => {
    let resultado = a * b;
    console.log("El resultado es", resultado);
    return resultado;
  };
  ```
  Aquí tuvimos que usar llaves y `return` explícito porque el cuerpo tiene varias instrucciones.

### Arrow functions como callbacks

Las arrow functions son especialmente útiles como funciones callback (de eventos, de arrays como map/filter, de promesas, etc.) porque suelen ser cortas.

Ejemplo con array:
```js
let numeros = [1, 2, 3, 4];
let cuadrados = numeros.map(x => x * x);
console.log(cuadrados); // [1, 4, 9, 16]
```
Aquí usamos `map` con una arrow `x => x * x`. Es más conciso que `function(x){ return x*x; }`.

Otro ejemplo con filter:
```js
let impares = numeros.filter(n => n % 2 !== 0);
console.log(impares); // [1, 3]
```

Eventos:
```js
button.addEventListener("click", e => {
  console.log("Botón clickeado, id:", e.target.id);
});
```
Si el cuerpo es pequeñito, incluso podría ser `button.addEventListener("click", e => console.log("Clic", e));` en una línea (aunque aquí no hay retorno relevante, solo side effect).

### El valor de `this` en arrow functions

Una diferencia importante: Las arrow functions **no tienen su propio `this`**. En una función normal, `this` depende de cómo se llama a la función (p.ej., si es método de objeto, `this` es el objeto). En una arrow function, `this` se mantiene léxico, es decir, toma el valor de `this` del entorno exterior en el que se definió.

Esto es útil para ciertos casos, por ejemplo al manejar callbacks donde quieres acceder al `this` de la clase o del objeto circundante sin perderlo.

Ejemplo clásico:
```js
function Persona(nombre) {
  this.nombre = nombre;
  // usar una función regular:
  this.saludarRegular = function() {
    console.log("Hola, soy " + this.nombre);
  };
  // usar arrow function:
  this.saludarFlecha = () => {
    console.log("Hola, soy " + this.nombre);
  };
}

let p = new Persona("Ana");
setTimeout(p.saludarRegular, 1000); // después de 1s, "Hola, soy undefined" (this se perdió)
setTimeout(p.saludarFlecha, 1500);  // después de 1.5s, "Hola, soy Ana"
```
¿Por qué pasó esto? Porque en `setTimeout`, la función se llama sin contexto (this por defecto es global o undefined en strict), así que `this.nombre` dentro de `saludarRegular` no encuentra `this.nombre` (this es window/undefined). Pero `saludarFlecha`, al definirse como arrow dentro del constructor, capturó el `this` léxico de la función Persona, que es la instancia `p`, por tanto dentro de la arrow `this.nombre` sigue refiriendo a `p.nombre`.

En contextos sencillos, esto puede no ser relevante, pero es bueno saberlo. En la mayoría de casos, usar arrow en callbacks evita tener que hacer `var self = this` antes, etc.

**Precaución:** Justamente porque no tiene `this` propio, no se debe usar arrow functions para definir métodos de objetos cuando necesites `this` apuntando al objeto, porque si defines un método arrow dentro de un objeto literal, el `this` interior no será el objeto sino el que esté fuera (global, o undefined en strict). Por ejemplo:
```js
let obj = {
  nombre: "Objeto",
  saludar: () => {
    console.log("Hola, " + this.nombre);
  }
};
obj.saludar(); // "Hola, undefined", porque this dentro de arrow no es obj (sino global).
```
Para métodos de objeto conviene usar la sintaxis normal (o la abreviada `saludar() { ... }` que al final es función normal) para que `this` sea el objeto. Las arrow se usan más para funciones anónimas, callbacks, etc., no tanto como métodos propios de objetos literales (excepto en clases, donde su uso es menos común salvo en propiedades de clase).

### Otros detalles

- Las arrow no tienen `arguments` (variable pseudo-array con argumentos); si necesitas argumentos, en arrow debes usar rest `(...args)`.
- No pueden usarse como constructores (no tienen `[[Construct]]`), es decir, no se puede hacer `new arrowFunction`.
- Pueden implicar retorno de objeto literal: si quieres retornar un objeto literal en una arrow concisa, debes envolverlo en paréntesis, porque si pones `=> { foo: 1 }` con llaves se interpreta como bloque y no como objeto. Ej: `() => ({ foo: 1 })` retornaría `{ foo: 1 }`.

### Ejercicios

1. **Reescritura en flecha:** Reescribe las siguientes funciones tradicionales en forma de funciones flecha:
   - `function resta(a, b) { return a - b; }`
   - `function esPar(n) { return n % 2 === 0; }`
   - `function imprimir() { console.log("Imprimiendo"); }`
   Comprueba su funcionamiento llamándolas con algunos valores.
2. **Map con flecha:** Tienes un array de palabras: `let palabras = ["hola", "mundo", "JavaScript"];`. Usa `map` con una función flecha para convertir cada palabra a mayúsculas. (Pista: método de string `.toUpperCase()`). Resultará en `["HOLA", "MUNDO", "JAVASCRIPT"]`.
3. **Filter con flecha:** Dado un array de números `let nums = [10, 25, 32, 50, 61, 80];`, utiliza `filter` con una función flecha para obtener solo los números mayores a 50. Debería devolver `[61, 80]`.
4. **Reduce con flecha:** Dado un array `let valores = [5, 7, 9, 3, 1];`, usa `reduce` y una función flecha para obtener la suma de todos los elementos. (Recuerda proporcionar el valor inicial 0 para el acumulador).
5. **this léxico:** Crea un objeto `contador` con una propiedad `cuenta` inicializada en 0. Agrega un método `incrementarAsync` que después de 1 segundo incremente `cuenta` en 1 y la muestre por consola. Implementa `incrementarAsync` usando `setTimeout` con una función flecha adentro para que el `this` apunte correctamente al objeto `contador`. Prueba llamar `contador.incrementarAsync()` y verifica que pasado un segundo se ve el resultado esperado. (Si lo haces mal con una función normal, `this` no apuntaría al objeto).
6. **Comparación this:** Crea un objeto similar al anterior pero en lugar de arrow function en setTimeout, usa una función normal y guarda referencia a `this` en una variable externa (`that = this`) antes del setTimeout (clásica solución pre-ES6). Observa la diferencia.
