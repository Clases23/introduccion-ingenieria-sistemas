# Introducción a SQL con SQLite

Este material ofrece notas **didácticas** sobre el lenguaje **SQL** (Structured Query Language) usando **SQLite** como sistema de base de datos. Cubre los conceptos fundamentales de bases de datos relacionales. A lo largo de estas notas encontrarás explicaciones claras, ejemplos prácticos en código SQL y ejercicios sugeridos para practicar cada tema. *SQLite* es una base de datos relacional ligera y fácil de usar, ideal para practicar consultas SQL sin necesidad de configurar un servidor.

## ¿Qué es SQL?

SQL son las siglas de **Structured Query Language**, que en español significa *Lenguaje de Consulta Estructurado*. Es un lenguaje de consultas **estándar** utilizado para interactuar con bases de datos relacionales. En otras palabras, SQL nos permite **comunicarnos** con un sistema de gestión de bases de datos (DBMS) para definir la estructura de los datos y manipular la información almacenada.

Algunas características clave de SQL:

* **Declarativo**: En SQL usualmente se especifica *qué* datos se desean, no *cómo* obtenerlos exactamente. El motor de base de datos se encarga de planificar la mejor forma de ejecutar la consulta.
* **Estandarizado**: Existe un estándar ISO/ANSI SQL que la mayoría de sistemas de bases de datos sigue (con variaciones menores o *dialectos* específicos en cada sistema). Por ejemplo, sistemas populares que usan SQL incluyen Oracle, MySQL/MariaDB, PostgreSQL, Microsoft SQL Server y **SQLite**, entre otros.
* **Potente**: Con SQL se pueden realizar diversas operaciones: consultar datos (lectura), insertar nuevos datos, actualizar datos existentes, borrar datos, así como crear o modificar la estructura de la base de datos (tablas, índices, etc.).

En resumen, SQL es la herramienta principal para **gestionar y manipular datos** en bases de datos relacionales. A lo largo de estas notas aprenderás a usar SQL para realizar consultas y operaciones básicas, utilizando **SQLite** como plataforma de práctica (un motor de base de datos pequeño y sencillo integrado en un solo archivo).

**Ejercicios sugeridos:**

1. Investiga y enumera **tres sistemas de gestión de bases de datos** que utilicen SQL. Por ejemplo, Oracle es uno de ellos.
2. En tus propias palabras, escribe una breve definición de **SQL** y menciona una tarea que permite realizar en una base de datos.
3. Verifica si SQL distingue entre mayúsculas y minúsculas: por ejemplo, ¿`SELECT` y `select` producen el mismo resultado en SQLite? *(Pista: Puedes probar creando una pequeña tabla en SQLite y ejecutar consultas con diferente capitalización de palabras clave.)*

## Modelo entidad-relación

Antes de escribir consultas SQL, es importante entender cómo se **modelan** los datos en una base de datos. El **modelo entidad-relación (ER)** es una forma de diseñar la estructura lógica de una base de datos mediante un **diagrama entidad-relación (ERD)**. Este modelo nos permite identificar:

* **Entidades**: Son los objetos o conceptos principales sobre los cuales almacenaremos datos. Por ejemplo, en un contexto universitario podrían ser *Estudiante*, *Curso*, *Profesor*, etc. Cada entidad se representa usualmente como una tabla en la base de datos.
* **Atributos**: Son las propiedades o características de cada entidad. Por ejemplo, la entidad Estudiante podría tener atributos como código (identificación), nombre, edad, ciudad, etc. En una tabla, los atributos corresponden a las **columnas**.
* **Relaciones**: Describen cómo se asocian o conectan las entidades entre sí. Por ejemplo, un estudiante **se inscribe** en un curso; esa es una relación entre las entidades Estudiante y Curso. Las relaciones pueden tener *cardinalidades* (por ejemplo, uno a muchos, muchos a muchos, etc.) que indican cuántas instancias de una entidad se pueden asociar con otra. En un diagrama ER, las entidades suelen dibujarse como rectángulos y las relaciones como líneas o rombos que conectan las entidades.

**Ejemplo (escenario universitario):** Imaginemos un sistema simple de gestión de cursos. Podemos identificar las siguientes entidades y relaciones:

* **Estudiante**: con atributos como *EstudianteID*, *Nombre*, *Edad*, *Ciudad*, etc.
* **Curso**: con atributos como *CursoID*, *NombreCurso*, *Creditos*, etc.
* **Inscripción**: representa la relación de muchos a muchos entre Estudiante y Curso (un estudiante puede inscribirse en muchos cursos, y un curso tiene muchos estudiantes inscritos). Esta podría considerarse una entidad relación con atributos propios como *InscripcionID*, *EstudianteID*, *CursoID* y *Nota* (calificación obtenida).

En el modelo ER, *Inscripción* se vincula con *Estudiante* y *Curso*. Cada registro de inscripción conecta un estudiante con un curso específico, pudiendo almacenar además la nota del estudiante en ese curso.

Comprender el modelo entidad-relación te ayuda a visualizar cómo estructurarás la base de datos y cómo las tablas estarán **relacionadas** entre sí. Una vez definido el modelo, podemos crear las tablas físicas en SQLite y comenzar a consultar datos con SQL.

**Ejercicios sugeridos:**

1. Piensa en un sistema sencillo (por ejemplo, una biblioteca, una tienda o un sistema escolar) e identifica al menos **3 entidades** principales y algunos atributos para cada una. Luego, describe **qué relaciones** existen entre esas entidades (por ejemplo, "Un *Libro* puede ser prestado a muchos *Usuarios* en la biblioteca").
2. Dibuja (en papel o digital) un pequeño **diagrama ER** para el escenario que imaginaste en el ejercicio anterior, mostrando entidades, atributos clave y relaciones. No es necesario que sea muy detallado; concéntrate en reflejar cómo se conectan las entidades.
3. En el diagrama ER de la universidad mencionado (Estudiante, Curso, Inscripción), identifica la **cardinalidad** de la relación entre Estudiante y Curso a través de Inscripción (por ejemplo, ¿uno a uno, uno a muchos, muchos a muchos?) e indica cómo se representaría eso en el modelo (pista: Inscripción como tabla intermedia en caso de muchos a muchos).

## Llaves primaria y foránea

En las bases de datos relacionales, es esencial garantizar que cada registro sea identificable de manera única y que las relaciones entre tablas se mantengan consistentes. Para lograr esto se usan **llaves (claves) primaria y foránea**:

* **Llave primaria (Primary Key)**: Es un atributo (columna) o combinación de atributos que **identifica de manera única** cada registro de una tabla. Ningún valor de llave primaria se repite en esa tabla, y por lo general no debe ser NULL (nulo). Por ejemplo, en la tabla Estudiante podríamos usar *EstudianteID* como llave primaria: cada estudiante tendrá un ID único.
* **Llave foránea (Foreign Key)**: Es un atributo en una tabla que **referencia** la llave primaria de otra tabla. Esto crea una **relación** entre las dos tablas y garantiza la **integridad referencial** – es decir, que el valor de la llave foránea siempre corresponda a un registro válido en la otra tabla. Por ejemplo, *EstudianteID* en la tabla Inscripción es una llave foránea que referencia al *EstudianteID* (llave primaria) de la tabla Estudiante. Esto asegura que no podamos crear una inscripción para un estudiante que no exista. Del mismo modo, *CursoID* en Inscripción sería foránea que referencia a *CursoID* en la tabla Curso.

