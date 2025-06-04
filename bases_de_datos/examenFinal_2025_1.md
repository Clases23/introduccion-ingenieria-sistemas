
# Examen Final Práctico: SQL (SQLite)

La siguiente evaluación práctica cubre los temas de SQL vistos en el curso, utilizando el motor de base de datos **SQLite**. Se presenta una base de datos de ejemplo correspondiente a una tienda de tecnología, con dos tablas: `fabricante` (catálogo de fabricantes) y `producto` (lista de productos ofrecidos, cada uno asociado a un fabricante). El examen consta de **10 ejercicios prácticos** de consulta y manipulación de datos.

**Formato:** Trabajo individual con una semana de plazo para su realización, seguido de una sustentación oral de las soluciones. Se debe garantizar que las consultas funcionen en SQLite y se ajusten a los contenidos vistos en clase. A continuación se muestran las definiciones de las tablas de la base de datos con datos iniciales, seguidas por los ejercicios a resolver.

**Intrucciones:**
 - No se conocen de antemano los valores numéricos de id en ninguna tabla. Para filtrar por fabricante, debe usarse una subconsulta simple que busque el id en la tabla fabricante usando la columna nombre. Jamás referencie directamente un número de id en su WHERE.
 - Se debe de entregar un documento **PFD** y solo ese formato, en el cual incluyan para cada pregunta, la pregunta, la sentencia que uso, escrita no un pantallazo, y el resultado, este último si puede ser un pantallazo.
 - El **NO** seguimiento de las instrucciones también se sancionará.
 - El Archivo debe de ser llamado así **"nombre_apellido_examen_bd_2025_1.pdf"**  
  Ejemplo: Si usted se llama Jose Repelin el archivo debe ser nombrado así:  
  **"jose_repelin_examen_bd_2025_1.pdf"**

## Base de Datos: Tablas y Datos Iniciales

```sql

-- Inserta todos los fabricantes
INSERT INTO fabricante (id, nombre) VALUES
  (1, 'Asus'),
  (2, 'Lenovo'),
  (3, 'Hewlett-Packard'),
  (4, 'Samsung'),
  (5, 'Seagate'),
  (6, 'Crucial'),
  (7, 'Gigabyte'),
  (8, 'Huawei'),
  (9, 'Xiaomi');

-- Inserta todos los productos, indicando fabricante_id
INSERT INTO producto (id, nombre, precio, fabricante_id) VALUES
  (1,  'Disco duro SATA3 1TB',         86.99,   5),  -- Seagate
  (2,  'Memoria RAM DDR4 8GB',         120.00,  6),  -- Crucial
  (3,  'Disco SSD 1 TB',              150.99,  5),  -- Seagate
  (4,  'GeForce GTX 1050Ti',          185.00,  7),  -- Gigabyte
  (5,  'GeForce GTX 1080 Xtreme',     755.00,  7),  -- Gigabyte
  (6,  'Monitor 24 LED Full HD',      202.00,  4),  -- Samsung
  (7,  'Monitor 27 LED Full HD',      245.99,  4),  -- Samsung
  (8,  'Portátil Yoga 520',           559.00,  2),  -- Lenovo
  (9,  'Portátil Ideapad 320',        444.00,  2),  -- Lenovo
  (10, 'Impresora HP Deskjet 3720',    59.99,   3),  -- Hewlett-Packard
  (11, 'Impresora HP Laserjet Pro M26nw', 180.00,   3);-- Hewlett-Packard


```


## Preguntas de Desarrollo
1. Crea las tablas necesarias con los atributos correctos.
   
2. Devuelve todos los productos del fabricante **`Lenovo`**.

3. Devuelve todos los productos que tienen un precio mayor o igual al precio del producto más caro del fabricante **`Lenovo`**, ordenados de mayor a menor precio.

4. Lista el nombre del producto más caro del fabricante **`Lenovo`**.

5. Lista todos los productos del fabricante **`Asus`** que tienen un precio superior al precio promedio de todos sus productos.

6. Calcula el número total de productos que tiene el fabricante **`Asus`**.

7. Muestra el **precio máximo**, **precio mínimo**, **precio promedio** y el **número total de productos** del fabricante **`Crucial`**.

8. Devuelve los nombres de los fabricantes que **no tienen ningún producto** asociado, mostrando dichos nombres en mayúsculas.

9.  Inserta un nuevo fabricante en la tabla `fabricante` con el nombre **“Western Digital”**.

10. Aumenta en un **10%** el precio de todos los productos del fabricante **`Samsung`**.

11. Elimina de la base de datos todos los productos del fabricante **`Seagate`**.

## Rúbrica de Evaluación

* **Corrección Sintáctica:** Sentencias SQL bien formadas y sin errores de sintaxis. Uso correcto de la sintaxis SQLite (cláusulas en orden, puntos y comas, comillas, etc.).
* **Lógica de la Consulta/Operación:** Cada solución produce el **resultado correcto** según lo solicitado. Las condiciones WHERE y las subconsultas filtran los datos apropiados, y las operaciones de inserción/actualización/eliminación modifican los datos deseados sin afectar otros registros.
* **Uso de Funciones y Operadores:** Empleo adecuado de **funciones SQL** (por ejemplo, `MAX`, `MIN`, `AVG`, etc.) y operadores aritméticos o lógicos. Se evalúa que el estudiante utilice las funciones necesarias para obtener resultados (p. ej., calcular promedios, porcentajes) y lo haga de forma correcta.
* **Buenas Prácticas SQL:** Código organizado y legible. Uso de mayúsculas para palabras clave y formato indentado cuando aplique. Empleo de **alias descriptivos** para columnas o tablas cuando ayude a la comprensión. Se valorará igualmente evitar el uso de `SELECT *` (a menos que se soliciten todas las columnas) y **seguir las instrucciones**.
