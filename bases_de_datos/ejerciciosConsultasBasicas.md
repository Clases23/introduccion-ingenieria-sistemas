


# Ejercicios SQL en SQLite

## Ejercicio 1: Películas

```sql
CREATE TABLE peliculas (
  id       INTEGER PRIMARY KEY,
  titulo   TEXT    NOT NULL,
  genero   TEXT    NOT NULL,
  duracion INTEGER NOT NULL,    -- duración en minutos
  rating   REAL    NOT NULL     -- calificación de 0.0 a 10.0
);

INSERT INTO peliculas (titulo, genero, duracion, rating) VALUES
  ('La Gran Aventura',   'Acción',   140, 8.1),
  ('Romance de Otoño',   'Drama',     95, 7.4),
  ('Risas y Conflictos', 'Comedia',  110, 6.8),
  ('Guerra Eterna',      'Acción',   155, 7.9),
  ('Misterio Nocturno',  'Suspenso', 125, 8.5),
  ('Comedia Ligera',     'Comedia',   85, 7.0),
  ('Drama Familiar',     'Drama',    105, 8.2);
````

1. Muestra el **título** y **género** de las películas de género **‘Acción’** que tengan **rating ≥ 8.0** y **duración < 150** minutos.
2. Selecciona las películas de **comedia** con **rating ≥ 7.0**.
3. Obtén el **título** y la **duración** de las películas cuya duracion esté **entre 90 y 120 minutos**.
4. Lista los **títulos** de las películas con **rating > 8.0**.
5. Cuenta cuántas películas hay **por género**.
6. Calcula el **promedio de rating** por género.
7. Muestra las películas que sean **muy cortas** (duración < 90) o **muy largas** (duración > 140).

---

## Ejercicio 2: Clientes

```sql
CREATE TABLE clientes (
  id     INTEGER PRIMARY KEY,
  nombre TEXT    NOT NULL,
  pais   TEXT    NOT NULL,
  saldo  REAL    NOT NULL
);

INSERT INTO clientes (nombre, pais, saldo) VALUES
  ('María López',    'España',      1200.50),
  ('Thomas Müller',  'Alemania',     850.00),
  ('Alice Dupont',   'Francia',     1500.75),
  ('Kenji Sato',     'Japón',       1100.00),
  ('Liu Wei',        'China',        950.25),
  ('John Smith',     'Reino Unido', 1300.00),
  ('Carlos Silva',   'Brasil',       700.00),
  ('Sara Svensson',  'Suecia',      1400.30);
```


1. Obtén el **nombre** y el **saldo** de los clientes cuyo **país** sea **‘España’**, **‘Francia’** o **‘Alemania’**.
2. Selecciona los clientes con **saldo > 1000**.
3. Muestra los clientes cuyo **saldo** esté **entre 900 y 1400**.
4. Cuenta cuántos clientes hay **por país**.
5. Calcula el **saldo promedio** por país.
6. Lista los clientes que **no** sean de **España**, **Francia** ni **Alemania**.

---

## Ejercicio 3: Transacciones

```sql
CREATE TABLE transacciones (
  id     INTEGER PRIMARY KEY,
  tipo   TEXT    NOT NULL,  -- e.g. 'venta', 'compra', 'devolución'
  monto  REAL    NOT NULL
);

INSERT INTO transacciones (tipo, monto) VALUES
  ('venta',       1500.00),
  ('compra',       800.00),
  ('venta',       2200.50),
  ('devolución',   300.00),
  ('venta',       1800.75),
  ('compra',      1200.00),
  ('devolución',   450.25),
  ('venta',        900.00);
```

1. Para cada **tipo** de transacción, calcula el **número total de transacciones** y la **suma de montos**, pero **solo** muestra aquellos tipos cuya **suma total de montos > 3000**.
2. Cuenta cuántas transacciones hay del tipo **‘venta’**.
3. Muestra el **conteo** y la **suma de montos** por cada **tipo** de transacción.
4. Calcula el **promedio de monto** por tipo.
5. Obtén el **máximo** y el **mínimo** monto por tipo.
6. Lista los tipos de transacción con **suma de montos > 3000**.
7. Selecciona todas las transacciones con **monto ≥ 1000**.

---

## Ejercicio 4: Inventario

```sql
CREATE TABLE inventario (
  id       INTEGER PRIMARY KEY,
  producto TEXT    NOT NULL,
  stock    INTEGER NOT NULL
);

INSERT INTO inventario (producto, stock) VALUES
  ('Teclado',     25),
  ('Monitor',     10),
  ('Ratón',       40),
  ('Auriculares', 18),
  ('Webcam',       5);
```


1. Modifica la tabla **inventario** para **agregar** una columna **ubicacion** de tipo **TEXT**, con valor por defecto **'Almacén Central'**.
2. Muestra **todo** el inventario.
3. Obtén los productos con **stock < 20**.
4. Lista los productos cuya **ubicación** sea **'Almacén Central'**.
5. Cuenta el **total de productos** registrados.
6. Actualiza la **ubicación** de **'Webcam'** a **'Almacén Sur'**.
7. Agrega una columna **precio\_unitario** (REAL, default 0.0) al inventario.