En SQLite (y otros sistemas SQL) definimos las llaves al **crear la tabla**. Veamos cómo se traducen nuestras entidades de ejemplo a definiciones de tablas con llaves primaria y foránea:

```sql
CREATE TABLE Estudiante (
    EstudianteID INTEGER PRIMARY KEY,   -- Llave primaria, identificador único
    Nombre       TEXT,
    Edad         INTEGER,
    Ciudad       TEXT
);
```

```sql
CREATE TABLE Curso (
    CursoID     INTEGER PRIMARY KEY,   -- Llave primaria de Curso
    NombreCurso TEXT,
    Creditos    INTEGER
);
```

```sql
CREATE TABLE Inscripcion (
    InscripcionID INTEGER PRIMARY KEY,            -- Llave primaria de Inscripcion
    EstudianteID  INTEGER,                       -- Llave foránea a Estudiante
    CursoID       INTEGER,                       -- Llave foránea a Curso
    Nota          REAL,
    FOREIGN KEY (EstudianteID) REFERENCES Estudiante(EstudianteID),
    FOREIGN KEY (CursoID)     REFERENCES Curso(CursoID)
);
```

En las definiciones SQL anteriores:

* Se usa `PRIMARY KEY` para definir la llave primaria de cada tabla.
* En la tabla Inscripcion, las líneas `FOREIGN KEY (...) REFERENCES ...` establecen las llaves foráneas, indicando qué tabla y columna referencian. Por ejemplo, `FOREIGN KEY (EstudianteID) REFERENCES Estudiante(EstudianteID)` asegura que cualquier valor de EstudianteID en Inscripcion coincida con un EstudianteID existente en la tabla Estudiante.

> 💡 **Nota:** SQLite permite el uso de llaves foráneas, pero por defecto la verificación de integridad referencial puede estar deshabilitada. Si practicas estos ejemplos en SQLite, asegúrate de habilitar la verificación de foráneas ejecutando la instrucción `PRAGMA foreign_keys = ON;`. En otros sistemas de bases de datos, las llaves foráneas funcionan automáticamente al definirlas.

**Ejercicios sugeridos:**

1. En el modelo de base de datos que diseñaste en la sección anterior, identifica una posible **llave primaria** para cada entidad (tabla). ¿Qué atributo único puede servir para identificar cada registro?
2. Siguiendo con tu modelo, elige una de las relaciones e indica cómo implementarías una **llave foránea**. Por ejemplo: "En la tabla Préstamo, el atributo *UsuarioID* será llave foránea que referencia a *UsuarioID* en la tabla Usuario".
3. Examina las sentencias `CREATE TABLE` de ejemplo provistas arriba. ¿Qué ocurre si intentamos insertar un registro en Inscripcion con un *EstudianteID* que **no existe** en la tabla Estudiante? (Puedes razonar la respuesta o probar en SQLite después de crear las tablas).

## Consultas básicas (SELECT, INSERT, UPDATE, DELETE)

Una vez definidas las tablas y sus relaciones, podemos manipular los datos utilizando las **consultas básicas** de SQL. Las operaciones fundamentales se conocen a veces como **CRUD** (Create, Read, Update, Delete): creación, lectura, actualización y eliminación de datos. En SQL, estas corresponden a cuatro sentencias principales:

* **SELECT**: Leer o consultar datos almacenados (operación de *lectura*).
* **INSERT**: Insertar nuevos datos en la tabla (operación de *creación*).
* **UPDATE**: Actualizar o modificar datos existentes (operación de *actualización*).
* **DELETE**: Borrar datos de la tabla (operación de *eliminación*).

A continuación, explicamos cada una con ejemplos usando las tablas de nuestro escenario de estudiantes y cursos.

### SELECT – Consultar datos

La sentencia `SELECT` se usa para **consultar y recuperar datos** de una o varias tablas. Su sintaxis básica es:

```sql
SELECT <columnas>
FROM <tabla>
WHERE <condicion>;
```

* `<columnas>`: Lista de columnas que queremos ver (por ejemplo, Nombre, Edad). Si se quiere seleccionar *todas* las columnas de la tabla, se puede usar `SELECT *`.
* `<tabla>`: La tabla de la cual obtener los datos.
* `<condicion>`: (Opcional) Criterio para filtrar los registros que se devuelven. Si se omite `WHERE`, la consulta traerá **todos** los registros de la tabla.

**Ejemplo:** Obtener todos los estudiantes registrados:

```sql
SELECT * 
FROM Estudiante;
```

*Explicación:* Este query selecciona todas las columnas (`*`) de la tabla Estudiante. El resultado sería una lista de todos los estudiantes con todos sus datos. Si la tabla Estudiante tiene, por ejemplo, 5 registros, la consulta retornará esos 5 registros completos.

**Ejemplo:** Listar solo los nombres de todos los cursos disponibles:

```sql
SELECT NombreCurso
FROM Curso;
```

Esto traerá únicamente la columna "NombreCurso" de cada registro en la tabla Curso.

Podemos renombrar columnas en la salida usando alias, mediante la palabra clave `AS`. Por ejemplo, si quisiéramos mostrar los nombres de estudiantes pero con un encabezado distinto:

```sql
SELECT Nombre AS NombreEstudiante
FROM Estudiante;
```

Esto no cambia la tabla, solo etiqueta la columna en el resultado como "NombreEstudiante".

### INSERT – Insertar nuevos registros

La sentencia `INSERT` permite **agregar nuevos registros** (filas) a una tabla. Hay dos formas comunes:

* Especificar los nombres de columnas a llenar y luego los valores.
* Omitir los nombres de columnas si vas a proporcionar un valor para *todas* las columnas en el orden exacto definido.

La sintaxis generalmente es:

```sql
INSERT INTO <tabla> (<col1>, <col2>, ...)
VALUES (<val1>, <val2>, ...);
```

**Ejemplo:** Agregar un nuevo estudiante a la tabla Estudiante:

```sql
INSERT INTO Estudiante (EstudianteID, Nombre, Edad, Ciudad)
VALUES (1, 'Ana Gomez', 20, 'Bogota');
```

*Explicación:* Esto inserta en la tabla Estudiante un registro con ID = 1, Nombre = "Ana Gomez", Edad = 20, Ciudad = "Bogota". Hemos especificado los nombres de columnas para mayor claridad; los valores deben corresponder en orden a esas columnas. Las cadenas de texto van entre comillas simples `'...'`, mientras que los números se escriben sin comillas.

Si la tabla tiene una columna autoincremental (en SQLite, una PRIMARY KEY definida como INTEGER puede comportarse como autoincremental), podríamos omitir esa columna en la lista y en los VALUES dejar que la base de datos asigne el siguiente ID automáticamente.

**Ejemplo:** Insertar un curso nuevo en Curso (asumiendo CursoID autoincremental):

```sql
INSERT INTO Curso (NombreCurso, Creditos)
VALUES ('Fisica', 4);
```

Aquí no especificamos `CursoID`, asumiendo que SQLite asignará uno automáticamente. El nuevo curso "Fisica" de 4 créditos se agrega con un ID único generado.

### UPDATE – Actualizar datos existentes

La sentencia `UPDATE` se usa para **modificar los valores** de columnas de uno o varios registros existentes. Su sintaxis simplificada:

```sql
UPDATE <tabla>
SET <columna1> = <valor1>, <columna2> = <valor2>, ...
WHERE <condicion>;
```

* `<tabla>`: La tabla en la que se desea actualizar datos.
* En `SET`, se especifican las columnas a cambiar con sus nuevos valores.
* `WHERE` determina **qué registros** se van a actualizar. **¡Muy importante!**: Si se omite `WHERE`, la actualización se aplicará a *todos* los registros de la tabla, lo cual puede no ser deseado.

**Ejemplo:** Supongamos que la estudiante con EstudianteID = 1 (Ana Gomez) cambia de ciudad de residencia a Medellin. Para actualizar ese dato:

```sql
UPDATE Estudiante
SET Ciudad = 'Medellin'
WHERE EstudianteID = 1;
```

*Explicación:* Esto busca en la tabla Estudiante el registro donde EstudianteID sea 1, y cambia el valor de la columna Ciudad a "Medellin" para ese registro. Ningún otro estudiante se ve afectado gracias a la condición `WHERE EstudianteID = 1`. Si no incluyéramos la cláusula WHERE, **todos** los estudiantes tendrían ahora Ciudad = 'Medellin', lo cual no sería correcto.

### DELETE – Eliminar registros

La sentencia `DELETE` sirve para **eliminar registros** completos de una tabla. Sintaxis básica:

```sql
DELETE FROM <tabla>
WHERE <condicion>;
```

* `WHERE` indica qué registro(s) borrar. Al igual que con UPDATE, omitir `WHERE` significa borrar **todas** las filas de la tabla (lo cual usualmente no es lo que se desea, a menos que estemos vaciando la tabla intencionalmente).

**Ejemplo:** Eliminar de la tabla Curso el curso con ID 3:

```sql
DELETE FROM Curso
WHERE CursoID = 3;
```

Esto borrará el registro cuyo CursoID sea 3. Si ese curso tenía inscripciones asociadas, esas filas en Inscripcion quedarían *huérfanas* (referenciando un curso que ya no existe), violando la integridad referencial. Por eso, muchos sistemas (incluyendo SQLite si las foreign keys están habilitadas) impedirán este borrado o bien borrarán en cascada las inscripciones relacionadas dependiendo de la configuración. En nuestro caso, si `PRAGMA foreign_keys = ON`, SQLite no permitirá borrar el curso con ID 3 mientras existan filas en Inscripcion que lo referencien, a menos que se eliminen primero esas inscripciones.

**Resumen de las consultas básicas:**

* `SELECT` para leer datos.
* `INSERT` para crear nuevos datos.
* `UPDATE` para modificar datos existentes.
* `DELETE` para eliminar datos.

Estas operaciones cubren la manipulación esencial de la información en las tablas.

**Ejercicios sugeridos:**

Usando las tablas del ejemplo (Estudiante, Curso, Inscripcion), escribe las consultas SQL para realizar las siguientes operaciones:

1. **Seleccionar**: Obtén una lista de todos los estudiantes mostrando solo sus nombres y edades.
2. **Seleccionar con filtro**: Consulta los cursos (CursoID y NombreCurso) que tengan 4 créditos (asume que existen algunos con ese valor de créditos).
3. **Insertar**: Agrega un nuevo estudiante a la tabla Estudiante con tus propios datos ficticios (elige un ID no existente, un nombre y detalles cualquiera). Luego, inserta una nueva inscripción en Inscripcion para matricular a ese estudiante en algún curso existente.
4. **Actualizar**: Imagina que hubo un error y necesitas cambiar el nombre de un curso. Escribe una sentencia UPDATE para renombrar el curso con CursoID = 2 a "Calculo".
5. **Eliminar**: Escribe una sentencia para eliminar de la tabla Inscripcion todas las inscripciones del estudiante con EstudianteID = 1 (por ejemplo, si el estudiante se dio de baja de la universidad). *Piensa:* ¿Qué sucede si ejecutas esta sentencia y luego consultas las inscripciones de ese estudiante?

## Filtros: WHERE y operadores de condición

En muchas ocasiones no queremos aplicar nuestras consultas a todos los datos de una tabla, sino a un **subconjunto** que cumpla ciertos criterios. Ahí es donde entra la cláusula `WHERE`, que permite **filtrar** las filas en base a una condición booleana (verdadera/falsa). Junto con `WHERE`, se usan operadores **relacionales** (de comparación) y **lógicos** para construir condiciones más complejas.

### Operadores relacionales (de comparación)

Algunos de los operadores más comunes para comparar valores en SQL son:

* `=` : Igual a (==).
* `<>` o `!=` : Distinto de (no igual a).
* `<`  : Menor que.
* `<=` : Menor o igual que.
* `>`  : Mayor que.
* `>=` : Mayor o igual que.

Estos operadores se usan para comparar valores de columnas con algún valor literal o incluso con otra columna.

**Ejemplo:** Obtener estudiantes **mayores de 18 años**:

```sql
SELECT Nombre, Edad
FROM Estudiante
WHERE Edad > 18;
```

Aquí, `Edad > 18` es la condición; la consulta devolverá solo aquellos estudiantes cuyo valor en la columna Edad sea mayor que 18. Los estudiantes de 18 o menos no aparecerán en el resultado.

**Ejemplo:** Consultar cursos con **exactamente 3 créditos**:

```sql
SELECT CursoID, NombreCurso
FROM Curso
WHERE Creditos = 3;
```

Solo veremos los cursos cuyo número de créditos sea 3.

También podemos filtrar por texto usando `=` (coincidencia exacta). Por ejemplo, buscar estudiantes de una ciudad específica:

```sql
SELECT Nombre, Ciudad
FROM Estudiante
WHERE Ciudad = 'Medellin';
```

Esto listará únicamente los estudiantes cuya columna Ciudad coincide exactamente con "Medellin". La comparación de texto en SQL suele ser **sensible a mayúsculas/minúsculas dependiendo del collation**; en SQLite, las comparaciones por defecto son case-insensitive para texto, por lo que 'medellin' y 'Medellin' serían consideradas iguales.

### Operadores lógicos (AND, OR, NOT)

Para combinar múltiples condiciones, utilizamos operadores lógicos:

* `AND` (y lógico): Todas las condiciones unidas por AND deben ser verdaderas para que la fila sea seleccionada.
* `OR` (o lógico): Basta que **al menos una** de las condiciones unidas por OR sea verdadera para que la fila sea seleccionada.
* `NOT` (negación lógica): Invierte el valor de verdad de una condición (TRUE a FALSE o viceversa).

**Ejemplo:** Obtener estudiantes mayores de 18 **Y** que vivan en Medellin:

```sql
SELECT Nombre, Edad, Ciudad
FROM Estudiante
WHERE Edad > 18 
  AND Ciudad = 'Medellin';
```

Aquí tanto la condición de la edad como la de la ciudad deben cumplirse. Si un estudiante tiene 20 años pero vive en Bogotá, no aparecerá; tampoco si vive en Medellín pero tiene 17 años. Solo estudiantes con edad > 18 *y* ciudad = Medellin pasarán el filtro.

**Ejemplo:** Obtener cursos con 3 **o** 4 créditos:

```sql
SELECT NombreCurso, Creditos
FROM Curso
WHERE Creditos = 3
   OR Creditos = 4;
```

