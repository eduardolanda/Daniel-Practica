# ✅ RESPUESTAS - EJERCICIOS DE PSEUDOCÓDIGO

---

## EJERCICIO 1: Clase Básica

```
CLASE Estudiante
    ATRIBUTOS:
        nombre: texto
        edad: entero
        carrera: texto
    
    CONSTRUCTOR(n, e, c)
        INICIO
            ESTE.nombre ← n
            ESTE.edad ← e
            ESTE.carrera ← c
        FIN CONSTRUCTOR
    
    MÉTODO mostrar()
        INICIO
            ESCRIBIR "Nombre: ", ESTE.nombre
            ESCRIBIR "Edad: ", ESTE.edad
            ESCRIBIR "Carrera: ", ESTE.carrera
        FIN MÉTODO
FIN CLASE
```

**Explicación:**
- **CLASE** marca el inicio de la definición
- **ATRIBUTOS** lista las características con sus tipos
- **CONSTRUCTOR** inicializa el objeto con valores recibidos
- **ESTE** se refiere al objeto actual (equivalente a `self` en Python)
- **MÉTODO** define una acción que puede realizar el objeto
- Cada bloque termina con su respectivo **FIN**

---

## EJERCICIO 2: Crear y Mostrar Objeto

```
INICIO
    // Crear objeto estudiante1
    estudiante1 ← CREAR Estudiante("Ana García", 20, "Ingeniería")
    
    // Mostrar los datos
    estudiante1.mostrar()
FIN
```

**Explicación:**
- **CREAR** instancia un nuevo objeto de la clase
- Los argumentos se pasan al constructor en el orden definido
- El punto (.) accede a métodos y atributos del objeto
- `estudiante1.mostrar()` llama al método mostrar del objeto

**Salida esperada:**
```
Nombre: Ana García
Edad: 20
Carrera: Ingeniería
```

---

## EJERCICIO 3: Atributos Privados y Métodos de Acceso

```
CLASE CuentaBancaria
    ATRIBUTOS:
        titular: texto
        PRIVADO saldo: real
    
    CONSTRUCTOR(t, s)
        INICIO
            ESTE.titular ← t
            ESTE.saldo ← s
        FIN CONSTRUCTOR
    
    MÉTODO obtenerSaldo()
        INICIO
            RETORNAR ESTE.saldo
        FIN MÉTODO
    
    MÉTODO establecerSaldo(nuevoSaldo)
        INICIO
            SI nuevoSaldo >= 0 ENTONCES
                ESTE.saldo ← nuevoSaldo
            SINO
                ESCRIBIR "Saldo inválido"
            FIN SI
        FIN MÉTODO
FIN CLASE
```

**Explicación:**
- **PRIVADO** marca atributos que solo son accesibles dentro de la clase
- **obtenerSaldo()** es un getter que retorna el valor privado
- **establecerSaldo()** es un setter que valida antes de modificar
- La validación (`SI nuevoSaldo >= 0`) protege la integridad de los datos
- **RETORNAR** devuelve un valor al que llamó el método

**Ejemplo de uso:**
```
cuenta1 ← CREAR CuentaBancaria("Pedro López", 5000.0)
saldoActual ← cuenta1.obtenerSaldo()  // Retorna 5000.0
cuenta1.establecerSaldo(7000.0)       // Actualiza a 7000.0
cuenta1.establecerSaldo(-500.0)       // Muestra "Saldo inválido"
```

---

## EJERCICIO 4: Vector de Objetos

```
INICIO
    // Declarar e inicializar
    tamaño ← 10
    CREAR vector productos[tamaño]
    contador ← 0
    
    // Pedir cantidad
    ESCRIBIR "¿Cuántos productos desea agregar? (máximo 10):"
    LEER cantidad
    
    // Validar límite
    SI cantidad > 10 ENTONCES
        cantidad ← 10
        ESCRIBIR "Se agregarán solo 10 productos"
    FIN SI
    
    // Llenar el vector
    PARA i DESDE 0 HASTA cantidad-1 HACER
        ESCRIBIR "Producto ", i+1, ":"
        ESCRIBIR "Nombre:"
        LEER nombre
        ESCRIBIR "Precio:"
        LEER precio
        
        // Crear objeto y agregarlo
        producto ← CREAR Producto(nombre, precio)
        productos[contador] ← producto
        contador ← contador + 1
    FIN PARA
    
    // Mostrar todos los productos
    ESCRIBIR "Lista de productos:"
    PARA i DESDE 0 HASTA contador-1 HACER
        productos[i].mostrar()
    FIN PARA
FIN
```

