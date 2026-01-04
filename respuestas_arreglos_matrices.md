# ✅ RESPUESTAS - ARREGLOS DE OBJETOS Y MATRICES

---

# PARTE A: ARREGLOS DE OBJETOS

## Ejercicio 1: Crear Vector de Objetos Vacío

```python
tam = 15
alumnos = [0] * tam
cont = 0
```

**Explicación:**

- Definimos el tamaño del vector
- Inicializamos el vector con 0s
- El contador empieza en 0 porque no hay alumnos aún

---

## Ejercicio 2: Llenar Vector con Objetos

```python
print("¿Cuántos alumnos deseas agregar? (máximo 15):")
cantidad = int(input())

# Validar que no exceda el límite
if cantidad > 15:
    cantidad = 15
    print("Se agregarán solo 15 alumnos")

for i in range(cantidad):
    print(f"\nAlumno {i+1}:")
    print("Nombre:")
    nombre = input()
    print("Matrícula:")
    matricula = input()
    print("Calificación:")
    calificacion = float(input())

    # Crear objeto y agregarlo
    alumno = Alumno(nombre, matricula, calificacion)
    alumnos[cont] = alumno
    cont = cont + 1

print(f"\n{cont} alumnos agregados correctamente")
```

**Explicación:**

- Preguntamos cuántos alumnos se agregarán
- Validamos que no exceda el tamaño del vector
- Usamos un bucle `for` para pedir datos de cada alumno
- Creamos cada objeto dentro del bucle
- Incrementamos el contador en cada iteración
- Usamos `i+1` para mostrar números desde 1 (más natural para usuarios)

---

## Ejercicio 3: Recorrer y Mostrar Todos los Objetos

```python
print("Lista de alumnos:")
print("-" * 40)

for i in range(cont):
    print(f"\nAlumno {i+1}:")
    alumnos[i].mostrar()
    print("-" * 40)
```

**Explicación:**

- Recorremos solo hasta `cont` (elementos válidos)
- Llamamos al método `mostrar()` de cada objeto
- Agregamos líneas separadoras para mejor visualización
- `print("-" * 40)` imprime 40 guiones

---

## Ejercicio 4: Buscar y Contar

```python
print("Introduce la categoría a buscar:")
categoria_buscar = input()

contador_categoria = 0

for i in range(cont):
    if productos[i].categoria == categoria_buscar:
        contador_categoria = contador_categoria + 1

print(f"Total de productos en categoría '{categoria_buscar}': {contador_categoria}")
```

**Explicación:**

- Inicializamos un contador en 0
- Recorremos todos los productos
- Si la categoría coincide, incrementamos el contador
- Al final mostramos el total
- No usamos bandera `encontrado` porque queremos contar TODOS

---

## Ejercicio 5: Calcular Promedio de Atributos

```python
if cont == 0:
    print("No hay empleados registrados")
else:
    suma_salarios = 0

    for i in range(cont):
        suma_salarios = suma_salarios + empleados[i].salario

    promedio = suma_salarios / cont

    print(f"Suma total de salarios: ${suma_salarios:.2f}")
    print(f"Promedio de salarios: ${promedio:.2f}")
```

**Explicación:**

- Verificamos que haya al menos un empleado (evitar división por 0)
- Acumulamos todos los salarios en una variable
- Calculamos el promedio: suma / cantidad
- Usamos `.2f` para mostrar 2 decimales
- `cont` es el divisor porque indica cuántos empleados hay

---

## Ejercicio 6: Encontrar el Máximo

```python
if cont == 0:
    print("No hay empleados registrados")
else:
    # Inicializar con el primer empleado
    salario_maximo = empleados[0].salario
    empleado_max = empleados[0]

    # Buscar en el resto
    for i in range(1, cont):
        if empleados[i].salario > salario_maximo:
            salario_maximo = empleados[i].salario
            empleado_max = empleados[i]

    print("Empleado con el salario más alto:")
    print(f"Nombre: {empleado_max.nombre}")
    print(f"Salario: ${salario_maximo:.2f}")
```

**Explicación:**