Esto devolverá cursos que tengan 3 créditos, 4 créditos, o ambos. Con OR, una fila es seleccionada si cumple al menos una de las condiciones (en este caso, créditos igual a 3 o igual a 4).

**Ejemplo:** Obtener estudiantes que **NO** sean de Medellin:

```sql
SELECT Nombre, Ciudad
FROM Estudiante
WHERE NOT Ciudad = 'Medellin';
```

La condición `NOT Ciudad = 'Medellin'` es verdadera para estudiantes cuya ciudad *no* es Medellin. Equivalente a `Ciudad <> 'Medellin'`. Esta consulta listará todos los estudiantes excepto aquellos de Medellin.

Se pueden combinar múltiples condiciones con AND/OR, teniendo en cuenta que **AND tiene prioridad** sobre OR (similar a la multiplicación tiene prioridad sobre suma en aritmética). Es recomendable usar paréntesis `()` para evitar ambigüedades cuando se mezclan AND y OR en una misma cláusula WHERE.

**Ejemplo (combinando varios):** estudiantes mayores de 18 **que** (sean de Medellin **o** de Bogota):

```sql
SELECT Nombre, Edad, Ciudad
FROM Estudiante
WHERE Edad > 18
  AND (Ciudad = 'Medellin' OR Ciudad = 'Bogota');
```

Los paréntesis aseguran que la condición compuesta de ciudad se evalúe correctamente como un bloque.

## Operador LIKE (Patrones de texto)

El operador **LIKE** permite filtrar filas comparando el valor de una columna de tipo texto con un **patrón** que puede incluir comodines. Se usa en la cláusula `WHERE` junto con los siguientes comodines:

* `%`  : Representa **cero o mas** caracteres cualesquiera.
* `_`  : Representa **exactamente 1** caracter cualquiera.

### Sintaxis

```sql
SELECT <columnas>
FROM <tabla>
WHERE <columna_texto> LIKE '<patron>';
```

* `<columna_texto>`: columna de tipo texto sobre la cual se aplica el patron.
* `<patron>`: cadena entre comillas simples que incluye texto literal y comodines `%` o `_`.

### Ejemplos

1. **Coincidir texto al inicio**
   Obtener cursos cuyo nombre empiece con "Intro":

   ```sql
   SELECT CursoID, NombreCurso
   FROM Curso
   WHERE NombreCurso LIKE 'Intro%';
   ```

   – El patron `Intro%` encuentra cualquier cadena que inicie con "Intro" y continúe con cero o mas caracteres.

2. **Coincidir texto al final**
   Listar estudiantes cuyo apellido termine en "rez":

   ```sql
   SELECT Nombre
   FROM Estudiante
   WHERE Nombre LIKE '%rez';
   ```

   – `%rez` matchea nombres que terminen en "rez" (por ejemplo "Perez", "Gutierrez").

3. **Coincidir subcadena en medio**
   Buscar ciudades que contengan la letra "e" en cualquier posicion:

   ```sql
   SELECT DISTINCT Ciudad
   FROM Estudiante
   WHERE Ciudad LIKE '%e%';
   ```

   – `%e%` encuentra cualquier cadena que tenga al menos una "e" en cualquier parte.

4. **Usar guion bajo para reemplazar un solo caracter**
   Encontrar ciudades de cuatro letras donde la segunda letra sea "o":

   ```sql
   SELECT DISTINCT Ciudad
   FROM Estudiante
   WHERE Ciudad LIKE '_o__';
   ```

   – `_o__` significa: 1 caracter cualquiera, luego "o", luego 2 caracteres cualesquiera.

5. **Combinar comodines**
   Cursos que empiecen por cualquier letra seguida de "ogo" y terminen con cualquier numero de caracteres:

   ```sql
   SELECT CursoID, NombreCurso
   FROM Curso
   WHERE NombreCurso LIKE '_ogo%';
   ```

   – `_ogo%` coincide con cadenas como "LogoDesign", "BogoIntro", etc., donde "ogo" esta en posiciones 2–4.

> **Nota**: En SQLite las comparaciones con LIKE son por defecto **insensibles** a mayusculas/minusculas para texto ASCII. En otros motores de BD puede ser sensible o requerir funciones adicionales (por ejemplo `ILIKE` en PostgreSQL).
> 
---


**Ejercicios sugeridos:**

Para practicar el filtrado de datos, intenta escribir las consultas SQL para las siguientes peticiones:

1. Lista los **estudiantes menores o iguales a 18 años**. Muestra nombre, edad y ciudad.
2. Obtén todos los **cursos** cuyo nombre sea "Programación" **o** "Bases de Datos". *(Pista: utiliza OR en la condición, comparando la columna NombreCurso con cada valor.)*
3. Encuentra los **estudiantes de Bogotá** mayores de 20 años. (Combina condición de ciudad y edad con AND).
4. Muestra las inscripciones (tabla Inscripcion) donde la **nota** sea mayor o igual a 3.5 **y** el **CursoID sea 2**.
5. Escribe una consulta que liste los cursos de 2 créditos o 3 créditos, pero excluya (NOT) aquellos cursos cuyo nombre comience con "Intro". *\[**Nota:** Para este último podría ser necesario usar una condición con operador LIKE para filtrar por texto, e.g., `NombreCurso LIKE 'Intro%'`.]*
6. Listar todos los estudiantes cuyo nombre **inicie** con la letra "A".
7. Obtener los cursos cuyo nombre **termine** con la palabra "Basico" (por ejemplo, "SQL Basico").
8. Buscar las ciudades que **no** empiecen con la letra "B". *(Hint: usar `NOT LIKE 'B%'`).*
9. Mostrar los estudiantes cuyo nombre tenga **exactamente cinco** caracteres. *(Hint: usar `LIKE '_____'` con cinco guiones bajos).*
10. Encontrar cursos que contengan la subcadena "Data" en cualquier parte del nombre.

## Funciones de agregación (SUM, AVG, COUNT, MIN, MAX)

Las funciones de agregación en SQL nos permiten realizar cálculos **sobre conjuntos de filas** y obtener un resultado único. Son muy útiles para obtener estadísticas o resúmenes de los datos. Las funciones de agregación más comunes son:

* `COUNT` – Cuenta la cantidad de registros (filas) que cumplen alguna condición.
* `SUM` – Suma los valores de una columna (normalmente numérica) en las filas seleccionadas.
* `AVG` – Calcula el **promedio** (media aritmética) de los valores de una columna numérica.
* `MIN` – Encuentra el valor **mínimo** en una columna (numérica o de fecha, etc., incluso texto en orden alfabético).
* `MAX` – Encuentra el valor **máximo** en una columna.

Estas funciones se usan típicamente junto con `SELECT`. Importante: salvo que se utilice junto con `GROUP BY` (ver próxima sección), las funciones de agregación comprimen todo el conjunto de resultados en una sola fila. Es decir, si usamos una función agregada en un SELECT sin GROUP BY, el resultado será un solo valor (o unas pocas columnas agregadas).

**Ejemplos individuales de funciones:**

* Obtener el **total de estudiantes** registrados:

```sql
SELECT COUNT(*) 
FROM Estudiante;
```