**Explicación:**
- **CREAR vector** declara el arreglo con su tamaño
- Usamos un **contador** para rastrear cuántos elementos válidos hay
- **PARA i DESDE 0 HASTA cantidad-1** es el bucle for
- Dentro del bucle creamos cada objeto y lo agregamos
- **contador + 1** es equivalente a `cont = cont + 1`
- Al mostrar, recorremos solo hasta `contador-1` (elementos válidos)

**Flujo:**
1. Usuario dice cuántos productos agregará
2. Para cada producto: pedir datos → crear objeto → agregar al vector
3. Mostrar todos los agregados

---

## EJERCICIO 5: Búsqueda en Vector de Objetos

```
INICIO
    // Pedir título a buscar
    ESCRIBIR "Introduce el título del libro a buscar:"
    LEER tituloBuscar
    
    // Inicializar bandera
    encontrado ← FALSO
    
    // Buscar en el vector
    PARA i DESDE 0 HASTA cont-1 HACER
        SI libros[i].titulo = tituloBuscar ENTONCES
            ESCRIBIR "Libro encontrado:"
            libros[i].mostrar()
            encontrado ← VERDADERO
            SALIR DEL BUCLE
        FIN SI
    FIN PARA
    
    // Verificar si se encontró
    SI encontrado = FALSO ENTONCES
        ESCRIBIR "Libro no encontrado"
    FIN SI
FIN
```

**Explicación:**
- **Bandera** (encontrado) rastrea si se halló el elemento
- Se inicializa en **FALSO** antes del bucle
- **PARA** recorre todo el vector
- Al encontrar coincidencia: mostrar datos, cambiar bandera, salir
- **SALIR DEL BUCLE** es equivalente a `break` en Python
- Después del bucle verificamos la bandera
- Si sigue en FALSO, no se encontró

**Casos:**
- **Encontrado:** Muestra datos y no imprime "no encontrado"
- **No encontrado:** La bandera queda en FALSO y muestra mensaje

---

## EJERCICIO 6: Calcular Promedio

```
INICIO
    // Verificar que hay estudiantes
    SI cont = 0 ENTONCES
        ESCRIBIR "No hay estudiantes registrados"
    SINO
        // Inicializar acumulador
        sumaCalificaciones ← 0
        
        // Sumar todas las calificaciones
        PARA i DESDE 0 HASTA cont-1 HACER
            sumaCalificaciones ← sumaCalificaciones + estudiantes[i].calificacion
        FIN PARA
        
        // Calcular promedio
        promedio ← sumaCalificaciones / cont
        
        // Mostrar resultados
        ESCRIBIR "Suma total: ", sumaCalificaciones
        ESCRIBIR "Número de estudiantes: ", cont
        ESCRIBIR "Promedio: ", promedio
    FIN SI
FIN
```

**Explicación:**
- **Verificación inicial:** evita división por 0
- **Acumulador** (sumaCalificaciones) empieza en 0
- El bucle suma cada calificación al acumulador
- **Promedio** = suma total / cantidad de elementos
- **cont** es el divisor porque indica cuántos estudiantes hay

**Ejemplo numérico:**
```
Estudiante 1: 85
Estudiante 2: 90
Estudiante 3: 78

suma = 85 + 90 + 78 = 253
promedio = 253 / 3 = 84.33
```

---

## EJERCICIO 7: Validación de Datos

