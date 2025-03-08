
---

# **Ejercicio 1: Juego de Preguntas y Respuestas con Ranking de Puntajes**
📌 **Descripción:**  
El usuario responde **5 preguntas** de opción múltiple con **3 respuestas posibles**.  
Cada respuesta correcta **suma 1 punto**. Hay un **temporizador de 10 segundos** por pregunta.  
Si el tiempo se acaba, se pasa a la siguiente sin puntuar.  

📌 **Requisitos:**  
✅ **Pantallas:**  
- **Inicio:** botón `"Iniciar Juego"`.  
- **Juego:**  
  - Pregunta actual.  
  - Tres botones de respuesta.  
  - Temporizador de 10 segundos.  
  - Puntaje actual y barra de progreso.  
- **Resultados:** muestra el puntaje obtenido y los **3 mejores puntajes de la sesión**.  

✅ **Lógica del Juego:**  
- Usar una **lista de preguntas y respuestas**.  
- Si el usuario acierta, sumar **1 punto** y cambiar el fondo a **verde**.  
- Si se equivoca, **no sumar puntos** y cambiar el fondo a **rojo**.  
- Si el tiempo llega a **0 segundos**, pasar automáticamente a la siguiente pregunta.  
- Comparar el puntaje con los **3 mejores puntajes obtenidos en la sesión**.  

📌 **Criterios de Evaluación:**  
✔️ Implementación del **temporizador de 10 segundos**.  
✔️ Comparación de puntajes sin almacenamiento persistente.  
✔️ Uso de listas y validación de respuestas.  

---

# **Ejercicio 2: Examen con Temporizador y Niveles de Dificultad**
📌 **Descripción:**  
El usuario responde **5 preguntas con imágenes**, con **tiempo limitado** según el nivel seleccionado:  
- **Fácil:** 15 segundos por pregunta.  
- **Medio:** 10 segundos por pregunta.  
- **Difícil:** 5 segundos por pregunta.  

Si el tiempo se acaba antes de responder, la respuesta se marca como incorrecta.  

📌 **Requisitos:**  
✅ **Pantallas:**  
- **Inicio:** selector de dificultad y botón `"Iniciar Examen"`.  
- **Juego:**  
  - Pregunta con **imagen asociada**.  
  - Tres botones de respuesta.  
  - Temporizador según dificultad.  
  - Puntaje actual.  
- **Resultados:** muestra el puntaje final y **el mejor puntaje de la sesión**.  

✅ **Lógica del Juego:**  
- Configurar el **temporizador según el nivel de dificultad**.  
- Si el usuario responde correctamente, sumar **1 punto** y cambiar el fondo a **verde**.  
- Si se equivoca o el tiempo se agota, **no sumar puntos** y cambiar el fondo a **rojo**.  
- Comparar el puntaje con el mejor puntaje obtenido en la sesión.  

📌 **Criterios de Evaluación:**  
✔️ Implementación de **tres niveles de dificultad**.  
✔️ Temporizador ajustable y funcional.  
✔️ Comparación del puntaje sin almacenamiento persistente.  

---

# **Ejercicio 3: Juego de Memoria con Tarjetas Ocultas**
📌 **Descripción:**  
El usuario debe encontrar **pares de imágenes iguales** en un tablero **antes de que el tiempo se acabe**.  
El número de tarjetas varía según el nivel de dificultad:  
- **Fácil:** 6 tarjetas (3 pares).  
- **Medio:** 12 tarjetas (6 pares).  
- **Difícil:** 18 tarjetas (9 pares).  

📌 **Requisitos:**  
✅ **Pantallas:**  
- **Inicio:** selector de dificultad y botón `"Iniciar Juego"`.  
- **Juego:**  
  - Tablero de tarjetas (imágenes).  
  - Temporizador ajustado según dificultad.  
  - Contador de intentos.  
- **Resultados:** muestra la cantidad de intentos y si ganó antes del tiempo límite.  

