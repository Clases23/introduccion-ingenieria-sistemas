
**Instrucciones Generales del Examen**

1. **Estructura de archivos**

   * Deben entregar **dos archivos** separados:

     * `examen_nombre1_nombre2.html` ➔ contendrá **solo** la estructura HTML y la referencia al script.
     * `examen_nombre1_nombre2.js`   ➔ contendrá **todo** el código JavaScript.

2. **Entrega**


   * La entrega se hará a través de Uvirtual en una tarea que estara en la sección de HTML y JavaScript.
   * Se deberan de etregar los dos archivos el día antes de la sustentación antes de las 6:00 de la tarde, una vez pasada esa hora no dejara hacer mas entregas y se tomara como cero el 40% de la nota.
   

3. **Calificación (0 – 5)**

   * **40%** de la nota corresponde a la **entrega correcta** (nombres de archivos, separación HTML/JS, cumplimiento de especificaciones).
   * **60%** corresponde a la **sustentación oral**, donde deberán explicar la lógica y las decisiones de su código.

4. **Alcance y restricciones**

   * **Solo** HTML5 y JavaScript puro.
   * **No** emplear métodos especiales de `Array` ni funciones avanzadas.

---

## Enunciados

1. **Lista de aprobados**

   * En `examen.js`, crea un arreglo `estudiantes`, donde cada elemento es un arreglo de dos posiciones:

     ```js
     [ "Nombre", calificación ]
     ```

     con `calificación` entre 0 y 5.
   * Mediante un **for** y un **if/else**, recorre `estudiantes` y genera dinámicamente un `<ul>` en el `<body>` de `examen_nombre1_nombre2.html` que liste **solo** los nombres de quienes tienen calificación ≥ 3.
   * Usa `document.createElement` y `appendChild` (o `innerHTML`) para construir la lista.

2. **Tabla de multiplicar automática**

   * Declara en `examen_nombre1_nombre2.js` una variable `N` (entero positivo, p. ej. 5).
   * Con un **bucle for anidado**, genera la tabla de multiplicar de cada número del 1 a `N`.
   * Muestra cada operación en un `<p>` o en una tabla HTML, con el formato:

     ```
     2 × 1 = 2
     2 × 2 = 4
     …
     5 × 5 = 25
     ```
   * Inserta todo en `<div id="tabla"></div>` dentro del `<body>`.

3. **Operaciones básicas sobre un array**

   * Define en `examen_nombre1_nombre2.js` un arreglo `numeros` con al menos 8 enteros (positivos y negativos).
   * Con **un solo** bucle **for** y **condicionales**, calcula:

     1. La suma de todos los elementos.
     2. El promedio (suma ÷ cantidad).
     3. El valor máximo.
     4. El valor mínimo.
   * Al terminar, muestra cada resultado en un `<p>` dentro del `<body>`. No uses funciones auxiliares ni métodos de array.

4. **Detección de palíndromo/capicúa**

   * Declara en `examen_nombre1_nombre2.js` una variable `input` que contenga una **cadena de texto** (puede ser una palabra o un número en forma de cadena, p. ej. `"radar"` o `"12321"`).
   * Usando un **bucle for** y **programación secuencial**, recorre `input` de fin a inicio para construir una cadena `reversed`.
   * Con un **if/else**, compara `input` y `reversed` carácter a carácter para determinar si son iguales.
   * Inserta en el `<body>` un `<p>` con el mensaje:

     * `«input» es palíndromo/capicúa`
     * o `«input» no es palíndromo/capicúa`