Esto retornará un único número, que es el conteo de filas en la tabla Estudiante. `COUNT(*)` cuenta todas las filas, independientemente de valores nulos o duplicados. Si quisiéramos contar solo aquellos con un valor no nulo en una columna específica, podríamos usar `COUNT(Nombre)` por ejemplo, que contaría únicamente las filas donde Nombre no es NULL.

* Calcular la **edad promedio** de los estudiantes:

```sql
SELECT AVG(Edad) 
FROM Estudiante;
```

Devuelve un valor numérico que representa el promedio de las edades de todos los estudiantes. Si por ejemplo las edades fueran 18, 20, 22, el AVG sería 20.0.

* Sumar la **cantidad total de créditos** de todos los cursos:

```sql
SELECT SUM(Creditos) 
FROM Curso;
```

Si la tabla Curso tiene cursos con 3, 4 y 2 créditos, la suma total sería 9.

* Encontrar la **nota mínima y máxima** registrada en la tabla Inscripcion:

```sql
SELECT MIN(Nota), MAX(Nota)
FROM Inscripcion;
```

Esto puede devolver, por ejemplo, 1.5 (nota mínima) y 5.0 (nota máxima) si esas son las calificaciones más baja y más alta registradas. En la salida tendríamos dos columnas: la primera con el valor mínimo y la segunda con el máximo.

**Nota sobre NULL:** Las funciones de agregación (excepto COUNT(\*)) por defecto **ignoran los valores NULL** en la columna sobre la cual operan. Por ejemplo, si algún estudiante no tuviera edad registrada (Edad NULL), esa fila no contaría para el AVG(Edad). Ten esto en cuenta, ya que puede afectar los resultados sin que lo notes a primera vista.

Es común usar alias para dar nombres a los resultados agregados. Por ejemplo:

```sql
SELECT COUNT(*) AS TotalEstudiantes
FROM Estudiante;
```

Así la columna resultado se llamará "TotalEstudiantes" en lugar de "COUNT(\*)".

**Ejercicios sugeridos:**

1. ¿Cuántos cursos hay en la tabla Curso? Escribe una consulta usando `COUNT`.
2. Obtén la **suma total de créditos** de todos los cursos ofertados (usa `SUM`).
3. Calcula el **promedio de notas** de la tabla Inscripcion (usa `AVG(Nota)`). ¿Qué sucede con el promedio si algunas inscripciones no tienen nota (es decir, Nota es NULL)?
4. Encuentra la **edad mínima y máxima** entre los estudiantes registrados (usa `MIN` y `MAX` en la columna Edad).
5. *(Desafío adicional)*: ¿Cuál es el **promedio de créditos** por curso? *(Pista: puedes dividir la suma total de créditos entre el conteo de cursos, o usar directamente AVG sobre la columna Creditos.)*

## GROUP BY (Agrupar resultados)

La cláusula `GROUP BY` se utiliza en SQL para **agrupar filas** que tengan el mismo valor en una o varias columnas, de modo que se puedan aplicar funciones de agregación a cada grupo por separado. En lugar de obtener un solo resultado agregado para toda la tabla, obtendremos un resultado por **grupo**.

Imagina que quieres respuestas a preguntas del tipo: "¿cuántos... por cada ...?" o "promedio de ... para cada ...". Por ejemplo: "¿Cuántos estudiantes hay **por ciudad**?" o "Promedio de nota **por curso**". Estos son casos para `GROUP BY`.

**Sintaxis básica con GROUP BY:**

```sql
SELECT <columna_clave>, <función_agregación>(<columna>)
FROM <tabla>
GROUP BY <columna_clave>;
```

Donde `<columna_clave>` es la columna por la que agrupamos (por ejemplo, Ciudad), y la función de agregación se aplicará a cada grupo de filas que comparten el mismo valor en esa columna clave.

**Ejemplo:** Contar cuántos estudiantes hay en cada ciudad:

```sql
SELECT Ciudad, COUNT(*) AS CantidadEstudiantes
FROM Estudiante
GROUP BY Ciudad;
```

*Explicación:* Esta consulta agrupa los registros de Estudiante por el valor de la columna Ciudad. Por cada ciudad distinta, se calcula `COUNT(*)`. El resultado podría ser por ejemplo:

```
Ciudad      | CantidadEstudiantes
----------- | -------------------
Bogota      | 10
Medellin    | 7
Cali        | 4
```

(asumiendo 10 estudiantes de Bogotá, 7 de Medellín, 4 de Cali en la tabla).

Cada fila en el resultado representa un **grupo** (una ciudad) con el conteo de estudiantes en ella. La columna `Ciudad` que se selecciona debe aparecer también en el GROUP BY (es la regla SQL: toda columna en SELECT que **no** está dentro de una función de agregación, debe estar listada en GROUP BY).

**Ejemplo:** Promedio de nota por Curso (supongamos que queremos ver la nota promedio que obtienen los estudiantes en cada curso):

```sql
SELECT CursoID, AVG(Nota) AS PromedioNota
FROM Inscripcion
GROUP BY CursoID;
```

Esto agrupará las inscripciones por identificador de curso. Imaginemos que en Inscripcion tenemos múltiples registros para CursoID 1, múltiples para CursoID 2, etc., cada grupo representa un curso, y calculamos AVG(Nota) en ese grupo. El resultado nos da un promedio de notas para cada CursoID. Podríamos luego relacionar el CursoID con la tabla Curso para saber el nombre, pero con subconsultas o JOINS (tema más avanzado) se lograría. Por ahora, nos centramos en que `GROUP BY CursoID` permite obtener resultados agregados curso por curso.

Se pueden agrupar por más de una columna si se necesita jerarquía de grupos, pero eso es más avanzado (por ejemplo, agrupar por Departamento y dentro de cada uno por Ciudad, etc.). Para empezar, lo usual es agrupar por una sola categoría.

**Nota:** Si usas `GROUP BY`, **solo** puedes seleccionar en la parte de columnas:

* La(s) columna(s) por la que agrupaste, y
* Agregaciones (SUM, COUNT, etc.) de otras columnas.

No puedes incluir columnas que no estén agregadas ni en el GROUP BY, porque el resultado no sabría qué valor mostrar (ya que dentro de un grupo podría haber varios valores diferentes). Por ejemplo, en el primer ejemplo no podemos añadir Nombre (de estudiante) directamente al SELECT, porque cada ciudad tiene muchos nombres posibles; tendría que ser parte de una agregación (como maybe listing count of names, but count(\*) covers that anyway).

**Ejercicios sugeridos:**

1. Usando la tabla Estudiante, obtén cuántos estudiantes hay por cada **ciudad** (como el ejemplo anterior).
2. A partir de la tabla Curso, digamos que queremos saber cuántos cursos hay por cada cantidad de créditos. Escribe una consulta que muestre "Creditos" y la cantidad de cursos que tienen esa cantidad de créditos. (Hint: `GROUP BY Creditos`).
3. En la tabla Inscripcion, obtén el **promedio de nota por Estudiante**. Debes agrupar por EstudianteID y calcular AVG(Nota). ¿Qué indica el resultado para cada estudiante?
4. *(Avanzado)* Si existiera una columna "Carrera" en la tabla Estudiante (por ejemplo Ingeniería, Matemáticas, etc.), ¿cómo obtendrías el número de estudiantes por carrera? Escribe la consulta con GROUP BY asumiendo que la columna se llamara Carrera.
5. Reflexiona: ¿En qué se diferencia `COUNT(*)` de `COUNT(columna)` cuando se usa junto con GROUP BY? (Pista: piensa en valores NULL en la columna).