```
MÉTODO validarEmail(email)
    INICIO
        // 1. Verificar longitud mínima
        SI LONGITUD(email) < 5 ENTONCES
            RETORNAR FALSO
        FIN SI
        
        // 2. Contar símbolos @
        contadorArroba ← 0
        PARA i DESDE 0 HASTA LONGITUD(email)-1 HACER
            SI email[i] = '@' ENTONCES
                contadorArroba ← contadorArroba + 1
            FIN SI
        FIN PARA
        
        // Verificar que hay exactamente un @
        SI contadorArroba ≠ 1 ENTONCES
            RETORNAR FALSO
        FIN SI
        
        // 3. Encontrar posición del @
        posicionArroba ← -1
        PARA i DESDE 0 HASTA LONGITUD(email)-1 HACER
            SI email[i] = '@' ENTONCES
                posicionArroba ← i
                SALIR DEL BUCLE
            FIN SI
        FIN PARA
        
        // 4. Verificar que hay punto después del @
        hayPuntoDespues ← FALSO
        PARA i DESDE posicionArroba+1 HASTA LONGITUD(email)-1 HACER
            SI email[i] = '.' ENTONCES
                hayPuntoDespues ← VERDADERO
                SALIR DEL BUCLE
            FIN SI
        FIN PARA
        
        SI hayPuntoDespues = FALSO ENTONCES
            RETORNAR FALSO
        FIN SI
        
        // Si pasó todas las validaciones
        RETORNAR VERDADERO
    FIN MÉTODO
```

**Explicación:**
- **Validación por pasos:** cada requisito se verifica independientemente
- **LONGITUD()** retorna el número de caracteres
- **Contador manual** para contar @ (recorriendo todo el string)
- **Búsqueda de posición:** encontrar dónde está el @
- **Verificación posterior:** buscar punto solo DESPUÉS del @
- Si alguna validación falla, retorna FALSO inmediatamente
- Solo retorna VERDADERO si pasa todo

**Pruebas:**
```
validarEmail("abc") → FALSO (muy corto)
validarEmail("usuario@dominio.com") → VERDADERO
validarEmail("usuario@@dominio.com") → FALSO (dos @)
validarEmail("usuario@dominio") → FALSO (sin punto después de @)
```

---

## EJERCICIO 8: Ordenamiento de Burbuja

```
INICIO
    // Algoritmo de burbuja (mayor a menor por salario)
    PARA i DESDE 0 HASTA cont-2 HACER
        PARA j DESDE 0 HASTA (cont-2-i) HACER
            // Comparar salarios de posiciones adyacentes
            SI empleados[j].salario < empleados[j+1].salario ENTONCES
                // Intercambiar los objetos completos
                temporal ← empleados[j]
                empleados[j] ← empleados[j+1]
                empleados[j+1] ← temporal
            FIN SI
        FIN PARA
    FIN PARA
    
    // Mostrar vector ordenado
    ESCRIBIR "Empleados ordenados por salario (mayor a menor):"
    PARA i DESDE 0 HASTA cont-1 HACER
        empleados[i].mostrar()
    FIN PARA
FIN
```

**Explicación:**
- **Burbuja:** compara elementos adyacentes y los intercambia si están mal ordenados
- **Bucle externo (i):** número de pasadas = cont-1
- **Bucle interno (j):** compara hasta (cont-1-i) porque los últimos ya están ordenados
- **Condición para ordenar de mayor a menor:** `<` (si el actual es menor que el siguiente)
- **Intercambio en 3 pasos:**
  1. Guardar actual en temporal
  2. Copiar siguiente a actual
  3. Copiar temporal a siguiente
- Se intercambian los **objetos completos**, no solo el salario

**Visualización (3 elementos):**
```
Inicial: [50, 80, 60]
Pasada 1:
  Comparar 50 y 80 → intercambiar → [80, 50, 60]
  Comparar 50 y 60 → intercambiar → [80, 60, 50]
Pasada 2:
  Comparar 80 y 60 → no cambiar → [80, 60, 50]
Final: [80, 60, 50] ✓ (ordenado mayor a menor)
```

---

## EJERCICIO 9: Crear y Procesar Matriz