- Inicializamos el máximo con el primer elemento
- Recorremos desde el índice 1 (ya consideramos el 0)
- Comparamos cada salario con el máximo actual
- Si encontramos uno mayor, actualizamos el máximo y guardamos el objeto
- Al final tenemos el empleado con el mayor salario

---

## Ejercicio 7: Ordenamiento de Burbuja Básico

```python
# Algoritmo de burbuja (mayor a menor)
for i in range(cont - 1):
    for j in range(cont - 1 - i):
        if estudiantes[j].calificacion < estudiantes[j + 1].calificacion:
            # Intercambiar objetos completos
            temp = estudiantes[j]
            estudiantes[j] = estudiantes[j + 1]
            estudiantes[j + 1] = temp

print("Estudiantes ordenados de mayor a menor calificación:")
for i in range(cont):
    print(f"{estudiantes[i].nombre}: {estudiantes[i].calificacion}")
```

**Explicación:**

- Bucle externo: `i` va de 0 a cont-1
- Bucle interno: `j` va de 0 a (cont-1-i) porque los últimos ya están ordenados
- Comparamos calificaciones de posiciones adyacentes
- Si están en orden incorrecto (menor < mayor para descendente), los intercambiamos
- Intercambiamos los objetos COMPLETOS, no solo un atributo
- Usamos una variable temporal para el intercambio
- Al final mostramos el resultado ordenado

**Análisis del intercambio:**

```
temp = estudiantes[j]        # Guardar en temporal
estudiantes[j] = estudiantes[j+1]  # Copiar siguiente a actual
estudiantes[j+1] = temp      # Copiar temporal a siguiente
```

---

## Ejercicio 8: Filtrar y Crear Nuevo Vector

```python
# Crear nuevo vector
tam_caros = 20
productos_caros = [0] * tam_caros
cont_caros = 0

# Filtrar productos
for i in range(cont):
    if productos[i].precio > 1000:
        if cont_caros < tam_caros:
            productos_caros[cont_caros] = productos[i]
            cont_caros = cont_caros + 1

# Mostrar resultados
print(f"Se encontraron {cont_caros} productos con precio mayor a $1000:")
for i in range(cont_caros):
    print(f"- {productos_caros[i].nombre}: ${productos_caros[i].precio:.2f}")
```

**Explicación:**

- Creamos un nuevo vector independiente
- Recorremos el vector original
- Si el producto cumple la condición, lo copiamos al nuevo vector
- Verificamos que haya espacio antes de copiar
- Incrementamos el contador del nuevo vector
- Al final mostramos cuántos se copiaron
- Los objetos se copian por referencia (apuntan al mismo objeto)

---

## Ejercicio 9: Eliminar Duplicados por Atributo

```python
duplicados_eliminados = 0

for i in range(cont):
    # Si ya fue eliminado, saltar
    if contactos[i].nombre == " ":
        continue

    # Buscar duplicados de este contacto
    for j in range(i + 1, cont):
        # Si ya fue eliminado, saltar
        if contactos[j].nombre == " ":
            continue

        # Si tienen el mismo teléfono
        if contactos[i].telefono == contactos[j].telefono:
            # Eliminar el duplicado (el segundo)
            contactos[j].nombre = " "
            contactos[j].telefono = " "
            duplicados_eliminados = duplicados_eliminados + 1

print(f"Se eliminaron {duplicados_eliminados} contactos duplicados")

# Mostrar contactos únicos
print("\nContactos únicos:")
for i in range(cont):
    if contactos[i].nombre != " ":
        contactos[i].mostrar()
```

**Explicación:**

- Usamos dos bucles anidados para comparar cada par de contactos
- El bucle interno empieza en `i+1` para evitar comparar un contacto consigo mismo
- Si ya fue eliminado (nombre = " "), lo saltamos con `continue`
- Si encontramos duplicado, eliminamos el segundo (j)
- Contamos cuántos se eliminaron
- Al final mostramos solo los no eliminados

**Por qué funciona:**

- Comparamos contacto[0] con contacto[1], contacto[2], ... contacto[n]
- Comparamos contacto[1] con contacto[2], contacto[3], ... contacto[n]
- Y así sucesivamente
- Esto garantiza que comparamos todos los pares sin repetir

---

## Ejercicio 10: Agrupar y Contar por Categoría

```python
# Contadores para cada género
ficcion = 0
ciencia = 0
historia = 0

# Recorrer y contar
for i in range(cont):
    genero = libros[i].genero

    if genero == "Ficción":
        ficcion = ficcion + 1
    elif genero == "Ciencia":
        ciencia = ciencia + 1
    elif genero == "Historia":
        historia = historia + 1

# Mostrar resumen
print("=== RESUMEN POR GÉNERO ===")
print(f"Ficción: {ficcion} libros")
print(f"Ciencia: {ciencia} libros")
print(f"Historia: {historia} libros")
print(f"Total: {cont} libros")
```

**Explicación:**

- Creamos un contador para cada categoría conocida
- Recorremos todos los libros
- Usamos if-elif para incrementar el contador correspondiente
- Al final mostramos el resumen de todos
- Es importante que los nombres coincidan exactamente (mayúsculas/minúsculas)

**Alternativa con diccionario (avanzado):**

```python
conteo = {"Ficción": 0, "Ciencia": 0, "Historia": 0}

for i in range(cont):
    genero = libros[i].genero
    if genero in conteo:
        conteo[genero] = conteo[genero] + 1

for genero, cantidad in conteo.items():
    print(f"{genero}: {cantidad} libros")
```

---

# PARTE B: MATRICES

## Ejercicio 11: Crear Matriz Básica

```python
filas = 3
columnas = 4

# Método 1: List comprehension
matriz = [[0 for j in range(columnas)] for i in range(filas)]

# Método 2: Bucles anidados
matriz = []
for i in range(filas):
    fila = []
    for j in range(columnas):
        fila.append(0)
    matriz.append(fila)

print("Matriz creada de", filas, "x", columnas)
```

**Explicación:**

- Una matriz es una lista de listas
- El método 1 (list comprehension) es más compacto
- El método 2 (bucles) es más claro para principiantes
- `matriz[i][j]` accede a la fila `i`, columna `j`
- Se crea desde afuera hacia adentro: primero filas, luego columnas

**Visualización:**

```
matriz[0] = [0, 0, 0, 0]  # Fila 0
matriz[1] = [0, 0, 0, 0]  # Fila 1
matriz[2] = [0, 0, 0, 0]  # Fila 2
```

---

## Ejercicio 12: Llenar Matriz con Datos del Usuario

```python
filas = 3
columnas = 3
matriz = [[0 for j in range(columnas)] for i in range(filas)]

print("Introduce los valores para la matriz 3x3:")

for i in range(filas):
    for j in range(columnas):
        print(f"Elemento [{i}][{j}]:")
        valor = int(input())
        matriz[i][j] = valor

print("\nMatriz completa:")
for i in range(filas):
    print(matriz[i])
```

**Explicación:**

- Bucle externo recorre las filas
- Bucle interno recorre las columnas de cada fila
- Pedimos un valor para cada posición
- Almacenamos el valor en `matriz[i][j]`
- Al final mostramos la matriz completa
- El orden es importante: primero todas las columnas de la fila 0, luego fila 1, etc.

---

## Ejercicio 13: Mostrar Matriz Formateada

```python
filas = 4
columnas = 4

for i in range(filas):
    for j in range(columnas):
        print(f"{matriz[i][j]:3}", end=" ")
    print()  # Nueva línea al terminar cada fila
```

**Explicación:**

- `{matriz[i][j]:3}` formatea el número con 3 espacios
- `end=" "` evita el salto de línea y agrega un espacio
- `print()` al final del bucle interno hace el salto de línea
- Esto alinea los números en columnas

**Salida:**

```
  1   2   3   4
  5   6   7   8
  9  10  11  12
 13  14  15  16
```

**Versión con más formato:**

```python
for i in range(filas):
    fila_texto = ""
    for j in range(columnas):
        fila_texto = fila_texto + f"{matriz[i][j]:4}"
    print(fila_texto)
```

---

## Ejercicio 14: Suma de Todos los Elementos

```python
filas = 3
columnas = 5

suma_total = 0

for i in range(filas):
    for j in range(columnas):
        suma_total = suma_total + matriz[i][j]

print(f"La suma de todos los elementos es: {suma_total}")
```

**Explicación:**

- Inicializamos acumulador en 0
- Recorremos cada elemento de la matriz
- Sumamos cada elemento al acumulador
- Los bucles anidados garantizan que visitamos todos los elementos
- No importa el orden (filas primero o columnas primero)

---

## Ejercicio 15: Suma por Filas

```python
filas = 4
columnas = 3

for i in range(filas):
    suma_fila = 0

    # Sumar todos los elementos de esta fila
    for j in range(columnas):
        suma_fila = suma_fila + matriz[i][j]

    print(f"Fila {i}: suma = {suma_fila}")
```

**Explicación:**

- El bucle externo recorre cada fila
- Para cada fila, inicializamos su suma en 0
- El bucle interno suma todos los elementos de esa fila
- Mostramos el resultado de cada fila
- El acumulador se reinicia para cada fila nueva

**Ejemplo con matriz:**

```
Matriz:
1  2  3
4  5  6
7  8  9
10 11 12

Resultado:
Fila 0: suma = 6  (1+2+3)
Fila 1: suma = 15 (4+5+6)
Fila 2: suma = 24 (7+8+9)
Fila 3: suma = 33 (10+11+12)
```

---

## Ejercicio 16: Suma por Columnas

```python
filas = 3
columnas = 4

for j in range(columnas):
    suma_columna = 0

    # Sumar todos los elementos de esta columna
    for i in range(filas):
        suma_columna = suma_columna + matriz[i][j]

    print(f"Columna {j}: suma = {suma_columna}")
```

**Explicación:**

- Ahora el bucle externo recorre columnas
- El bucle interno recorre filas (al revés que antes)
- Para la columna j, sumamos matriz[0][j], matriz[1][j], matriz[2][j]...
- Es importante invertir el orden de los bucles

**Diferencia clave:**

- Suma por filas: `for i → for j → suma matriz[i][j]`
- Suma por columnas: `for j → for i → suma matriz[i][j]`

---

## Ejercicio 17: Encontrar el Elemento Máximo

```python
filas = 5
columnas = 5

# Inicializar con el primer elemento
maximo = matriz[0][0]
fila_max = 0
columna_max = 0

# Buscar en toda la matriz
for i in range(filas):
    for j in range(columnas):
        if matriz[i][j] > maximo:
            maximo = matriz[i][j]
            fila_max = i
            columna_max = j

print(f"Elemento máximo: {maximo}")
print(f"Posición: fila {fila_max}, columna {columna_max}")
print(f"Ubicación: matriz[{fila_max}][{columna_max}]")
```

**Explicación:**

- Inicializamos el máximo con el primer elemento
- Guardamos también su posición (fila y columna)
- Recorremos toda la matriz
- Si encontramos un elemento mayor, actualizamos máximo y posición
- Al final tenemos el valor y su ubicación

---

## Ejercicio 18: Diagonal Principal

```python
filas = 4
columnas = 4

print("Elementos de la diagonal principal:")
suma_diagonal = 0

for i in range(filas):
    elemento = matriz[i][i]  # Diagonal: i == j
    print(f"matriz[{i}][{i}] = {elemento}")
    suma_diagonal = suma_diagonal + elemento

print(f"\nSuma de la diagonal principal: {suma_diagonal}")
```

**Explicación:**

- La diagonal principal está donde fila == columna
- En una matriz 4x4: [0][0], [1][1], [2][2], [3][3]
- Solo necesitamos un bucle porque i = j
- Accedemos con `matriz[i][i]`
- Acumulamos la suma mientras recorremos

**Visualización:**

```
X  .  .  .
.  X  .  .
.  .  X  .
.  .  .  X
```

---

## Ejercicio 19: Transpuesta de una Matriz

```python
# Matriz original 3x4
filas = 3
columnas = 4

# Crear matriz transpuesta 4x3
filas_t = columnas
columnas_t = filas
transpuesta = [[0 for j in range(columnas_t)] for i in range(filas_t)]

# Calcular transpuesta
for i in range(filas):
    for j in range(columnas):
        transpuesta[j][i] = matriz[i][j]

# Mostrar original
print("Matriz original 3x4:")
for i in range(filas):
    for j in range(columnas):
        print(f"{matriz[i][j]:3}", end=" ")
    print()

# Mostrar transpuesta
print("\nMatriz transpuesta 4x3:")
for i in range(filas_t):
    for j in range(columnas_t):
        print(f"{transpuesta[i][j]:3}", end=" ")
    print()
```

**Explicación:**

- La transpuesta de una matriz MxN es una matriz NxM
- Las filas se convierten en columnas y viceversa
- La clave es: `transpuesta[j][i] = matriz[i][j]`
- Intercambiamos los índices

**Proceso:**

```
matriz[0][0] → transpuesta[0][0]
matriz[0][1] → transpuesta[1][0]
matriz[0][2] → transpuesta[2][0]
matriz[1][0] → transpuesta[0][1]
matriz[1][1] → transpuesta[1][1]
...
```

---

## Ejercicio 20: Búsqueda en Matriz (Desafío Final)

```python
filas = 5
columnas = 5

print("Introduce el número a buscar:")
numero = int(input())

encontrado = False
posiciones = []

# Buscar en toda la matriz
for i in range(filas):
    for j in range(columnas):
        if matriz[i][j] == numero:
            posiciones.append((i, j))
            encontrado = True

# Mostrar resultados
if encontrado:
    print(f"✓ Número {numero} encontrado en {len(posiciones)} posición(es):")
    for pos in posiciones:
        print(f"  - Fila {pos[0]}, Columna {pos[1]}")
else:
    print(f"✗ Número {numero} no encontrado en la matriz")
```

**Explicación:**

- Usamos una bandera para saber si se encontró
- Usamos una lista para guardar TODAS las posiciones
- `posiciones.append((i, j))` guarda una tupla con fila y columna
- Si encontramos al menos uno, cambiamos la bandera
- Al final mostramos todas las posiciones encontradas

**Versión simple (solo primera ocurrencia):**

```python
numero = int(input("Número a buscar: "))
encontrado = False

for i in range(filas):
    for j in range(columnas):
        if matriz[i][j] == numero:
            print(f"Encontrado en fila {i}, columna {j}")
            encontrado = True
            break
    if encontrado:
        break

if not encontrado:
    print("No encontrado")
```

---

# EJERCICIOS BONUS

## Ejercicio 21: Matriz de Objetos

```python
class Celda:
    valor = 0
    activo = False

    def __init__(self, v):
        self.valor = v
        self.activo = True

    def mostrar(self):
        estado = "Activo" if self.activo else "Inactivo"
        print(f"Valor: {self.valor}, Estado: {estado}")


# Crear matriz 3x3 de objetos
filas = 3
columnas = 3
matriz_objetos = [[None for j in range(columnas)] for i in range(filas)]

# Inicializar con objetos
contador = 1
for i in range(filas):
    for j in range(columnas):
        matriz_objetos[i][j] = Celda(contador)
        contador = contador + 1

# Mostrar matriz de objetos
print("Matriz de objetos:")
for i in range(filas):
    for j in range(columnas):
        celda = matriz_objetos[i][j]
        print(f"[{i}][{j}]: ", end="")
        celda.mostrar()
```

**Explicación:**

- Creamos una matriz donde cada elemento es un objeto
- Inicializamos con `None` para indicar que son objetos
- Recorremos la matriz y creamos un objeto Celda para cada posición
- Cada celda tiene un valor único (1, 2, 3, ..., 9)
- Todos empiezan con activo = True
- Podemos acceder a métodos: `matriz_objetos[i][j].mostrar()`

---

## Ejercicio 22: Validar Matriz Simétrica