## HAVING (Filtrar grupos)

La cláusula `HAVING` se utiliza junto con `GROUP BY` para **filtrar los grupos** resultado de una agregación. Es muy similar conceptualmente a `WHERE`, pero mientras `WHERE` filtra filas individuales *antes* de la agregación, `HAVING` filtra *después* de que los datos han sido agrupados. En otras palabras, `HAVING` permite poner condiciones sobre los resultados agregados.

**Sintaxis típica:**

```sql
SELECT <columna_clave>, <función_agregación>(columna)
FROM <tabla>
GROUP BY <columna_clave>
HAVING <condición sobre agregación>;
```

La condición en HAVING usualmente involucra alguna función de agregación o columna agrupada.

**Ejemplo sin HAVING (recapitulación):**
Del ejemplo anterior, teníamos el conteo de estudiantes por ciudad:

```sql
SELECT Ciudad, COUNT(*) AS Cantidad
FROM Estudiante
GROUP BY Ciudad;
```

Ahora supongamos que solo nos interesan las ciudades con **más de 5 estudiantes**. No podemos poner `WHERE COUNT(*) > 5` directamente, porque `WHERE` no acepta agregaciones en esa fase. En su lugar, usamos HAVING:

```sql
SELECT Ciudad, COUNT(*) AS Cantidad
FROM Estudiante
GROUP BY Ciudad
HAVING COUNT(*) > 5;
```

*Explicación:* Primero se agrupa la tabla por Ciudad, luego HAVING filtra esos grupos dejando solo aquellos cuyo `COUNT(*)` (cantidad de estudiantes en la ciudad) es mayor que 5. El resultado mostrará únicamente las ciudades con más de 5 estudiantes y la respectiva cantidad.

**Ejemplo:** Obtener el promedio de nota por curso (como antes), pero mostrar solo los cursos cuyo promedio de nota sea **aprobatorio (>= 3.0)**:

```sql
SELECT CursoID, AVG(Nota) AS PromedioNota
FROM Inscripcion
GROUP BY CursoID
HAVING AVG(Nota) >= 3.0;
```

Aquí, después de agrupar por CursoID, usamos HAVING para quedarnos solo con aquellos grupos (cursos) donde la condición `AVG(Nota) >= 3.0` se cumple, es decir, cursos donde el promedio de calificación es 3.0 o más.

Otro uso común de HAVING es filtrar por la agregación de `COUNT`. Por ejemplo, "cursos con al menos 5 inscripciones":

```sql
SELECT CursoID, COUNT(*) AS NumInscritos
FROM Inscripcion
GROUP BY CursoID
HAVING COUNT(*) >= 5;
```

Esto listaría los IDs de curso que tienen 5 o más estudiantes inscritos (asumiendo que cada fila de Inscripcion es un estudiante en ese curso). Si queremos ver el nombre del curso en lugar del ID, necesitaríamos combinar con la tabla Curso (lo cual implicaría un JOIN o subconsulta). Pero enfocándonos en HAVING, la idea está en poder filtrar grupos por condiciones de agregados.

**Importante:** Si en `SELECT` se usa alias (como `COUNT(*) AS NumInscritos`), **no puedes usar ese alias directamente dentro de HAVING** en muchos sistemas de SQL. Debes repetir la función, o algunos motores permiten la condición sobre alias pero SQLite no. En SQLite, la cláusula HAVING puede referirse a una expresión agregada ya sea repitiéndola o usando posición de la columna de salida (no recomendable). Es más claro poner `HAVING COUNT(*) >= 5` que `HAVING NumInscritos >= 5` para asegurarse.

**Ejercicios sugeridos:**

1. De la consulta de estudiantes por ciudad en el apartado anterior, añade HAVING para mostrar solo las ciudades con **2 o menos estudiantes** (<= 2).
2. Usando la tabla Inscripcion, escribe una consulta que muestre los CursoID cuya **cantidad de inscripciones** (COUNT) sea 0. *(Pista: podrías hacerlo con HAVING COUNT(*) = 0, pero ten en cuenta que si no hay inscripciones para un curso, ese curso ni siquiera aparecerá en la tabla Inscripcion para agrupar. Otra forma sería usando subconsulta; si te parece complejo, asume que quieres cursos con menos de 2 inscripciones, por ejemplo.)\*
3. Imagina que la tabla Estudiante tuviera una columna Carrera (como en el ejercicio anterior). Obtén las carreras con más de 10 estudiantes. (GROUP BY Carrera HAVING COUNT(\*) > 10).
4. ¿Puedes combinar condiciones de HAVING con operadores lógicos? Por ejemplo, "ciudades con más de 5 estudiantes **y** con promedio de edad > 20". ¿Cómo luciría esa consulta? (Pista: HAVING COUNT(\*) > 5 AND AVG(Edad) > 20).
5. Reflexiona: ¿Por qué no podemos usar `WHERE AVG(Nota) >= 3.0` en lugar de `HAVING` en el ejemplo inicial de promedio por curso? Explica con tus palabras qué hace primero SQL: el filtrado de filas o el agrupamiento.

## Subconsultas (Subqueries)

Una **subconsulta** es una consulta SQL anidada dentro de otra consulta principal. Las subconsultas permiten obtener resultados intermedios que luego se usan en la consulta exterior. Son útiles para resolver consultas que requieren múltiples pasos lógicos, de forma anidada en una sola sentencia SQL.

Podemos usar subconsultas en varias partes de una sentencia:

* En la cláusula `WHERE` (subconsulta escalar que devuelve un solo valor, o subconsulta que devuelve un conjunto de valores para usar con IN, por ejemplo).
* En la cláusula `FROM` (como si fuera una tabla derivada o "subtabla").
* En la cláusula `SELECT` (subconsultas correlacionadas que calculan algo por fila).
* Entre otras.

En una introducción, nos enfocaremos en subconsultas en la cláusula **WHERE**, que es un caso común y fácil de entender.

**Ejemplo 1:** Supongamos que queremos listar los estudiantes que están inscritos en el curso con CursoID = 2. Podríamos resolverlo en dos pasos: primero encontrar qué EstudianteIDs aparecen en Inscripcion con CursoID 2, y luego obtener los nombres de esos estudiantes. Con subconsulta se hace en una sola sentencia:

```sql
SELECT Nombre
FROM Estudiante
WHERE EstudianteID IN (
    SELECT EstudianteID
    FROM Inscripcion
    WHERE CursoID = 2
);
```

*Explicación:* La subconsulta interna `SELECT EstudianteID FROM Inscripcion WHERE CursoID = 2` obtiene el conjunto de IDs de estudiantes que tienen una inscripción en el curso 2. Ese resultado alimenta a la consulta externa, que básicamente se vuelve `WHERE EstudianteID IN (<lista_de_ids>)`. Así, el SELECT externo devuelve los nombres de los estudiantes cuyo ID está en esa lista. Si  por ejemplo los estudiantes 1, 3 y 5 están en el curso 2, la subconsulta devuelve {1, 3, 5} y el SELECT externo listará los nombres de EstudianteID 1, 3 y 5.