```
INICIO
    // 1. Crear matriz 4x4
    filas ← 4
    columnas ← 4
    CREAR matriz mat[filas][columnas]
    
    // 2. Llenar con números del 1 al 16
    numero ← 1
    PARA i DESDE 0 HASTA filas-1 HACER
        PARA j DESDE 0 HASTA columnas-1 HACER
            mat[i][j] ← numero
            numero ← numero + 1
        FIN PARA
    FIN PARA
    
    // 3. Mostrar la matriz
    ESCRIBIR "Matriz 4x4:"
    PARA i DESDE 0 HASTA filas-1 HACER
        PARA j DESDE 0 HASTA columnas-1 HACER
            ESCRIBIR mat[i][j], " "  // Sin salto de línea
        FIN PARA
        ESCRIBIR ""  // Salto de línea al final de cada fila
    FIN PARA
    
    // 4. Calcular suma de cada fila
    ESCRIBIR ""
    ESCRIBIR "Suma por filas:"
    PARA i DESDE 0 HASTA filas-1 HACER
        sumaFila ← 0
        PARA j DESDE 0 HASTA columnas-1 HACER
            sumaFila ← sumaFila + mat[i][j]
        FIN PARA
        ESCRIBIR "Fila ", i, ": suma = ", sumaFila
    FIN PARA
    
    // 5. Calcular suma de diagonal principal
    ESCRIBIR ""
    ESCRIBIR "Diagonal principal:"
    sumaDiagonal ← 0
    PARA i DESDE 0 HASTA filas-1 HACER
        ESCRIBIR "mat[", i, "][", i, "] = ", mat[i][i]
        sumaDiagonal ← sumaDiagonal + mat[i][i]
    FIN PARA
    ESCRIBIR "Suma de diagonal: ", sumaDiagonal
FIN
```

**Explicación:**

**Parte 1 - Crear matriz:**
- Matrices son arreglos bidimensionales
- Se accede con `[fila][columna]`

**Parte 2 - Llenar:**
- Bucles anidados recorren toda la matriz
- Variable `numero` va incrementando (1, 2, 3, ... 16)

**Parte 3 - Mostrar:**
- Bucle externo: filas
- Bucle interno: columnas (sin salto de línea)
- Al terminar cada fila, hacer salto de línea

**Parte 4 - Suma por filas:**
- Para cada fila, inicializar suma en 0
- Sumar todos los elementos de esa fila
- Mostrar el resultado de cada fila

**Parte 5 - Diagonal principal:**
- Diagonal: elementos donde fila = columna
- Solo un bucle porque `i = j`
- Acceso: `mat[i][i]`

**Salida esperada:**
```
Matriz 4x4:
1  2  3  4
5  6  7  8
9  10 11 12
13 14 15 16

Suma por filas:
Fila 0: suma = 10
Fila 1: suma = 26
Fila 2: suma = 42
Fila 3: suma = 58

Diagonal principal:
mat[0][0] = 1
mat[1][1] = 6
mat[2][2] = 11
mat[3][3] = 16
Suma de diagonal: 34
```

---

## EJERCICIO 10: Sistema Completo con Menú