✅ **Lógica del Juego:**  
- Mostrar las tarjetas **boca abajo**.  
- Si se tocan **dos tarjetas**, verificar si son iguales:  
  - **Si son iguales**, dejarlas visibles y sumar un par encontrado.  
  - **Si no son iguales**, ocultarlas después de 1 segundo.  
- Contar la cantidad de intentos y mostrarla al final.  

📌 **Criterios de Evaluación:**  
✔️ Uso de listas para manejar las tarjetas y verificar coincidencias.  
✔️ Temporizador y validación de pares.  

---

# **Ejercicio 4: Juego de Reflejos con Toques Rápidos**
📌 **Descripción:**  
El usuario debe **tocar un botón que aparece en posiciones aleatorias** antes de que desaparezca.  
Se puede elegir entre:  
- **Modo Rápido:** dura 30 segundos.  
- **Modo Infinito:** sin límite de tiempo.  

📌 **Requisitos:**  
✅ **Pantallas:**  
- **Inicio:** selector de modo y botón `"Jugar"`.  
- **Juego:**  
  - Botón que cambia de posición aleatoriamente.  
  - Contador de puntos.  
  - Temporizador en **Modo Rápido**.  
- **Resultados:** muestra el puntaje final.  

✅ **Lógica del Juego:**  
- Si el usuario toca el botón, moverlo a una nueva posición aleatoria y aumentar la puntuación.  
- Si **no toca el botón en 2 segundos**, restar 1 punto.  
- En **Modo Rápido**, detener el juego después de 30 segundos.  

📌 **Criterios de Evaluación:**  
✔️ Movimiento aleatorio correcto del botón.  
✔️ Implementación de los **dos modos de juego**.  

---

# **Ejercicio 5: Simulador de Tienda - Registro de Compras y Total**
📌 **Descripción:**  
El usuario **selecciona productos**, los **agrega al carrito**, y puede **confirmar la compra**.  

📌 **Requisitos:**  
✅ **Pantallas:**  
- **Inicio:** lista de productos con nombre, imagen y precio, botón `"Comprar"`.  
- **Juego:**  
  - Lista de productos con botones para agregar al carrito.  
  - Etiqueta con el total de la compra.  
  - Botón `"Pagar"` para confirmar la compra.  
- **Resultados:** muestra el total de productos comprados y el **monto final**.  

✅ **Lógica del Juego:**  
- Usar una **lista de productos con nombre, precio e imagen**.  
- Permitir **agregar productos al carrito** y calcular el total.  
- Mostrar el total en tiempo real y actualizar la lista de compras.  

📌 **Criterios de Evaluación:**  
✔️ Uso de listas y variables para gestionar productos y el total.  
✔️ Implementación del carrito de compras con total en tiempo real.  

---

# **Ejercicio 6: Simulador de Semáforo con Flujo de Tráfico**
📌 **Descripción:**  
El semáforo cambia automáticamente, pero **ajusta la duración de la luz verde según la cantidad de autos en espera**.  
Los autos **llegan aleatoriamente** y desaparecen cuando avanzan.  

📌 **Requisitos:**  
✅ **Pantallas:**  
- **Inicio:** botón `"Iniciar Simulación"`.  
- **Juego:**  
  - Semáforo con luces que cambian automáticamente.  
  - Etiqueta con el número de autos en espera.  
  - Animación que muestra autos moviéndose.  

✅ **Lógica del Juego:**  
- Cada **5 segundos**, puede llegar 1 auto al semáforo.  
- Si hay **más de 5 autos**, la luz verde dura **más tiempo**.  
- Si hay **menos de 3 autos**, la luz verde dura **menos tiempo**.  
- Cuando la luz verde está encendida, los autos avanzan y desaparecen.  

📌 **Criterios de Evaluación:**  
✔️ Ajuste dinámico del semáforo según autos en espera.  
✔️ Simulación del tráfico con autos llegando y avanzando.  

---