**Ejemplo 2:** Subconsulta para obtener un valor escalar. Imaginemos que queremos listar los cursos (CursoID y NombreCurso) que tienen una cantidad de créditos **por encima del promedio** de todos los cursos. Primero necesitamos calcular el promedio de créditos de todos los cursos, luego filtrar aquellos cuyo crédito sea mayor que ese promedio:

```sql
SELECT CursoID, NombreCurso, Creditos
FROM Curso
WHERE Creditos > (
    SELECT AVG(Creditos)
    FROM Curso
);
```

Aquí la subconsulta `(SELECT AVG(Creditos) FROM Curso)` devuelve un solo valor (el promedio general de créditos). Supongamos que el promedio es 3.5; la consulta externa se vuelve `WHERE Creditos > 3.5`, con lo cual listará solo los cursos con créditos mayor a 3.5. Esto muestra cómo integrar una función de agregación global dentro de un filtro.

**Ejemplo 3:** Subconsulta correlacionada (un poco más avanzada): A veces la subconsulta se refiere a la fila actual de la consulta externa. Un ejemplo: listar estudiantes y la cantidad de inscripciones que cada uno tiene. Podemos hacer un SELECT de Estudiante, y en la misma lista de columnas incluir una subconsulta que cuente en Inscripcion cuántas inscripciones tiene ese estudiante:

```sql
SELECT 
    E.Nombre, 
    (SELECT COUNT(*) 
     FROM Inscripcion I 
     WHERE I.EstudianteID = E.EstudianteID
    ) AS NumInscripciones
FROM Estudiante E;
```

Aquí la subconsulta interna cuenta las filas en Inscripcion para un estudiante en particular, referenciado por `I.EstudianteID = E.EstudianteID`. Esa referencia de la tabla externa dentro de la subconsulta la hace *correlacionada*, es decir, la subconsulta se evalúa para cada fila de Estudiante E. El resultado sería una lista de cada estudiante con el número de cursos en que está inscrito. Por ejemplo:

```
Nombre       | NumInscripciones
------------ | ----------------
Ana Gomez    | 3
Luis Perez   | 1
...etc.
```

Las subconsultas correlacionadas pueden ser menos eficientes en ciertos casos, pero son muy expresivas para escribir consultas de forma declarativa.

**Ejercicios sugeridos:**

1. Escribe una consulta para encontrar los **estudiantes que no tienen inscripciones** en la tabla Inscripcion. *(Pista: Puedes usar una subconsulta en la cláusula WHERE con NOT IN, buscando estudiantes cuyo ID no esté en la lista de EstudianteID de Inscripcion.)*
2. Usando subconsulta, encuentra el **nombre del curso** en el que esté matriculado el estudiante con Nombre "Carlos Perez". *(Pista: primero obtén el ID de "Carlos Perez" de Estudiante en una subconsulta, luego busca en Inscripcion los CursoID para ese estudiante, y finalmente obtén los nombres de Curso con esos IDs. Puedes anidar subconsultas o usar IN varias veces.)*
3. Encuentra los **cursos** (CursoID) que tienen un número de inscripciones superior al número promedio de inscripciones de todos los cursos. Este es un reto interesante que combina agregación y subconsulta: primero calcula el promedio de inscripciones por curso (puede ser un subquery que cuente inscripciones agrupando por CursoID, aunque SQLite requeriría una subconsulta dentro de FROM para eso, un poco complejo; como simplificación, podrías calcular el total de inscripciones dividido entre número de cursos).
4. Utilizando una subconsulta escalar, obten el **curso con mayor cantidad de créditos** mostrando su NombreCurso y Creditos. (Pista: una forma es encontrar primero el valor máximo de créditos con una subconsulta `SELECT MAX(Creditos) FROM Curso` y luego usar ese valor para filtrar el curso con ese número de créditos.)
5. Reflexiona: ¿En qué casos preferirías usar una subconsulta versus buscar otra solución (como una combinación de tablas con JOIN, que aún no hemos detallado)? Piensa en legibilidad y en si la subconsulta devuelve un valor único o un conjunto.

## Valores nulos vs valores "sin valor"

Al trabajar con bases de datos, es fundamental comprender la diferencia entre un **valor NULL** y otros valores "vacíos" o por defecto, ya que afectan el comportamiento de las consultas y la integridad de los datos.

* **NULL** en SQL representa la **ausencia de valor**. Significa que en ese campo no se ha especificado ningún dato, es *desconocido* o *no aplicable*. Un campo NULL no es igual a cero, ni a cadena vacía, ni a un espacio en blanco — simplemente es *nada*. Por ejemplo, si en la tabla Estudiante la columna Teléfono puede ser NULL, un estudiante con Teléfono NULL significa que su número es desconocido o no registrado.
* Un **valor vacío** o *por defecto* depende del tipo de dato: puede ser una cadena vacía `''` (cero caracteres) para texto, o 0 para un número. Estos *sí* son valores concretos (el string vacío es un valor, el número 0 es un valor) y **no** se consideran NULL. Por ejemplo, en la columna Ciudad, podríamos poner `''` (vacío) para un estudiante si queremos indicar explícitamente que no proporcionó su ciudad. Pero eso no es NULL, es un dato que dice "no hay texto". Otro ejemplo: en un campo numérico, 0 podría ser un valor válido (por ejemplo, nota = 0), distinto de NULL que indicaría que la nota no se ha asignado aún.

**Comparaciones y comportamiento:**

* Un valor NULL no se compara igual que otro NULL usando `=`. De hecho, cualquier comparación que involucre NULL generalmente resulta **UNKNOWN** (que en filtrado se trata como FALSE). Por ejemplo, la expresión `NULL = NULL` no es verdadera, es desconocida, porque por definición no se puede afirmar que "nada" sea igual a "nada" (son valores desconocidos). Por eso, en SQL no se usa `=` para verificar NULL, sino los operadores especiales `IS NULL` o `IS NOT NULL`.

  Ejemplo: Para encontrar estudiantes sin ciudad registrada (Ciudad es NULL):

  ```sql
  SELECT Nombre
  FROM Estudiante
  WHERE Ciudad IS NULL;
  ```

  Esto listará los estudiantes cuyo campo Ciudad es NULL. En cambio, `WHERE Ciudad = NULL` no funciona como esperas.

* Para cadenas vacías, sí se usa `=`. Por ejemplo, si quisiéramos encontrar estudiantes con cadena vacía en nombre (quizá un dato mal ingresado):

  ```sql
  SELECT Nombre, Edad
  FROM Estudiante
  WHERE Nombre = '';
  ```

  Esto buscaría registros donde Nombre es exactamente una cadena vacía. De nuevo, **no es lo mismo** que NULL. En SQLite, por cierto, una cadena vacía `''` no se convierte a NULL automáticamente ni nada por el estilo; permanece como cadena de longitud 0.

* Las funciones de agregación (como vimos) ignoran NULL. Si tenemos valores NULL en una columna numérica, `SUM(col)` sumará solo los que no son nulos. `COUNT(col)` contará solo las filas donde col no es nulo (mientras que COUNT(\*) cuenta todas las filas). Esto puede llevar a confusiones: por ejemplo, si quieres contar cuántos estudiantes tienen teléfono registrado podrías usar `COUNT(Telefono)` y esto ignorará los NULL (dándote precisamente los que sí tienen), mientras `COUNT(*)` te da todos.

* Al insertar datos, si una columna no se especifica y no tiene valor por defecto, suele quedar en NULL automáticamente (dependiendo de la configuración de la tabla).