```
// ==================== CLASE LIBRO ====================
CLASE Libro
    ATRIBUTOS:
        titulo: texto
        autor: texto
        PRIVADO codigo: texto
    
    CONSTRUCTOR(t, a)
        INICIO
            ESTE.titulo ← t
            ESTE.autor ← a
        FIN CONSTRUCTOR
    
    MÉTODO establecerCodigo(cod)
        INICIO
            ESTE.codigo ← cod
        FIN MÉTODO
    
    MÉTODO obtenerCodigo()
        INICIO
            RETORNAR ESTE.codigo
        FIN MÉTODO
    
    MÉTODO mostrar()
        INICIO
            ESCRIBIR "Título: ", ESTE.titulo
            ESCRIBIR "Autor: ", ESTE.autor
            ESCRIBIR "Código: ", ESTE.codigo
        FIN MÉTODO
FIN CLASE


// ==================== FUNCIÓN VALIDAR CÓDIGO ====================
FUNCIÓN validarCodigo(cod)
    INICIO
        // Verificar longitud
        SI LONGITUD(cod) ≠ 4 ENTONCES
            RETORNAR FALSO
        FIN SI
        
        // Verificar que todos sean dígitos
        PARA i DESDE 0 HASTA 3 HACER
            SI cod[i] < '0' O cod[i] > '9' ENTONCES
                RETORNAR FALSO
            FIN SI
        FIN PARA
        
        RETORNAR VERDADERO
    FIN FUNCIÓN


// ==================== PROGRAMA PRINCIPAL ====================
INICIO
    // Inicializar vector
    tamaño ← 20
    CREAR vector libros[tamaño]
    contador ← 0
    opcion ← 0
    
    // Menú principal
    MIENTRAS opcion ≠ 5 HACER
        ESCRIBIR ""
        ESCRIBIR "========== SISTEMA DE BIBLIOTECA =========="
        ESCRIBIR "1. Agregar libro"
        ESCRIBIR "2. Buscar libro por título"
        ESCRIBIR "3. Mostrar todos los libros"
        ESCRIBIR "4. Eliminar libro"
        ESCRIBIR "5. Salir"
        ESCRIBIR "Introduce la opción:"
        LEER opcion
        
        // ========== OPCIÓN 1: AGREGAR LIBRO ==========
        SI opcion = 1 ENTONCES
            SI contador < tamaño ENTONCES
                ESCRIBIR "Introduce el título:"
                LEER titulo
                ESCRIBIR "Introduce el autor:"
                LEER autor
                
                // Pedir y validar código
                ESCRIBIR "Introduce el código (4 dígitos):"
                LEER codigo
                MIENTRAS validarCodigo(codigo) = FALSO HACER
                    ESCRIBIR "Código inválido. Debe tener 4 dígitos:"
                    LEER codigo
                FIN MIENTRAS
                
                // Crear objeto y agregarlo
                libro ← CREAR Libro(titulo, autor)
                libro.establecerCodigo(codigo)
                libros[contador] ← libro
                contador ← contador + 1
                
                ESCRIBIR "✓ Libro agregado correctamente"
            SINO
                ESCRIBIR "✗ No hay espacio para más libros"
            FIN SI
        FIN SI
        
        // ========== OPCIÓN 2: BUSCAR LIBRO ==========
        SI opcion = 2 ENTONCES
            ESCRIBIR "Introduce el título a buscar:"
            LEER tituloBuscar
            encontrado ← FALSO
            
            PARA i DESDE 0 HASTA contador-1 HACER
                SI libros[i].titulo = tituloBuscar ENTONCES
                    ESCRIBIR "✓ Libro encontrado:"
                    libros[i].mostrar()
                    encontrado ← VERDADERO
                    SALIR DEL BUCLE
                FIN SI
            FIN PARA
            
            SI encontrado = FALSO ENTONCES
                ESCRIBIR "✗ Libro no encontrado"
            FIN SI
        FIN SI
        
        // ========== OPCIÓN 3: MOSTRAR TODOS ==========
        SI opcion = 3 ENTONCES
            ESCRIBIR "========== LISTA DE LIBROS =========="
            hayLibros ← FALSO
            
            PARA i DESDE 0 HASTA contador-1 HACER
                SI libros[i].titulo ≠ " " ENTONCES
                    libros[i].mostrar()
                    ESCRIBIR "--------------------"
                    hayLibros ← VERDADERO
                FIN SI
            FIN PARA
            
            SI hayLibros = FALSO ENTONCES
                ESCRIBIR "No hay libros registrados"
            FIN SI
        FIN SI
        
        // ========== OPCIÓN 4: ELIMINAR LIBRO ==========
        SI opcion = 4 ENTONCES
            ESCRIBIR "Introduce el título del libro a eliminar:"
            LEER tituloEliminar
            encontrado ← FALSO
            
            PARA i DESDE 0 HASTA contador-1 HACER
                SI libros[i].titulo = tituloEliminar ENTONCES
                    // Eliminación lógica
                    libros[i].titulo ← " "
                    libros[i].autor ← " "
                    libros[i].establecerCodigo(" ")
                    encontrado ← VERDADERO
                    ESCRIBIR "✓ Libro eliminado correctamente"
                    SALIR DEL BUCLE
                FIN SI
            FIN PARA
            
            SI encontrado = FALSO ENTONCES
                ESCRIBIR "✗ Libro no encontrado"
            FIN SI
        FIN SI
        
        // ========== OPCIÓN 5: SALIR ==========
        SI opcion = 5 ENTONCES
            ESCRIBIR "¡Hasta luego!"
        FIN SI
        
        // Validar opción incorrecta
        SI opcion < 1 O opcion > 5 ENTONCES
            ESCRIBIR "✗ Opción inválida. Intenta de nuevo."
        FIN SI
    FIN MIENTRAS
FIN
```

**Explicación completa:**

**Estructura:**
1. **Clase Libro:** Define el tipo de objeto
2. **Función validarCodigo:** Valida que tenga 4 dígitos
3. **Programa principal:** Contiene el menú y la lógica

