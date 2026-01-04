# 📚 GUÍA DE ESTUDIO - PROGRAMACIÓN ORIENTADA A OBJETOS EN PYTHON

## Índice

1. [Conceptos Básicos](#nivel-1-conceptos-básicos)
2. [Nivel Intermedio](#nivel-2-intermedio)
3. [Nivel Avanzado](#nivel-3-avanzado)
4. [Ejercicios Prácticos](#ejercicios-prácticos)
5. [Preguntas de Examen](#preguntas-de-examen)

---

## NIVEL 1: CONCEPTOS BÁSICOS

### 1.1 ¿Qué es una Clase?

Una clase es un molde o plantilla para crear objetos. Define atributos (características) y métodos (acciones).

**Sintaxis básica:**

```python
class NombreClase:
    # Atributos
    atributo1 = ""
    atributo2 = 0

    # Constructor
    def __init__(self, param1, param2):
        self.atributo1 = param1
        self.atributo2 = param2
```

**Ejemplo simple:**

```python
class Alumno:
    nombre = ""
    edad = 0

    def __init__(self, n, e):
        self.nombre = n
        self.edad = e
```

### 1.2 ¿Qué es un Objeto?

Un objeto es una instancia específica de una clase. Es la materialización del molde.

**Crear objetos:**

```python
# Crear objeto alumno1
alumno1 = Alumno("Juan", 20)

# Crear objeto alumno2
alumno2 = Alumno("María", 22)
```

### 1.3 Constructor `__init__`

Es un método especial que se ejecuta automáticamente al crear un objeto.

**Características:**

- Siempre se llama `__init__`
- El primer parámetro es `self` (referencia al objeto)
- Inicializa los atributos del objeto

**Ejemplo:**

```python
class Producto:
    nombre = ""
    precio = 0.0

    def __init__(self, n, p):
        self.nombre = n
        self.precio = p

# Al crear el objeto, se ejecuta __init__
prod1 = Producto("Laptop", 15000.0)
```

### 1.4 Atributos Públicos

Son accesibles desde cualquier parte del código.

```python
class Carro:
    marca = ""  # Atributo público
    modelo = ""

    def __init__(self, ma, mo):
        self.marca = ma
        self.modelo = mo

# Acceso directo
c1 = Carro("Toyota", "Corolla")
print(c1.marca)  # Imprime: Toyota
c1.marca = "Honda"  # Se puede modificar directamente
```

---

## NIVEL 2: INTERMEDIO

### 2.1 Atributos Privados

Se definen con doble guion bajo `__`. Solo son accesibles dentro de la clase.

**¿Por qué usar atributos privados?**

- Proteger datos sensibles
- Controlar cómo se modifican los datos
- Encapsulamiento (principio de POO)

**Ejemplo:**

```python
class CuentaBancaria:
    titular = ""
    __saldo = 0.0  # Atributo privado

    def __init__(self, t, s):
        self.titular = t
        self.__saldo = s

cuenta = CuentaBancaria("Pedro", 1000.0)
# print(cuenta.__saldo)  # ERROR: no se puede acceder directamente
```

### 2.2 Métodos Getter y Setter

Permiten acceder y modificar atributos privados de forma controlada.

**Getter:** Obtiene el valor del atributo privado
**Setter:** Establece/modifica el valor del atributo privado

```python
class CuentaBancaria:
    titular = ""
    __saldo = 0.0

    def __init__(self, t, s):
        self.titular = t
        self.__saldo = s

    # GETTER
    def getSaldo(self):
        return self.__saldo

    # SETTER
    def setSaldo(self, nuevo_saldo):
        if nuevo_saldo >= 0:  # Validación
            self.__saldo = nuevo_saldo
        else:
            print("El saldo no puede ser negativo")

# Uso correcto
cuenta = CuentaBancaria("Ana", 5000.0)
print(cuenta.getSaldo())  # Imprime: 5000.0
cuenta.setSaldo(7000.0)   # Modifica el saldo
```

### 2.3 Métodos Personalizados

Son funciones dentro de la clase que realizan acciones específicas.

```python
class Libro:
    titulo = ""
    autor = ""
    __codigo = ""

    def __init__(self, t, a):
        self.titulo = t
        self.autor = a

    def setCodigo(self, cod):
        self.__codigo = cod

    def getCodigo(self):
        return self.__codigo

    # Método personalizado para mostrar información
    def mostrar(self):
        print("Título:", self.titulo)
        print("Autor:", self.autor)
        print("Código:", self.__codigo)

# Uso
libro1 = Libro("Don Quijote", "Cervantes")
libro1.setCodigo("LIB001")
libro1.mostrar()
```

### 2.4 Vectores/Listas de Objetos

Almacenar múltiples objetos en una lista.

```python
# Crear lista vacía de tamaño 10
tam = 10
libros = [0] * tam

# Crear objetos
libro1 = Libro("Cien años", "García Márquez")
libro2 = Libro("El túnel", "Sábato")

# Almacenar en la lista
libros[0] = libro1
libros[1] = libro2
cont = 2  # Contador de libros

# Recorrer y mostrar
for i in range(cont):
    libros[i].mostrar()
```

---

## NIVEL 3: AVANZADO

### 3.1 Validación de Datos

Verificar que los datos cumplan con ciertas condiciones antes de procesarlos.

**Ejemplo: Validar fecha (dd/mm/aaaa)**

```python
def validarFecha(self, f):
    # 1. Verificar longitud
    if len(f) != 10:
        return False

    # 2. Verificar formato (separadores /)
    if f[2] != "/" or f[5] != "/":
        return False

    # 3. Verificar que sean números
    for i in range(len(f)):
        if i in (2, 5):  # Saltar las diagonales
            continue
        if not f[i].isdigit():
            return False

    # 4. Extraer día, mes y año
    dia = int(f[0:2])
    mes = int(f[3:5])
    año = int(f[6:10])

    # 5. Validar rangos
    if dia < 1 or dia > 31:
        return False
    if mes < 1 or mes > 12:
        return False
    if año != 2023:
        return False

    return True
```

**Análisis paso a paso:**

```
Entrada: "15/06/2023"
1. len("15/06/2023") = 10 ✓
2. f[2] = '/' y f[5] = '/' ✓
3. Todos los caracteres (excepto /) son dígitos ✓
4. dia=15, mes=06, año=2023
5. 1≤15≤31 ✓, 1≤6≤12 ✓, año=2023 ✓
Resultado: True
```

### 3.2 Búsqueda en Listas

Buscar un objeto en una lista usando una bandera (flag).

**Patrón de búsqueda:**

```python
# Buscar libro por título
print("Introduce el título a buscar:")
buscar = input()
encontrado = False  # Bandera

for i in range(cont):
    if buscar == libros[i].titulo:
        encontrado = True
        print("Libro encontrado:")
        libros[i].mostrar()
        break  # Opcional: salir del ciclo

if encontrado == False:
    print("El libro no existe")
```

**Búsqueda parcial (contiene):**

```python
# Buscar por autor (puede ser parcial)
autor_buscar = input("Introduce el autor: ")
encontrado = False

for i in range(cont):
    autor_completo = libros[i].autor
    if autor_buscar in autor_completo:  # Búsqueda parcial
        print("Encontrado:", libros[i].titulo)
        encontrado = True

if not encontrado:
    print("No se encontró")
```

### 3.3 Relación entre Clases

Usar atributos de una clase en otra clase.

```python
class Prestamo:
    __codigo = ""
    alumno = ""
    titulo = ""  # Relaciona con Libro
    fecha_prestamo = ""
    estado = 0  # 0=prestado, 1=devuelto

    def __init__(self, alu, fp):
        self.alumno = alu
        self.fecha_prestamo = fp

    def setCodigo(self, cod):
        self.__codigo = cod

    def getCodigo(self):
        return self.__codigo

# Registrar préstamo
prestamo1 = Prestamo("Juan Pérez", "15/06/2023")
prestamo1.titulo = libro1.titulo  # Usar atributo de otro objeto
prestamo1.setCodigo(libro1.getCodigo())  # Usar el mismo código
prestamo1.estado = 0  # Libro prestado
```

### 3.4 Modificación y Eliminación

**Modificar atributos:**

```python
# Cambiar nombre de libro
print("Introduce el título actual:")
titulo_actual = input()
encontrado = False

for i in range(cont):
    if titulo_actual == libros[i].titulo:
        print("Introduce el nuevo título:")
        nuevo_titulo = input()
        libros[i].titulo = nuevo_titulo
        encontrado = True
        print("Título modificado")
        break

if not encontrado:
    print("Libro no encontrado")
```

**Eliminación lógica (marcar como vacío):**

```python
# Borrar libro (eliminación lógica)
print("Introduce el título del libro a borrar:")
titulo = input()
encontrado = False

for i in range(cont):
    if titulo == libros[i].titulo:
        libros[i].titulo = " "
        libros[i].autor = " "
        libros[i].setCodigo(" ")
        encontrado = True
        print("Libro borrado")
        break

if not encontrado:
    print("Libro no encontrado")
```

### 3.5 Gestión de Estados

Controlar el estado de un objeto (disponible/ocupado, activo/inactivo, etc.)

```python
class Prestamo:
    estado = 0  # 0=prestado, 1=devuelto

    def mostrar(self):
        if self.estado == 1:
            print("Estado: Devuelto")
        else:
            print("Estado: Prestado")

# Devolver libro
print("Introduce el título del libro:")
titulo = input()
encontrado = False

for i in range(cont_prestamos):
    if titulo == prestamos[i].titulo and prestamos[i].estado == 0:
        prestamos[i].estado = 1  # Cambiar estado
        print("Libro devuelto correctamente")
        encontrado = True
        break

if not encontrado:
    print("No se encontró el préstamo o ya está devuelto")
```

---

## EJERCICIOS PRÁCTICOS

### Ejercicio 1: Nivel Básico

**Crear clase Estudiante**

Escribe el código para una clase `Estudiante` con:

- Atributos: nombre, matricula, carrera
- Constructor que inicialice los 3 atributos
- Método `mostrar()` que imprima todos los datos

**Respuesta esperada:**

```python
class Estudiante:
    nombre = ""
    matricula = ""
    carrera = ""

    def __init__(self, n, m, c):
        self.nombre = n
        self.matricula = m
        self.carrera = c

    def mostrar(self):
        print("Nombre:", self.nombre)
        print("Matrícula:", self.matricula)
        print("Carrera:", self.carrera)
```

### Ejercicio 2: Nivel Intermedio

**Agregar atributos privados**

Modifica la clase Estudiante para:

- Hacer `matricula` privada (`__matricula`)
- Crear `setMatricula()` y `getMatricula()`
- En `setMatricula()`, validar que la matrícula tenga exactamente 8 caracteres

**Respuesta esperada:**

```python
class Estudiante:
    nombre = ""
    __matricula = ""
    carrera = ""

    def __init__(self, n, m, c):
        self.nombre = n
        self.__matricula = m
        self.carrera = c

    def setMatricula(self, m):
        if len(m) == 8:
            self.__matricula = m
        else:
            print("La matrícula debe tener 8 caracteres")

    def getMatricula(self):
        return self.__matricula

    def mostrar(self):
        print("Nombre:", self.nombre)
        print("Matrícula:", self.__matricula)
        print("Carrera:", self.carrera)
```

### Ejercicio 3: Nivel Avanzado

**Sistema de vectores y búsqueda**

Dado un vector de 5 estudiantes ya creados, escribe el código para:

1. Buscar un estudiante por nombre
2. Si existe, cambiar su carrera
3. Usar una bandera `encontrado`

**Respuesta esperada:**

```python
# Vector con 5 estudiantes
estudiantes = [0] * 10
estudiantes[0] = Estudiante("Ana", "20231001", "Ingeniería")
estudiantes[1] = Estudiante("Luis", "20231002", "Medicina")
estudiantes[2] = Estudiante("Carlos", "20231003", "Derecho")
estudiantes[3] = Estudiante("María", "20231004", "Arquitectura")
estudiantes[4] = Estudiante("Pedro", "20231005", "Psicología")
cont = 5

# Buscar y modificar
print("Introduce el nombre del estudiante:")
nombre = input()
encontrado = False

for i in range(cont):
    if nombre == estudiantes[i].nombre:
        print("Introduce la nueva carrera:")
        nueva_carrera = input()
        estudiantes[i].carrera = nueva_carrera
        encontrado = True
        print("Carrera modificada correctamente")
        break

if not encontrado:
    print("Estudiante no encontrado")
```

### Ejercicio 4: Validación de Datos

**Crear método de validación**

Crea un método `validarMatricula(m)` que verifique:

- Longitud de 8 caracteres
- Los primeros 4 deben ser el año (2023 o 2024)
- Los últimos 4 deben ser números del 0001 al 9999

**Respuesta esperada:**

```python
def validarMatricula(self, m):
    # Verificar longitud
    if len(m) != 8:
        return False

    # Verificar que todos sean dígitos
    if not m.isdigit():
        return False

    # Extraer año y número
    año = int(m[0:4])
    numero = int(m[4:8])

    # Validar año
    if año != 2023 and año != 2024:
        return False

    # Validar número
    if numero < 1 or numero > 9999:
        return False

    return True
```

### Ejercicio 5: Dos Clases Relacionadas

**Sistema de Calificaciones**

Crea dos clases:

1. `Materia`: nombre, codigo (privado), creditos
2. `Calificacion`: nombre_alumno, nombre_materia, calificacion, aprobado (0=no, 1=sí)

Escribe el código completo con:

- Constructores
- Getters y setters para códigos/atributos privados
- Método `mostrar()` en ambas clases
- En `Calificacion.mostrar()`, indicar si está aprobado (≥70)

**Respuesta esperada:**

```python
class Materia:
    nombre = ""
    __codigo = ""
    creditos = 0

    def __init__(self, n, cred):
        self.nombre = n
        self.creditos = cred

    def setCodigo(self, cod):
        self.__codigo = cod

    def getCodigo(self):
        return self.__codigo

    def mostrar(self):
        print("Materia:", self.nombre)
        print("Código:", self.__codigo)
        print("Créditos:", self.creditos)

class Calificacion:
    nombre_alumno = ""
    nombre_materia = ""
    calificacion = 0.0
    aprobado = 0

    def __init__(self, alum, mat, cal):
        self.nombre_alumno = alum
        self.nombre_materia = mat
        self.calificacion = cal
        if cal >= 70:
            self.aprobado = 1
        else:
            self.aprobado = 0

    def mostrar(self):
        print("Alumno:", self.nombre_alumno)
        print("Materia:", self.nombre_materia)
        print("Calificación:", self.calificacion)
        if self.aprobado == 1:
            print("Estado: Aprobado")
        else:
            print("Estado: Reprobado")
```

---

## PREGUNTAS DE EXAMEN

### Sección A: Preguntas Teóricas (Respuesta Corta)

1. **¿Qué es una clase en programación orientada a objetos?**

   - Respuesta: Es una plantilla o molde que define atributos y métodos para crear objetos.

2. **¿Cuál es la diferencia entre un atributo público y uno privado?**

   - Respuesta: Un atributo público es accesible desde cualquier parte del código, mientras que uno privado (con `__`) solo es accesible dentro de la clase.

3. **¿Para qué sirven los métodos getter y setter?**

   - Respuesta: Para acceder y modificar atributos privados de forma controlada y segura.

4. **¿Qué hace el método `__init__` en Python?**

   - Respuesta: Es el constructor que inicializa los atributos de un objeto cuando se crea.

5. **¿Qué es una "bandera" o "flag" en programación?**
   - Respuesta: Es una variable booleana que indica si se cumplió una condición (ej: encontrado = True/False).

### Sección B: Completar Código

**Pregunta 6:** Completa el siguiente código para crear una clase Producto:

```python
class Producto:
    nombre = ""
    __precio = 0.0
    stock = 0

    def __init__(self, n, p, s):
        # COMPLETA AQUÍ

    def setPrecio(self, p):
        # COMPLETA AQUÍ

    def getPrecio(self):
        # COMPLETA AQUÍ
```

**Respuesta:**

```python
def __init__(self, n, p, s):
    self.nombre = n
    self.__precio = p
    self.stock = s

def setPrecio(self, p):
    if p >= 0:
        self.__precio = p

def getPrecio(self):
    return self.__precio
```

**Pregunta 7:** ¿Qué imprime el siguiente código?

```python
class Carro:
    marca = ""

    def __init__(self, m):
        self.marca = m

c1 = Carro("Toyota")
c2 = Carro("Honda")
c1.marca = "Mazda"

print(c1.marca)
print(c2.marca)
```

**Respuesta:**

```
Mazda
Honda
```

### Sección C: Análisis de Código

**Pregunta 8:** Encuentra y explica el error en este código:

```python
class Libro:
    titulo = ""
    __codigo = ""

    def __init__(self, t, c):
        self.titulo = t
        self.__codigo = c

libro1 = Libro("Harry Potter", "LIB123")
print(libro1.__codigo)  # ¿Qué pasa aquí?
```

**Respuesta:** Error: No se puede acceder directamente a `__codigo` porque es un atributo privado. Se debe usar un método getter como `getCodigo()`.

**Pregunta 9:** ¿Qué hace este bucle?

```python
encontrado = False
for i in range(cont):
    if nombre == estudiantes[i].nombre:
        estudiantes[i].mostrar()
        encontrado = True

if not encontrado:
    print("No encontrado")
```

**Respuesta:** Busca un estudiante por nombre en el vector. Si lo encuentra, muestra sus datos y marca la bandera como True. Si termina el bucle sin encontrarlo, imprime "No encontrado".

### Sección D: Ejercicios Prácticos (Escritura de Código)

**Pregunta 10:** Escribe una clase `Empleado` con:

- Atributos: nombre, \_\_salario (privado), departamento
- Constructor que inicialice los 3 atributos
- getSalario() y setSalario() con validación (salario debe ser > 0)
- aumentarSalario(porcentaje) que aumente el salario en un porcentaje dado
- mostrar() que imprima todos los datos

**Pregunta 11:** Dado un vector de 10 empleados, escribe el código para:

1. Buscar un empleado por nombre
2. Si existe y su salario es menor a 10000, aumentarlo en 15%
3. Mostrar un mensaje si no se encontró

**Pregunta 12:** Crea un método `validarNombreCompleto(nombre)` que verifique:

- Debe tener al menos un espacio (nombre y apellido)
- Cada palabra debe empezar con mayúscula
- Solo puede contener letras y espacios
- Debe tener entre 5 y 50 caracteres

### Sección E: Preguntas de Razonamiento

**Pregunta 13:** Explica la diferencia entre estos dos códigos:

```python
# Código A
if estudiante.calificacion >= 70:
    estudiante.aprobado = 1
else:
    estudiante.aprobado = 0

# Código B
estudiante.aprobado = 1 if estudiante.calificacion >= 70 else 0
```

**Respuesta:** Ambos hacen lo mismo (asignan 1 si aprobó, 0 si no). El código B usa una expresión condicional ternaria (más compacta), mientras que A usa if-else tradicional (más legible).

**Pregunta 14:** ¿Por qué es mejor usar eliminación lógica que eliminación física en un vector?

**Respuesta:** Eliminación lógica (marcar como vacío) evita reorganizar el vector y perder índices. Eliminación física (eliminar del vector) requiere mover todos los elementos y puede causar errores con los índices.

**Pregunta 15:** Explica qué problema soluciona este código:

```python
for i in range(cont):
    if vec[i].titulo != " ":  # Verifica que no esté "borrado"
        vec[i].mostrar()
```

**Respuesta:** Evita mostrar elementos que fueron eliminados lógicamente (marcados con " "). Solo muestra los objetos válidos.

---

## CONSEJOS PARA EL EXAMEN

### ✅ Checklist antes de entregar

1. **Sintaxis de clases:**

   - ¿Usé `class NombreClase:`?
   - ¿Definí `__init__(self, ...)`?
   - ¿Todos los métodos tienen `self` como primer parámetro?

2. **Atributos privados:**

   - ¿Usé `__` para atributos privados?
   - ¿Creé getter y setter correspondientes?
   - ¿Incluí validaciones en los setters?

3. **Búsquedas:**

   - ¿Usé una bandera `encontrado = False`?
   - ¿Cambié la bandera a `True` cuando encontré el elemento?
   - ¿Verifiqué la bandera después del bucle?

4. **Validaciones:**

   - ¿Verifiqué longitud de cadenas?
   - ¿Validé rangos numéricos?
   - ¿Manejé casos especiales (cadenas vacías, números negativos)?

5. **Vectores:**
   - ¿Inicialicé el vector con tamaño suficiente?
   - ¿Usé un contador para saber cuántos elementos hay?
   - ¿Recorrí solo hasta `cont`, no hasta `tam`?

### 📝 Patrones Comunes

**Patrón 1: Crear y agregar objeto**

```python
if cont < tam:
    obj = Clase(param1, param2)
    obj.setAtributoPrivado(valor)
    vector[cont] = obj
    cont = cont + 1
else:
    print("No hay espacio")
```

**Patrón 2: Buscar y modificar**

```python
nombre = input()
encontrado = False
for i in range(cont):
    if nombre == vector[i].atributo:
        # Modificar aquí
        vector[i].atributo = nuevo_valor
        encontrado = True
        break
if not encontrado:
    print("No encontrado")
```

**Patrón 3: Validar entrada**

```python
valor = input()
while not validar(valor):
    print("Inválido. Intenta de nuevo:")
    valor = input()
# Usar valor validado
```

### 🎯 Errores Comunes a Evitar

1. ❌ Olvidar `self` en métodos
2. ❌ Acceder directamente a atributos privados fuera de la clase
3. ❌ No inicializar la bandera antes del bucle
4. ❌ Recorrer el vector hasta `tam` en vez de `cont`
5. ❌ Olvidar incrementar el contador después de agregar
6. ❌ No validar entradas del usuario
7. ❌ Confundir `=` (asignación) con `==` (comparación)
8. ❌ No usar `break` cuando ya encontraste lo que buscabas

---

## MINI EXAMEN DE PRÁCTICA

### Tiempo estimado: 45 minutos

**Instrucciones:** Resuelve los siguientes ejercicios en papel, como si estuvieras en un examen real.

**Ejercicio 1 (20 puntos):** Crea una clase `Vehiculo` con:

- Atributos: marca, modelo, \_\_placa (privado), año
- Constructor
- setPlaca() que valide que la placa tenga exactamente 7 caracteres
- getPlaca()
- mostrar() que imprima todos los datos

**Ejercicio 2 (30 puntos):** Dado un vector de 10 vehículos con 4 ya creados (cont=4):

- Escribe el código para agregar un nuevo vehículo pidiendo datos al usuario
- Incluye validación de placa usando el método del Ejercicio 1
- Verifica que haya espacio antes de agregar

**Ejercicio 3 (30 puntos):** Usando el mismo vector del Ejercicio 2:

- Escribe código para buscar un vehículo por marca
- Si existe, mostrar todos los vehículos de esa marca
- Usa una bandera para verificar si se encontró al menos uno
- Si no existe ninguno, mostrar mensaje apropiado

**Ejercicio 4 (20 puntos):** Crea un método `validarAño(año)` que verifique:

- Debe ser un número de 4 dígitos
- Debe estar entre 1900 y 2024
- Retorna True si es válido, False si no

---

## SOLUCIONES DEL MINI EXAMEN

### Solución Ejercicio 1:

```python
class Vehiculo:
    marca = ""
    modelo = ""
    __placa = ""
    año = 0

    def __init__(self, ma, mo, a):
        self.marca = ma
        self.modelo = mo
        self.año = a

    def setPlaca(self, p):
        if len(p) == 7:
            self.__placa = p
        else:
            print("La placa debe tener 7 caracteres")

    def getPlaca(self):
        return self.__placa

    def mostrar(self):
        print("Marca:", self.marca)
        print("Modelo:", self.modelo)
        print("Placa:", self.__placa)
        print("Año:", self.año)
```

### Solución Ejercicio 2:

```python
tam = 10
vehiculos = [0] * tam
cont = 4  # Ya hay 4 vehículos

if cont < tam:
    print("Introduce la marca:")
    ma = input()
    print("Introduce el modelo:")
    mo = input()
    print("Introduce el año:")
    a = int(input())

    v = Vehiculo(ma, mo, a)

    print("Introduce la placa (7 caracteres):")
    placa = input()
    while len(placa) != 7:
        print("Placa inválida. Debe tener 7 caracteres:")
        placa = input()

    v.setPlaca(placa)
    vehiculos[cont] = v
    cont = cont + 1
    print("Vehículo agregado correctamente")
else:
    print("No hay espacio para más vehículos")
```

### Solución Ejercicio 3:

```python
print("Introduce la marca a buscar:")
marca_buscar = input()
encontrado = False

for i in range(cont):
    if marca_buscar == vehiculos[i].marca:
        print("Vehículo encontrado:")
        vehiculos[i].mostrar()
        encontrado = True

if not encontrado:
    print("No se encontraron vehículos de esa marca")
```

### Solución Ejercicio 4:

```python
def validarAño(self, año):
    # Convertir a string para verificar longitud
    año_str = str(año)

    # Verificar que tenga 4 dígitos
    if len(año_str) != 4:
        return False

    # Verificar que sea número
    if not año_str.isdigit():
        return False

    # Verificar rango
    if año < 1900 or año > 2024:
        return False

    return True
```

---

## TABLA DE CONCEPTOS CLAVE

| Concepto         | Definición                   | Ejemplo               |
| ---------------- | ---------------------------- | --------------------- |
| Clase            | Molde para crear objetos     | `class Libro:`        |
| Objeto           | Instancia de una clase       | `libro1 = Libro(...)` |
| Atributo         | Característica de un objeto  | `titulo`, `autor`     |
| Método           | Función dentro de una clase  | `def mostrar(self):`  |
| Constructor      | Inicializa el objeto         | `__init__(self, ...)` |
| Atributo privado | Solo accesible en la clase   | `__codigo`            |
| Getter           | Obtiene atributo privado     | `getCodigo()`         |
| Setter           | Modifica atributo privado    | `setCodigo(cod)`      |
| self             | Referencia al objeto actual  | `self.titulo = t`     |
| Bandera/Flag     | Variable booleana de control | `encontrado = False`  |

---

## RECURSOS ADICIONALES

### Ejercicios Extra para Practicar

1. **Sistema de Películas:** Crea clases Película y Renta similar al sistema de Libros
2. **Agenda de Contactos:** Clase Contacto con nombre, teléfono privado, email
3. **Inventario de Productos:** Gestionar stock, precios, validar cantidades
4. **Sistema Escolar:** Relacionar clases Alumno, Materia y Calificacion
5. **Biblioteca Digital:** Agregar atributo tipo (físico/digital) y validaciones específicas

### Preguntas de Reflexión

1. ¿Por qué es importante la encapsulación (atributos privados)?
2. ¿Cuándo usarías eliminación lógica vs física?
3. ¿Qué ventajas tiene validar datos antes de guardarlos?
4. ¿Cómo relacionarías 3 clases diferentes? (ej: Alumno, Materia, Inscripción)

---

**¡Buena suerte en tu examen!** 🎓

Recuerda: La práctica hace al maestro. Intenta resolver los ejercicios sin mirar las soluciones primero.
