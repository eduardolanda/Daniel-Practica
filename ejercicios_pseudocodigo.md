# 📋 EJERCICIOS DE PSEUDOCÓDIGO
## Programación Orientada a Objetos - De Básico a Avanzado

**Nombre:** ______________________ **Fecha:** ______________________

**Instrucciones:** 
- Escribe pseudocódigo claro y estructurado
- Usa sangrías (indentación) para mostrar bloques
- Nombra variables de forma descriptiva
- No uses código Python, solo pseudocódigo en español

---

## ¿Qué es Pseudocódigo?

El pseudocódigo es una forma de escribir algoritmos usando lenguaje natural estructurado, sin seguir la sintaxis exacta de un lenguaje de programación. Es una herramienta para planificar antes de codificar.

### Palabras Clave Comunes:
- **INICIO / FIN** - Marcan el principio y final del programa
- **LEER** - Entrada de datos
- **ESCRIBIR / MOSTRAR** - Salida de datos
- **SI...ENTONCES...SINO** - Condicionales
- **MIENTRAS** - Bucle while
- **PARA** - Bucle for
- **HACER...MIENTRAS** - Bucle do-while
- **CLASE** - Definición de clase
- **MÉTODO** - Función dentro de una clase
- **CREAR** - Instanciar objeto
- **←** o **=** - Asignación

---

## EJERCICIO 1: Clase Básica ⭐
**Nivel: Básico**

Escribe el pseudocódigo para una clase llamada `Estudiante` que tenga:
- Atributos: nombre, edad, carrera
- Un constructor que inicialice los tres atributos
- Un método `mostrar()` que imprima todos los datos

```
# Escribe tu pseudocódigo aquí:



























```

---

## EJERCICIO 2: Crear y Mostrar Objeto ⭐
**Nivel: Básico**

Escribe el pseudocódigo para:
1. Crear un objeto de la clase `Estudiante` con datos: "Ana García", 20, "Ingeniería"
2. Mostrar los datos del objeto usando el método `mostrar()`

Usa la clase del Ejercicio 1.

```
# Escribe tu pseudocódigo aquí:



















```

---

## EJERCICIO 3: Atributos Privados y Métodos de Acceso ⭐⭐
**Nivel: Intermedio**

Escribe el pseudocódigo para una clase `CuentaBancaria` que tenga:
- Atributos públicos: titular
- Atributos privados: saldo
- Constructor que inicialice ambos
- Método `obtenerSaldo()` que retorne el saldo
- Método `establecerSaldo(nuevoSaldo)` que:
  - Verifique que el nuevo saldo sea mayor o igual a 0
  - Si es válido, actualice el saldo
  - Si no, muestre "Saldo inválido"

```
# Escribe tu pseudocódigo aquí:




































```

---

## EJERCICIO 4: Vector de Objetos ⭐⭐
**Nivel: Intermedio**

Escribe el pseudocódigo completo para:
1. Crear un vector `productos` de tamaño 10
2. Inicializar un contador en 0
3. Pedir al usuario cuántos productos desea agregar (máximo 10)
4. Para cada producto:
   - Leer nombre y precio
   - Crear objeto `Producto`
   - Agregarlo al vector
   - Incrementar contador
5. Mostrar todos los productos agregados

Asume que existe una clase `Producto` con constructor y método `mostrar()`.

```
# Escribe tu pseudocódigo aquí:

















































```

---

## EJERCICIO 5: Búsqueda en Vector de Objetos ⭐⭐
**Nivel: Intermedio**

Escribe el pseudocódigo para buscar un libro por título en un vector de objetos `Libro`.

El algoritmo debe:
1. Pedir al usuario el título a buscar
2. Usar una bandera `encontrado` inicializada en FALSO
3. Recorrer el vector de libros
4. Si encuentra el título:
   - Mostrar los datos del libro
   - Cambiar la bandera a VERDADERO
   - Salir del bucle
5. Si no lo encuentra, mostrar "Libro no encontrado"

Asume: vector `libros[]`, contador `cont`, clase `Libro` con atributo `titulo` y método `mostrar()`.

```
# Escribe tu pseudocódigo aquí:












































```

---

## EJERCICIO 6: Calcular Promedio ⭐⭐
**Nivel: Intermedio**

Escribe el pseudocódigo para calcular el promedio de calificaciones de todos los estudiantes en un vector.

El algoritmo debe:
1. Verificar que haya al menos un estudiante
2. Inicializar un acumulador en 0
3. Recorrer el vector sumando las calificaciones
4. Calcular el promedio (suma / cantidad)
5. Mostrar el resultado

Asume: vector `estudiantes[]`, contador `cont`, clase `Estudiante` con atributo `calificacion`.

```
# Escribe tu pseudocódigo aquí:








































```

---

## EJERCICIO 7: Validación de Datos ⭐⭐⭐
**Nivel: Avanzado**

Escribe el pseudocódigo para un método `validarEmail(email)` que verifique si un correo electrónico es válido.

Requisitos:
- Debe tener al menos 5 caracteres
- Debe contener exactamente un símbolo @
- Debe contener al menos un punto (.) después del @
- Retorna VERDADERO si es válido, FALSO si no

```
# Escribe tu pseudocódigo aquí:

















































```

---

## EJERCICIO 8: Ordenamiento de Burbuja ⭐⭐⭐
**Nivel: Avanzado**

Escribe el pseudocódigo del algoritmo de ordenamiento de burbuja para ordenar un vector de empleados por salario de mayor a menor.

El algoritmo debe:
- Usar dos bucles anidados
- Comparar elementos adyacentes
- Intercambiar si están en orden incorrecto
- Mostrar el vector ordenado al final