**Opción 1 - Agregar:**
- Verifica espacio disponible
- Pide datos al usuario
- Valida código en bucle MIENTRAS
- Crea objeto, lo configura y lo agrega
- Incrementa contador

**Opción 2 - Buscar:**
- Usa bandera `encontrado`
- Recorre el vector comparando títulos
- Si encuentra: muestra y sale
- Si no encuentra: muestra mensaje

**Opción 3 - Mostrar todos:**
- Recorre todo el vector
- Filtra los eliminados (titulo ≠ " ")
- Solo muestra los válidos
- Usa bandera para saber si hay alguno

**Opción 4 - Eliminar:**
- Busca por título
- Eliminación lógica (marca con " ")
- No reorganiza el vector
- Usa bandera para confirmar

**Opción 5 - Salir:**
- Sale del bucle MIENTRAS
- Muestra mensaje de despedida

**Control del menú:**
- MIENTRAS opcion ≠ 5: se repite hasta salir
- Cada opción en su propio SI
- Validación de opción incorrecta al final

---

## CONCEPTOS CLAVE DOMINADOS

### 1. Estructura de Clase
- Atributos (públicos y privados)
- Constructor
- Métodos (getters, setters, mostrar)

### 2. Creación de Objetos
- Sintaxis: `objeto ← CREAR Clase(argumentos)`
- Acceso a métodos: `objeto.metodo()`
- Acceso a atributos públicos: `objeto.atributo`

### 3. Vectores de Objetos
- Declaración con tamaño
- Uso de contador
- Agregar, buscar, mostrar, eliminar

### 4. Algoritmos de Búsqueda
- Búsqueda lineal con bandera
- Salir del bucle al encontrar
- Verificar bandera después

### 5. Algoritmos de Acumulación
- Inicializar acumulador en 0
- Sumar en bucle
- Calcular promedio

### 6. Validaciones
- Verificar condiciones múltiples
- Retornar VERDADERO/FALSO
- Usar en bucles MIENTRAS

### 7. Ordenamiento
- Burbuja con bucles anidados
- Intercambio con temporal
- Objetos completos, no solo atributos

### 8. Matrices
- Bucles anidados
- Acceso [fila][columna]
- Operaciones por filas/columnas
- Diagonal principal

### 9. Menús
- Bucle MIENTRAS
- Estructura SI-SI-SI
- Validación de opciones

### 10. Buenas Prácticas
- Indentación consistente
- Nombres descriptivos
- Comentarios claros
- Validaciones antes de procesar

---

## DIFERENCIAS: PSEUDOCÓDIGO vs PYTHON

| Concepto | Pseudocódigo | Python |
|----------|--------------|--------|
| Asignación | `x ← 5` | `x = 5` |
| Condicional | `SI...ENTONCES...FIN SI` | `if...:`  |
| Bucle | `PARA i DESDE 0 HASTA 9` | `for i in range(10):` |
| Clase | `CLASE NombreClase` | `class NombreClase:` |
| Crear objeto | `obj ← CREAR Clase()` | `obj = Clase()` |
| Método | `MÉTODO nombre()` | `def nombre(self):` |
| Retornar | `RETORNAR valor` | `return valor` |
| Leer | `LEER variable` | `variable = input()` |
| Escribir | `ESCRIBIR "texto"` | `print("texto")` |
| Verdadero/Falso | `VERDADERO/FALSO` | `True/False` |

---

## TIPS FINALES

### ✅ El pseudocódigo es útil para:
1. **Planificar** antes de codificar
2. **Comunicar** ideas sin depender de un lenguaje específico
3. **Estudiar** algoritmos sin preocuparse por sintaxis
4. **Diseñar** la lógica de forma clara

### 📝 Recuerda:
- **No hay sintaxis estricta** en pseudocódigo
- Lo importante es la **claridad y la lógica**
- La **indentación** es crucial para legibilidad
- Usa **nombres descriptivos** de variables
- **Comenta** la lógica compleja

### 🎯 Para el examen:
- Practica escribir pseudocódigo a mano
- Revisa la lógica, no la sintaxis
- Asegúrate de que cada bloque tenga su FIN
- Usa sangrías consistentes
- Verifica que la lógica fluya correctamente

---

**¡Éxito en tu examen! El pseudocódigo bien escrito demuestra comprensión profunda de la lógica.** 🎓