```python
def es_simetrica(matriz, n):
    """
    Verifica si una matriz cuadrada n x n es simétrica
    """
    for i in range(n):
        for j in range(n):
            if matriz[i][j] != matriz[j][i]:
                return False
    return True


# Ejemplo de uso
filas = 4
columnas = 4

if filas != columnas:
    print("La matriz debe ser cuadrada para verificar simetría")
else:
    if es_simetrica(matriz, filas):
        print("✓ La matriz ES simétrica")
    else:
        print("✗ La matriz NO es simétrica")
```

**Explicación:**

- Una matriz es simétrica si es igual a su transpuesta
- Es decir, `matriz[i][j] == matriz[j][i]` para todos los i, j
- Solo necesitamos verificar que cada par de elementos reflejados sea igual
- Si encontramos un par que no cumple, retornamos False inmediatamente
- Solo matrices cuadradas pueden ser simétricas

**Ejemplo de matriz simétrica:**

```
1  2  3
2  4  5
3  5  6

mat[0][1] = 2 = mat[1][0] ✓
mat[0][2] = 3 = mat[2][0] ✓
mat[1][2] = 5 = mat[2][1] ✓
```

**Ejemplo de matriz NO simétrica:**

```
1  2  3
4  5  6
7  8  9

mat[0][1] = 2 ≠ mat[1][0] = 4 ✗
```

---

## PATRONES IMPORTANTES

### Patrón 1: Recorrer Vector de Objetos

```python
for i in range(cont):
    vector[i].metodo()
    # o acceder a atributo
    valor = vector[i].atributo
```

### Patrón 2: Buscar en Vector de Objetos

```python
encontrado = False
for i in range(cont):
    if vector[i].atributo == valor_buscar:
        # Acción
        encontrado = True
        break
```

### Patrón 3: Acumular Valores de Objetos

```python
suma = 0
for i in range(cont):
    suma = suma + vector[i].atributo
promedio = suma / cont
```

### Patrón 4: Crear Matriz

```python
matriz = [[0 for j in range(columnas)] for i in range(filas)]
```

### Patrón 5: Recorrer Matriz Completa

```python
for i in range(filas):
    for j in range(columnas):
        # Procesar matriz[i][j]
```

### Patrón 6: Procesar por Filas

```python
for i in range(filas):
    # Inicializar para esta fila
    suma_fila = 0
    for j in range(columnas):
        suma_fila += matriz[i][j]
    # Mostrar/usar resultado de la fila
```

### Patrón 7: Procesar por Columnas

```python
for j in range(columnas):
    # Inicializar para esta columna
    suma_col = 0
    for i in range(filas):
        suma_col += matriz[i][j]
    # Mostrar/usar resultado de la columna
```

---

## ERRORES COMUNES

### Error 1: Crear matriz incorrectamente

```python
# ❌ Incorrecto (todas las filas apuntan a la misma lista)
matriz = [[0] * columnas] * filas

# ✅ Correcto
matriz = [[0 for j in range(columnas)] for i in range(filas)]
```

### Error 2: Confundir filas y columnas

```python
# ❌ Incorrecto
for i in range(columnas):  # ERROR: columnas en filas
    for j in range(filas):

# ✅ Correcto
for i in range(filas):
    for j in range(columnas):
```

### Error 3: No verificar espacio antes de agregar

```python
# ❌ Incorrecto (puede causar índice fuera de rango)
vector[cont] = objeto
cont = cont + 1

# ✅ Correcto
if cont < tam:
    vector[cont] = objeto
    cont = cont + 1
else:
    print("Vector lleno")
```

### Error 4: Olvidar incrementar contador

```python
# ❌ Incorrecto
vector[cont] = objeto
# Falta incrementar cont

# ✅ Correcto
vector[cont] = objeto
cont = cont + 1
```

### Error 5: Acceso incorrecto a matriz

```python
# ❌ Incorrecto
elemento = matriz[j][i]  # Índices invertidos

# ✅ Correcto (para fila i, columna j)
elemento = matriz[i][j]
```

---

**¡Fin de las respuestas!** ✅

Compara tus soluciones con estas. Si tienes diferencias, analiza cuál es más eficiente o correcta. 🎓