**Ejemplo de diferencia practical:**

Imagina una tabla simple de Usuarios con columnas: UsuarioID, Nombre, Email. Si un usuario no proporciona email:

* Podríamos guardar Email = NULL (significa "no tenemos ese dato").
* O podríamos guardar Email = '' (cadena vacía, significa "dijo que no tiene email" o decidimos ponerlo vacío).

Si hacemos una consulta:

```sql
SELECT * FROM Usuario WHERE Email = '';
```

obtendrás todos los usuarios cuyo email es cadena vacía, pero no incluirá aquellos cuyo email es NULL. Y

```sql
SELECT * FROM Usuario WHERE Email IS NULL;
```

traerá los usuarios sin email (NULL) pero no los vacíos.

Ambos representan falta de un email real, pero a nivel de base de datos son diferentes. En general se recomienda usar NULL para "dato desconocido/no proporcionado", y reservar el vacío/0 para casos en que realmente semánticamente aplique (por ejemplo, una nota de 0 es una nota real, no es ausencia de nota).

**Resumen:**

* *NULL = ausencia de valor.* No es igual a nada, ni siquiera a otro NULL. Usa `IS NULL` para comprobar.
* *Vacío / 0 = valores concretos.* Representan "sin contenido" pero siguen siendo datos. Usa las comparaciones normales (`= ''`, `= 0`) para buscarlos.
* Ten cuidado al usar condiciones lógicas: `WHERE NOT (Ciudad = 'Bogota')` **no** devolverá registros donde Ciudad es NULL, porque `Ciudad = 'Bogota'` sería UNKNOWN allí y NOT UNKNOWN sigue siendo UNKNOWN (filtrado fuera). Si quisieras incluir tanto "no es Bogotá" como también los NULL, tendrías que hacerlo explícito: `WHERE Ciudad <> 'Bogota' OR Ciudad IS NULL`.

**Ejercicios sugeridos:**

1. Crea en SQLite una tabla simple de ejemplo con una columna que pueda ser NULL. Inserta un par de filas donde en una de ellas ese valor sea NULL y en otra sea un valor "vacío" (ej. cadena vacía o 0 según el tipo). Luego intenta escribir una consulta para seleccionar la fila con NULL usando `=` y otra usando `IS NULL`. ¿Qué observas en los resultados?
2. En la tabla Estudiante, supongamos que la columna Edad puede ser NULL si no se registra. Escribe una consulta para obtener los estudiantes **sin edad registrada**. (Debería usar `IS NULL`).
3. En la tabla Estudiante, supongamos que decidimos almacenar en Ciudad la cadena vacía `''` para estudiantes cuyo origen no se conoce. Escribe una consulta para contar cuántos estudiantes tienen Ciudad vacía. (Usa `WHERE Ciudad = ''` con COUNT).
4. ¿Qué resultado esperas de la consulta `SELECT COUNT(Ciudad) FROM Estudiante;` si algunos estudiantes tienen Ciudad NULL? ¿Contará esas filas o no? Veríficalo conceptualmente o con una prueba en SQLite.
5. Explica con tus palabras por qué es importante distinguir entre NULL y un valor como 0 o '' en una base de datos. ¿Qué problemas podrían surgir si no se tiene en cuenta la diferencia?

## Resumen y Conclusiones

En estas notas didácticas hemos cubierto los fundamentos del manejo de bases de datos relacionales usando SQL, específicamente con ejemplos en SQLite. A modo de recapitulación, los **puntos clave** y objetivos logrados son:

* **SQL como lenguaje**: Entendimos que SQL (Lenguaje de Consulta Estructurado) es la forma estándar de interactuar con bases de datos relacionales. Permite definir la estructura de los datos y realizar operaciones de inserción, consulta, actualización y eliminación de información de manera declarativa.
* **Modelado de datos (Entidad-Relación)**: Aprendimos a identificar entidades, atributos y relaciones en un dominio dado, usando el modelo entidad-relación para planificar la estructura de la base de datos. Esto sienta las bases para crear tablas bien diseñadas, con llaves primarias y foráneas apropiadas.
* **Llaves primaria y foránea**: Vimos cómo las llaves primarias garantizan unicidad de registros, y las llaves foráneas mantienen la integridad referencial entre tablas. Implementamos estos conceptos en SQLite mediante las sentencias `CREATE TABLE` con las cláusulas PRIMARY KEY y FOREIGN KEY.
* **Consultas básicas (CRUD)**: Practicamos las sentencias fundamentales:

  * `SELECT` para obtener datos.
  * `INSERT` para agregar nuevos registros.
  * `UPDATE` para modificar registros existentes.
  * `DELETE` para eliminar registros.
    A través de ejemplos comprendimos la sintaxis y precauciones (como usar WHERE para no afectar filas indeseadas).
* **Filtrado de datos**: Usando `WHERE` junto con operadores relacionales (`=, <, >, <>`, etc.) y lógicos (`AND, OR, NOT`), filtramos consultas para responder preguntas específicas (ej. estudiantes de cierta ciudad y edad). Aprendimos a construir condiciones compuestas y la importancia de la precedencia de operadores lógicos.
* **Funciones de agregación**: Exploramos cómo obtener información resumida de nuestros datos mediante `COUNT`, `SUM`, `AVG`, `MIN`, `MAX`. Por ejemplo, contar registros, sumar valores, calcular promedios. Entendimos que estas funciones operan sobre conjuntos de filas y devuelven un valor agregado, ignorando NULL en muchos casos.
* **Agrupamiento (GROUP BY) y HAVING**: Vimos cómo `GROUP BY` nos permite aplicar agregaciones por categorías (grupos) en lugar de toda la tabla, por ejemplo agrupando por ciudad o por curso. Luego utilizamos `HAVING` para filtrar esos grupos agregados, pudiendo imponer condiciones sobre los resultados de las funciones de agregación (ej. sólo mostrar grupos con cierto mínimo de elementos).
* **Subconsultas**: Aprendimos a anidar consultas dentro de otras para lograr resultados más complejos, ya sea listas de valores para usar con IN, o valores escalares para comparaciones, e incluso subconsultas correlacionadas que se evalúan fila por fila. Esto amplía notablemente el poder expresivo de SQL, permitiendo consultas de múltiples pasos lógicos en una sola sentencia.
* **NULL vs valores vacíos**: Finalmente, diferenciamos el concepto de *NULL* (ausencia de dato) de un valor vacío o cero. Comprendimos cómo cada uno se comporta en comparaciones y en funciones (por ejemplo, COUNT(\*) vs COUNT(col)) y por qué es crucial manejar correctamente los NULL en nuestras consultas para evitar resultados inesperados.

Con esta base, deberías estar en capacidad de **crear esquemas simples de base de datos** en SQLite, poblar datos de ejemplo y ejecutar consultas que resuelvan preguntas sobre esos datos. Has visto ejemplos prácticos y has tenido la oportunidad de realizar ejercicios para afianzar cada concepto.

**¿Qué sigue?** A medida que avances, encontrarás temas más avanzados como *joins* (para combinar resultados de múltiples tablas de forma declarativa), *views* (vistas), *procedimientos almacenados*, optimización de consultas, entre otros. Pero con lo aprendido aquí, ya cuentas con las herramientas esenciales para comenzar a trabajar con bases de datos relacionales y el lenguaje SQL.
�
