# 📊 EJERCICIOS - ARREGLOS DE OBJETOS Y MATRICES

## Nivel Progresivo: De Básico a Avanzado

**Nombre:** **********\_\_********** **Fecha:** **********\_\_**********

**Instrucciones:**

- Resuelve cada ejercicio en orden
- Los ejercicios 1-10 son sobre arreglos de objetos
- Los ejercicios 11-20 son sobre matrices (arreglos bidimensionales)
- Escribe el código completo y legible

---

# PARTE A: ARREGLOS DE OBJETOS (Ejercicios 1-10)

## Ejercicio 1: Crear Vector de Objetos Vacío

Crea un vector llamado `alumnos` de tamaño 15 para almacenar objetos de tipo `Alumno`. Inicializa un contador `cont` en 0.

Asume que existe una clase `Alumno` con atributos: nombre, matricula, calificacion.

```python
# Escribe tu código aquí:







```

---

## Ejercicio 2: Llenar Vector con Objetos

Dado el vector del ejercicio anterior, escribe un código que:

1. Pregunte al usuario cuántos alumnos desea agregar (máximo 15)
2. Use un bucle `for` para pedir los datos de cada alumno
3. Cree cada objeto `Alumno` y agréguelo al vector
4. Actualice el contador

```python
# Escribe tu código aquí:





















```

---

## Ejercicio 3: Recorrer y Mostrar Todos los Objetos

Escribe código para recorrer el vector `alumnos` y mostrar los datos de cada alumno usando su método `mostrar()`.

```python
# Escribe tu código aquí:









```

---

## Ejercicio 4: Buscar y Contar

Dado un vector de productos con atributos: nombre, precio, categoria.

Escribe código que:

1. Pida al usuario una categoría
2. Recorra el vector y cuente cuántos productos pertenecen a esa categoría
3. Muestre el total

Asume: vector `productos[]`, contador `cont`, clase `Producto`.

```python
# Escribe tu código aquí:



















```

---

## Ejercicio 5: Calcular Promedio de Atributos

Dado un vector de empleados con atributos: nombre, departamento, salario.

Escribe código que:

1. Recorra todos los empleados
2. Sume todos los salarios
3. Calcule y muestre el promedio

Asume: vector `empleados[]`, contador `cont`, clase `Empleado`.

```python
# Escribe tu código aquí:

















```

---

## Ejercicio 6: Encontrar el Máximo

Dado el mismo vector de empleados del ejercicio anterior, escribe código que:

1. Encuentre al empleado con el salario más alto
2. Muestre su nombre y salario

```python
# Escribe tu código aquí:



















```

---

## Ejercicio 7: Ordenamiento de Burbuja Básico

Dado un vector de estudiantes con atributo `calificacion`, escribe el algoritmo de ordenamiento de burbuja para ordenar el vector de mayor a menor calificación.

Asume: vector `estudiantes[]`, contador `cont`.

```python
# Escribe tu código aquí:


























```

---

## Ejercicio 8: Filtrar y Crear Nuevo Vector

Dado un vector de productos, crea un NUEVO vector que contenga solo los productos cuyo precio sea mayor a 1000.

Escribe el código completo que:

1. Cree un nuevo vector `productos_caros`
2. Recorra el vector original
3. Copie los productos que cumplan la condición
4. Muestre cuántos productos se copiaron

Asume: vector `productos[]` con `cont`, clase `Producto` con atributo `precio`.

```python
# Escribe tu código aquí:


























```

---

## Ejercicio 9: Eliminar Duplicados por Atributo

Dado un vector de contactos con atributo `telefono`, escribe código que:

1. Recorra el vector
2. Para cada contacto, verifique si ya existe otro con el mismo teléfono
3. Si encuentra duplicado, elimínelo lógicamente (marcando nombre = " ")
4. Muestre cuántos duplicados se eliminaron

Asume: vector `contactos[]`, contador `cont`, clase `Contacto`.

```python
# Escribe tu código aquí:

































```

---

## Ejercicio 10: Agrupar y Contar por Categoría

Dado un vector de libros con atributo `genero` (puede ser: "Ficción", "Ciencia", "Historia"), escribe código que:

1. Cuente cuántos libros hay de cada género
2. Muestre el resumen:
   ```
   Ficción: 5 libros
   Ciencia: 3 libros
   Historia: 2 libros
   ```

Asume: vector `libros[]`, contador `cont`, clase `Libro`.

```python
# Escribe tu código aquí:































```

---

# PARTE B: MATRICES (Ejercicios 11-20)

## Ejercicio 11: Crear Matriz Básica

Crea una matriz de 3x4 (3 filas, 4 columnas) con todos los valores inicializados en 0.

```python
# Escribe tu código aquí:









```

---

## Ejercicio 12: Llenar Matriz con Datos del Usuario

Dada una matriz de 3x3, escribe código que:

1. Use bucles anidados para recorrer cada posición
2. Pida al usuario un número para cada posición
3. Almacene el número en la matriz

```python
# Escribe tu código aquí:

















```

---

## Ejercicio 13: Mostrar Matriz Formateada

Escribe código para mostrar una matriz de 4x4 de forma visual, por ejemplo:

```
1  2  3  4
5  6  7  8
9  10 11 12
13 14 15 16
```

Asume: matriz `mat` de 4x4 ya llena con números.

```python
# Escribe tu código aquí:













```

---

## Ejercicio 14: Suma de Todos los Elementos

Dada una matriz de 3x5, escribe código que:

1. Sume todos los elementos de la matriz
2. Muestre el total

```python
# Escribe tu código aquí:

















```

---

## Ejercicio 15: Suma por Filas

Dada una matriz de 4x3, escribe código que:

1. Calcule la suma de cada fila
2. Muestre el resultado:
   ```
   Fila 0: suma = 15
   Fila 1: suma = 22
   Fila 2: suma = 18
   Fila 3: suma = 20
   ```

```python
# Escribe tu código aquí:





















```

---

## Ejercicio 16: Suma por Columnas

Dada una matriz de 3x4, escribe código que:

1. Calcule la suma de cada columna
2. Muestre el resultado de forma similar al ejercicio anterior

```python
# Escribe tu código aquí:





















```

---

## Ejercicio 17: Encontrar el Elemento Máximo

Dada una matriz de 5x5, escribe código que:

1. Encuentre el elemento más grande
2. Muestre su valor y su posición (fila, columna)

```python
# Escribe tu código aquí:


























```

---

## Ejercicio 18: Diagonal Principal

Dada una matriz cuadrada de 4x4, escribe código que:

1. Muestre solo los elementos de la diagonal principal
2. Calcule la suma de estos elementos

La diagonal principal son los elementos donde fila == columna: [0][0], [1][1], [2][2], [3][3]

```python
# Escribe tu código aquí:





















```

---

## Ejercicio 19: Transpuesta de una Matriz

Dada una matriz de 3x4, crea su matriz transpuesta (4x3) donde las filas se convierten en columnas.

Ejemplo:

```
Original 3x4:        Transpuesta 4x3:
1  2  3  4          1  5  9
5  6  7  8    →     2  6  10
9  10 11 12         3  7  11
                    4  8  12
```

```python
# Escribe tu código aquí:






























```

---

## Ejercicio 20: Búsqueda en Matriz (Desafío Final)

Dada una matriz de 5x5, escribe código que:

1. Pida un número al usuario
2. Busque ese número en toda la matriz
3. Si lo encuentra:
   - Muestre "Encontrado en fila X, columna Y"
   - Use una bandera para indicar que se encontró
4. Si no lo encuentra, muestre "No encontrado"

**Bonus:** Si el número aparece varias veces, muestra todas las posiciones.

```python
# Escribe tu código aquí:





































```

---

## EJERCICIOS BONUS (Opcionales)

### Ejercicio 21: Matriz de Objetos

Crea una matriz de 3x3 donde cada elemento es un objeto `Celda` con atributos: valor, activo (booleano).

Inicializa todos los objetos y establece todos como activo = True.

```python
# Escribe tu código aquí:


























```

---

### Ejercicio 22: Validar Matriz Simétrica

Escribe código que verifique si una matriz cuadrada es simétrica (es igual a su transpuesta).

Una matriz es simétrica si mat[i][j] == mat[j][i] para todos los i, j.

```python
# Escribe tu código aquí:


























```

---

## AUTOEVALUACIÓN

Marca las casillas conforme completes cada sección:

### Arreglos de Objetos:

- [ ] Ejercicio 1: Crear vector vacío
- [ ] Ejercicio 2: Llenar vector
- [ ] Ejercicio 3: Recorrer y mostrar
- [ ] Ejercicio 4: Buscar y contar
- [ ] Ejercicio 5: Calcular promedio
- [ ] Ejercicio 6: Encontrar máximo
- [ ] Ejercicio 7: Ordenamiento burbuja
- [ ] Ejercicio 8: Filtrar y crear nuevo vector
- [ ] Ejercicio 9: Eliminar duplicados
- [ ] Ejercicio 10: Agrupar y contar

### Matrices:

- [ ] Ejercicio 11: Crear matriz básica
- [ ] Ejercicio 12: Llenar matriz
- [ ] Ejercicio 13: Mostrar matriz
- [ ] Ejercicio 14: Suma total
- [ ] Ejercicio 15: Suma por filas
- [ ] Ejercicio 16: Suma por columnas
- [ ] Ejercicio 17: Elemento máximo
- [ ] Ejercicio 18: Diagonal principal
- [ ] Ejercicio 19: Transpuesta
- [ ] Ejercicio 20: Búsqueda en matriz

### Bonus:

- [ ] Ejercicio 21: Matriz de objetos
- [ ] Ejercicio 22: Validar simétrica

---

## CONCEPTOS CLAVE A DOMINAR

### Arreglos de Objetos:

- Crear vectores de tamaño fijo
- Usar contadores para saber cuántos elementos válidos hay
- Recorrer con `for i in range(cont)`
- Acceder a atributos: `vector[i].atributo`
- Acumular valores (sumas, conteos)
- Encontrar máximos/mínimos
- Ordenamiento básico
- Filtrado de datos

### Matrices:

- Crear matrices con `[[0] * cols for _ in range(filas)]`
- Bucles anidados para recorrer
- Acceder a elementos: `matriz[fila][columna]`
- Operaciones por filas
- Operaciones por columnas
- Diagonal principal: `i == j`
- Transpuesta: intercambiar filas por columnas

---

**Tiempo estimado: 2-3 horas**

**¡Mucho éxito! Consulta el archivo de respuestas cuando termines.** 🎯
