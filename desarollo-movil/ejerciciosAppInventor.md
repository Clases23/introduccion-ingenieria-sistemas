
---

# **📌 Ejercicios de Programación con App Inventor**  

Estos ejercicios están diseñados para reforzar el uso de **condicionales, generación de números aleatorios y manipulación de datos en App Inventor**.  

## **📌 Tabla de Contenidos**  

- [1️⃣ Generador de Números Aleatorios con Puntuación](#1️⃣-generador-de-números-aleatorios-con-puntuación)  
- [2️⃣ Contador de Números en un Rango](#2️⃣-contador-de-números-en-un-rango)  
- [3️⃣ Identificación de Números Primos y Múltiplos en un Rango](#3️⃣-identificación-de-números-primos-y-múltiplos-en-un-rango)  
- [4️⃣ Suma de Números con Restricciones](#4️⃣-suma-de-números-con-restricciones)  

---

## **1️⃣ Generador de Números Aleatorios con Puntuación**  

### **📌 Descripción del Problema**  
Se debe desarrollar una aplicación en **App Inventor** que genere **números aleatorios de tres cifras** al presionar un botón. Dependiendo del valor del número generado, se asignarán puntos según las siguientes reglas:  

- Si el número es **mayor que 900**, se suma **1 punto**.  
- Si el número está **entre 400 y 500** (incluyéndolos), se suman **3 puntos**.  
- Si el número es **par**, se suma **1 punto**.  
- La aplicación debe **detenerse automáticamente** cuando el usuario alcance **20 puntos**, mostrando un mensaje de victoria e impidiendo que el botón siga funcionando.  

### **📌 Requisitos Técnicos**  
✅ Uso de **números aleatorios** para generar valores entre 100 y 999.  
✅ Implementación de **condicionales** para verificar y asignar puntos.  
✅ Control de **estado del juego** para desactivar el botón cuando se alcancen 20 puntos.  
✅ Uso de **etiquetas** para mostrar el puntaje y el número generado.  

### **📌 Flujo de la Aplicación**  
1. El usuario presiona el botón **"Generar Número"**.  
2. Se genera un número aleatorio de **tres cifras**.  
3. Se evalúan las reglas de puntuación y se actualiza el marcador.  
4. Cuando el usuario alcanza **20 puntos**, la aplicación muestra `"¡Has ganado!"` y desactiva el botón.  

---

## **2️⃣ Contador de Números en un Rango**  

### **📌 Descripción del Problema**  
Se debe desarrollar una aplicación que permita al usuario ingresar **dos números**:  
- **Límite Inferior**  
- **Límite Superior**  

📌 **La aplicación debe verificar que los límites sean correctos**, es decir, que el **límite superior sea mayor** que el inferior.  

📌 **Una vez validados los datos, la aplicación debe mostrar:**  
- **Todos los números pares** dentro del rango.  
- **Todos los números impares** dentro del rango.  
- **Todos los números dentro del rango que terminen en 3 o en 7**.  

### **📌 Requisitos Técnicos**  
✅ Uso de **entradas numéricas** para definir los límites.  
✅ Implementación de **condicionales** para validar los límites y clasificar los números.  
✅ Uso de **listas o etiquetas dinámicas** para mostrar los números pares, impares y los que terminan en 3 o 7.  

### **📌 Flujo de la Aplicación**  
1. El usuario **ingresa el límite inferior y el límite superior** en los cuadros de texto.  
2. Presiona el botón **"Calcular"**.  
3. Se valida que **el límite superior sea mayor** que el límite inferior.  
4. La aplicación muestra los números que cumplen las condiciones.  

---

## **3️⃣ Identificación de Números Primos y Múltiplos en un Rango**  

### **📌 Descripción del Problema**  
El usuario ingresará **dos números** que representarán un **límite inferior y un límite superior**.  
La aplicación deberá:  
✅ **Verificar que los límites sean correctos** (el límite superior debe ser mayor que el inferior).  
✅ **Mostrar todos los números primos dentro del rango.**  
✅ **Mostrar todos los múltiplos de 3 o de 5 dentro del rango.**  

### **📌 Requisitos Técnicos**  
✅ **Entrada de datos validada**: Límite inferior y superior deben ser correctos.  
✅ **Uso de condicionales**: Para determinar qué números son primos y cuáles son múltiplos de 3 o 5.  
✅ **Ciclo de iteración**: Para recorrer todos los números dentro del rango.  

### **📌 Flujo de la Aplicación**  
1. El usuario **ingresa el límite inferior y el límite superior**.  
2. La aplicación **valida que el límite superior sea mayor** que el límite inferior.  
3. Se **recorren los números en el rango** y se identifican:  
   - **Números primos** (solo divisibles entre 1 y ellos mismos).  
   - **Números múltiplos de 3 o 5**.  
4. La aplicación muestra los resultados en **listas separadas**.  

---

## **4️⃣ Suma de Números con Restricciones**  

### **📌 Descripción del Problema**  
El usuario ingresará **dos números**:  
- **Un límite inferior.**  
- **Un límite superior.**  

📌 **La aplicación deberá calcular la suma de ciertos números dentro del rango, con reglas específicas:**  
✅ **Suma de todos los números impares.**  
✅ **Suma de todos los números que no sean múltiplos de 4.**  

### **📌 Requisitos Técnicos**  
✅ **Validación de límites**: El límite superior debe ser mayor que el inferior.  
✅ **Uso de condicionales**: Para verificar números impares y que no sean múltiplos de 4.  
✅ **Uso de variables acumuladoras**: Para ir sumando los valores.  

### **📌 Flujo de la Aplicación**  
1. El usuario **ingresa el límite inferior y el límite superior**.  
2. Se valida que **el límite superior sea mayor**.  
3. Se recorren los números dentro del rango y se calcula:  
   - La **suma de los impares**.  
   - La **suma de los que no sean múltiplos de 4**.  
4. La aplicación muestra los **resultados finales**.  

---

## 📌 **Consideraciones Generales**  
- Se pueden agregar **mensajes de error** si los límites no son correctos.  
- Se pueden utilizar **diferentes colores o estilos visuales** para diferenciar los resultados.  
- **Bonus:** Agregar **opciones interactivas**, como mostrar los números sumados en una lista antes de mostrar el resultado final.  

---