Asume: vector `empleados[]`, contador `cont`, clase `Empleado` con atributo `salario` y método `mostrar()`.

```
# Escribe tu pseudocódigo aquí:
















































































```

---

## EJERCICIO 9: Crear y Procesar Matriz ⭐⭐⭐
**Nivel: Avanzado**

Escribe el pseudocódigo completo para:
1. Crear una matriz de 4x4
2. Llenar la matriz con números del 1 al 16 (sin pedir al usuario)
3. Mostrar la matriz completa
4. Calcular y mostrar la suma de cada fila
5. Calcular y mostrar la suma de la diagonal principal

```
# Escribe tu pseudocódigo aquí:





































































































































```

---

## EJERCICIO 10: Sistema Completo con Menú ⭐⭐⭐⭐
**Nivel: Muy Avanzado**

Escribe el pseudocódigo completo de un sistema de biblioteca con las siguientes opciones:

**Menú:**
1. Agregar libro
2. Buscar libro por título
3. Mostrar todos los libros
4. Eliminar libro (lógicamente)
5. Salir

**Requisitos:**
- Usar un vector de máximo 20 libros
- Clase `Libro` con: titulo, autor, codigo (privado)
- Validar que el código tenga exactamente 4 dígitos
- Al agregar, verificar que hay espacio
- Al buscar, usar bandera
- Al eliminar, marcar titulo = " "
- Al mostrar, solo mostrar libros no eliminados
- El menú debe repetirse hasta elegir opción 5

**Este es el ejercicio más completo. Usa hojas adicionales si es necesario.**

```
# Escribe tu pseudocódigo aquí:






















































































































































































```

---

## CONSEJOS PARA ESCRIBIR BUEN PSEUDOCÓDIGO

### ✅ Buenas Prácticas:

1. **Usa sangrías (indentación)** para mostrar bloques de código
   ```
   SI condicion ENTONCES
       accion1
       accion2
   FIN SI
   ```

2. **Sé descriptivo pero conciso**
   - ✅ Bueno: `LEER nombreEstudiante`
   - ❌ Malo: `LEER x`

3. **Usa palabras clave consistentes**
   - Elige un estilo y manténlo (LEER vs INPUT)

4. **Estructura clara**
   - Inicio y fin bien definidos
   - Bloques visualmente separados

5. **Comenta lo importante**
   - Explica la lógica compleja
   - No documentes lo obvio

### ❌ Errores Comunes:

1. **No usar indentación**
   ```
   // ❌ Malo
   SI x > 0 ENTONCES
   MOSTRAR "Positivo"
   FIN SI
   
   // ✅ Bueno
   SI x > 0 ENTONCES
       MOSTRAR "Positivo"
   FIN SI
   ```

2. **Mezclar idiomas**
   ```
   // ❌ Malo
   LEER name
   IF edad > 18 THEN
   
   // ✅ Bueno
   LEER nombre
   SI edad > 18 ENTONCES
   ```

3. **Ser demasiado técnico**
   ```
   // ❌ Malo (parece código Python)
   estudiantes = [0] * 10
   for i in range(cont):
   
   // ✅ Bueno (pseudocódigo claro)
   CREAR vector estudiantes de tamaño 10
   PARA i desde 0 hasta cont-1 HACER
   ```

4. **Olvidar los FIN**
   ```
   // ❌ Malo
   SI condicion ENTONCES
       accion
   PARA i desde 1 hasta 10 HACER
   
   // ✅ Bueno
   SI condicion ENTONCES
       accion
   FIN SI
   PARA i desde 1 hasta 10 HACER
       accion
   FIN PARA
   ```

---

## FORMATO DE REFERENCIA

### Estructura de Clase:
```
CLASE NombreClase
    ATRIBUTOS:
        publico: tipo
        PRIVADO: tipo
    
    CONSTRUCTOR(parametros)
        INICIO
            ESTE.atributo ← parametro
        FIN CONSTRUCTOR
    
    MÉTODO nombreMetodo(parametros)
        INICIO
            // código del método
            RETORNAR valor (si aplica)
        FIN MÉTODO
FIN CLASE
```

### Crear Objeto:
```
nombreObjeto ← CREAR NombreClase(argumentos)
```

### Condicionales:
```
SI condicion ENTONCES
    acciones
SINO
    otras acciones
FIN SI
```

### Bucles:
```
// Bucle FOR
PARA variable DESDE inicio HASTA fin HACER
    acciones
FIN PARA

// Bucle MIENTRAS
MIENTRAS condicion HACER
    acciones
FIN MIENTRAS
```

### Vectores:
```
CREAR vector nombre[tamaño]
nombre[indice] ← valor
elemento ← nombre[indice]
```

### Matrices:
```
CREAR matriz nombre[filas][columnas]
nombre[i][j] ← valor
elemento ← nombre[i][j]
```

---

## AUTOEVALUACIÓN

Marca conforme completes:

- [ ] Ejercicio 1: Clase básica
- [ ] Ejercicio 2: Crear objeto
- [ ] Ejercicio 3: Atributos privados
- [ ] Ejercicio 4: Vector de objetos
- [ ] Ejercicio 5: Búsqueda en vector
- [ ] Ejercicio 6: Calcular promedio
- [ ] Ejercicio 7: Validación
- [ ] Ejercicio 8: Ordenamiento
- [ ] Ejercicio 9: Matrices
- [ ] Ejercicio 10: Sistema completo

**Tiempo estimado: 2-3 horas**

---

## NOTAS PERSONALES

_Usa este espacio para escribir conceptos importantes o dudas:_

<br><br><br><br><br><br>

---

**¡Éxito en tus ejercicios! El pseudocódigo es la base para programar en cualquier lenguaje.** 🎯
