# ✅ RESPUESTAS - EJERCICIOS DE PROGRAMACIÓN ORIENTADA A OBJETOS

---

## NIVEL 1: CONCEPTOS BÁSICOS

### Ejercicio 1: Tu Primera Clase
```python
class Persona:
    nombre = ""
    edad = 0
    ciudad = ""
    
    def __init__(self, n, e, c):
        self.nombre = n
        self.edad = e
        self.ciudad = c
```

**Explicación:**
- Definimos tres atributos públicos
- El constructor `__init__` recibe tres parámetros (además de self)
- Asignamos cada parámetro al atributo correspondiente usando `self.`

---

### Ejercicio 2: Crear Objetos
```python
persona1 = Persona("Juan", 25, "Monterrey")
persona2 = Persona("María", 30, "Guadalajara")
persona3 = Persona("Carlos", 22, "CDMX")
```

**Explicación:**
- Creamos tres instancias de la clase Persona
- Cada objeto tiene sus propios valores para los atributos
- Los valores se pasan en el orden definido en el constructor

---

### Ejercicio 3: Método Mostrar
```python
class Persona:
    nombre = ""
    edad = 0
    ciudad = ""
    
    def __init__(self, n, e, c):
        self.nombre = n
        self.edad = e
        self.ciudad = c
    
    def mostrar(self):
        print("Nombre:", self.nombre)
        print("Edad:", self.edad)
        print("Ciudad:", self.ciudad)
```

**Explicación:**
- El método `mostrar()` requiere `self` como parámetro
- Accedemos a los atributos usando `self.atributo`
- `print()` muestra cada atributo en una línea

---

### Ejercicio 4: Acceso a Atributos
```python
# 1. Imprimir la marca
print(c1.marca)  # Imprime: Toyota

# 2. Cambiar el año
c1.año = 2021

# 3. Imprimir el nuevo año
print(c1.año)  # Imprime: 2021
```

**Explicación:**
- Accedemos a atributos públicos usando `objeto.atributo`
- Podemos modificar atributos públicos directamente
- La sintaxis es: `objeto.atributo = nuevo_valor`

---

### Ejercicio 5: Vector Simple
```python
tam = 5
carros = [0] * tam
cont = 0

# Agregar carros
c1 = Carro("Honda", "Civic", 2019)
c2 = Carro("Mazda", "3", 2022)

carros[0] = c1
carros[1] = c2
cont = 2

# Mostrar
for i in range(cont):
    print("Marca:", carros[i].marca)
    print("Modelo:", carros[i].modelo)
    print("Año:", carros[i].año)
    print("---")
```

**Explicación:**
- Creamos un vector de tamaño 5 inicializado con 0
- Agregamos objetos en posiciones específicas
- Usamos un contador para saber cuántos elementos válidos hay
- Recorremos solo hasta `cont`, no hasta `tam`

---

## NIVEL 2: ATRIBUTOS PRIVADOS Y ENCAPSULAMIENTO

### Ejercicio 6: Primer Atributo Privado
```python
class CuentaBancaria:
    titular = ""
    __saldo = 0.0
    
    def __init__(self, t, s):
        self.titular = t
        self.__saldo = s
```

**Explicación:**
- El doble guion bajo `__` hace que `saldo` sea privado
- Solo es accesible dentro de la clase
- El constructor lo inicializa igual que atributos públicos

---

### Ejercicio 7: Getter y Setter
```python
class CuentaBancaria:
    titular = ""
    __saldo = 0.0
    
    def __init__(self, t, s):
        self.titular = t
        self.__saldo = s
    
    def getSaldo(self):
        return self.__saldo
    
    def setSaldo(self, nuevo_saldo):
        if nuevo_saldo >= 0:
            self.__saldo = nuevo_saldo
        else:
            print("El saldo no puede ser negativo")
```

**Explicación:**
- `getSaldo()` retorna el valor del atributo privado
- `setSaldo()` incluye validación antes de modificar
- Esto protege el dato de valores inválidos

---

### Ejercicio 8: Clase Producto Completa
```python
class Producto:
    nombre = ""
    __precio = 0.0
    stock = 0
    
    def __init__(self, n, p, s):
        self.nombre = n
        self.__precio = p
        self.stock = s
    
    def getPrecio(self):
        return self.__precio
    
    def setPrecio(self, p):
        if p >= 0:
            self.__precio = p
        else:
            print("El precio no puede ser negativo")
    
    def mostrar(self):
        print("Nombre:", self.nombre)
        print("Precio:", self.__precio)
        print("Stock:", self.stock)
```

**Explicación:**
- Clase completa con atributo privado y métodos de acceso
- El constructor inicializa todos los atributos
- Validación en el setter protege la integridad de los datos

---

### Ejercicio 9: Método de Negocio
```python
def vender(self, cantidad):
    if self.stock >= cantidad:
        self.stock = self.stock - cantidad
        print("Venta realizada. Stock restante:", self.stock)
    else:
        print("Stock insuficiente")
```

**Explicación:**
- Verificamos que hay suficiente stock antes de vender
- Solo restamos si la condición se cumple
- Mostramos mensajes apropiados en cada caso

---

### Ejercicio 10: Uso Completo
```python
# 1. Crear producto
p1 = Producto("Laptop", 15000, 10)

# 2. Vender 3 unidades
p1.vender(3)  # Stock queda en 7

# 3. Mostrar datos
p1.mostrar()

# 4. Vender 8 unidades
p1.vender(8)  # Imprime "Stock insuficiente" porque solo hay 7
```

**Explicación:**
- Primero vendemos 3, quedan 7 unidades
- Al intentar vender 8, la validación previene el error
- El stock nunca puede ser negativo gracias a la validación

---

## NIVEL 3: VALIDACIONES

### Ejercicio 11: Validar Teléfono
```python
class Contacto:
    nombre = ""
    __telefono = ""
    
    def validarTelefono(self, tel):
        # Verificar longitud
        if len(tel) != 10:
            return False
        
        # Verificar que todos sean dígitos
        if not tel.isdigit():
            return False
        
        return True
```

**Explicación:**
- `len(tel)` verifica que tenga exactamente 10 caracteres
- `isdigit()` verifica que todos sean números
- Si pasa ambas validaciones, retorna True

---

### Ejercicio 12: Validar Email
```python
def validarEmail(self, email):
    # Verificar longitud mínima
    if len(email) < 5:
        return False
    
    # Contar cantidad de @
    contador_arroba = 0
    for c in email:
        if c == '@':
            contador_arroba = contador_arroba + 1
    
    if contador_arroba != 1:
        return False
    
    # Buscar @ y verificar que hay punto después
    posicion_arroba = email.find('@')
    parte_despues = email[posicion_arroba:]
    
    if '.' not in parte_despues:
        return False
    
    return True
```

**Explicación:**
- Validamos longitud mínima de 5 caracteres
- Contamos @ manualmente (debe haber exactamente 1)
- Verificamos que hay un punto después del @
- Usamos slicing `[posicion_arroba:]` para obtener la parte después del @

---

### Ejercicio 13: Validar Fecha Completa
```python
def validarFecha(self, fecha):
    # 1. Verificar longitud
    if len(fecha) != 10:
        return False
    
    # 2. Verificar separadores
    if fecha[2] != "/" or fecha[5] != "/":
        return False
    
    # 3. Verificar que sean números (excepto /)
    for i in range(len(fecha)):
        if i in (2, 5):
            continue
        if not fecha[i].isdigit():
            return False
    
    # 4. Extraer y convertir día, mes, año
    dia = int(fecha[0:2])
    mes = int(fecha[3:5])
    año = int(fecha[6:10])
    
    # 5. Validar rangos
    if dia < 1 or dia > 31:
        return False
    if mes < 1 or mes > 12:
        return False
    if año < 2020 or año > 2025:
        return False
    
    return True
```

**Explicación:**
- Validación paso a paso de cada requisito
- Usamos slicing para extraer día, mes y año
- `continue` salta las posiciones de las diagonales
- Validamos que cada parte esté en su rango válido

---

### Ejercicio 14: Usar Validación en Constructor
```python
class Evento:
    nombre = ""
    __fecha = ""
    lugar = ""
    
    def validarFecha(self, fecha):
        if len(fecha) != 10:
            return False
        if fecha[2] != "/" or fecha[5] != "/":
            return False
        for i in range(len(fecha)):
            if i in (2, 5):
                continue
            if not fecha[i].isdigit():
                return False
        dia = int(fecha[0:2])
        mes = int(fecha[3:5])
        año = int(fecha[6:10])
        if dia < 1 or dia > 31:
            return False
        if mes < 1 or mes > 12:
            return False
        if año < 2020 or año > 2025:
            return False
        return True
    
    def __init__(self, n, f, l):
        self.nombre = n
        self.lugar = l
        
        if self.validarFecha(f):
            self.__fecha = f
        else:
            self.__fecha = "01/01/2023"
            print("Fecha inválida. Se asignó fecha por defecto.")
```

**Explicación:**
- El constructor llama al método de validación
- Si la fecha es válida, la asigna
- Si no es válida, usa un valor por defecto
- Esto garantiza que nunca tengamos fechas inválidas

---

## NIVEL 4: BÚSQUEDA Y BANDERAS

### Ejercicio 15: Búsqueda Simple
```python
print("Introduce el nombre a buscar:")
nombre_buscar = input()
encontrado = False

for i in range(cont):
    if nombre_buscar == estudiantes[i].nombre:
        encontrado = True
        break

if encontrado:
    print("Estudiante encontrado")
else:
    print("Estudiante no encontrado")
```

**Explicación:**
- Inicializamos la bandera en False
- Recorremos el vector comparando nombres
- Si encontramos coincidencia, cambiamos la bandera a True y salimos
- Después del bucle, verificamos la bandera para mostrar el mensaje

---

### Ejercicio 16: Búsqueda y Mostrar
```python
print("Introduce el nombre a buscar:")
nombre_buscar = input()
encontrado = False

for i in range(cont):
    if nombre_buscar == estudiantes[i].nombre:
        print("Estudiante encontrado:")
        estudiantes[i].mostrar()
        encontrado = True
        break

if not encontrado:
    print("Estudiante no encontrado")
```

**Explicación:**
- Similar al ejercicio anterior
- Cuando encontramos el estudiante, llamamos a su método `mostrar()`
- Esto imprime todos sus datos automáticamente
- Usamos `not encontrado` en lugar de `encontrado == False`

---

### Ejercicio 17: Búsqueda Múltiple
```python
print("Introduce la ciudad a buscar:")
ciudad_buscar = input()
encontrado = False

for i in range(cont):
    if ciudad_buscar == estudiantes[i].ciudad:
        print("Estudiante encontrado:")
        estudiantes[i].mostrar()
        print("---")
        encontrado = True

if not encontrado:
    print("No se encontraron estudiantes de esa ciudad")
```

**Explicación:**
- No usamos `break` porque queremos encontrar TODOS
- Cambiamos la bandera a True cada vez que encontramos uno
- El bucle continúa hasta el final
- La bandera indica si se encontró AL MENOS uno

---

## NIVEL 5: MODIFICACIÓN Y ELIMINACIÓN

### Ejercicio 18: Modificar Atributo
```python
print("Introduce el título del libro:")
titulo_buscar = input()
encontrado = False

for i in range(cont):
    if titulo_buscar == libros[i].titulo:
        print("Introduce la nueva editorial:")
        nueva_editorial = input()
        libros[i].editorial = nueva_editorial
        print("Editorial modificada correctamente")
        encontrado = True
        break

if not encontrado:
    print("Libro no encontrado")
```

**Explicación:**
- Buscamos el libro por título
- Si lo encontramos, pedimos el nuevo valor
- Asignamos el nuevo valor directamente al atributo
- Mostramos confirmación y salimos del bucle

---

### Ejercicio 19: Eliminación Lógica
```python
print("Introduce el título del libro a eliminar:")
titulo = input()
encontrado = False

for i in range(cont):
    if titulo == libros[i].titulo:
        libros[i].titulo = " "
        libros[i].autor = " "
        libros[i].setCodigo(" ")
        encontrado = True
        print("Libro eliminado")
        break

if not encontrado:
    print("Libro no encontrado")
```

**Explicación:**
- Eliminación lógica = marcar como vacío, no eliminar físicamente
- Marcamos todos los atributos con " " (un espacio)
- El objeto sigue en el vector pero marcado como "eliminado"
- No reorganizamos el vector ni cambiamos el contador

---

### Ejercicio 20: Mostrar Solo Válidos
```python
print("Lista de libros:")
for i in range(cont):
    if libros[i].titulo != " ":
        libros[i].mostrar()
        print("---")
```

**Explicación:**
- Recorremos todo el vector
- Verificamos que el título NO sea " " (no esté eliminado)
- Solo mostramos los objetos válidos
- Esto filtra los libros eliminados lógicamente

---

## NIVEL 6: SISTEMAS COMPLETOS

### Ejercicio 21: Agregar con Validación
```python
if cont < tam:
    print("Introduce el título:")
    titulo = input()
    print("Introduce el autor:")
    autor = input()
    print("Introduce la editorial:")
    editorial = input()
    print("Introduce la edición:")
    edicion = input()
    
    print("Introduce el código (4 dígitos):")
    codigo = input()
    while len(codigo) != 4 or not codigo.isdigit():
        print("Código inválido. Debe tener 4 dígitos:")
        codigo = input()
    
    # Crear objeto
    libro = Libro(titulo, autor, editorial, edicion)
    libro.setCodigo(codigo)
    
    # Agregar al vector
    libros[cont] = libro
    cont = cont + 1
    
    print("Libro agregado correctamente")
else:
    print("No hay espacio para más libros")
```

**Explicación:**
- Verificamos espacio antes de pedir datos
- Pedimos todos los datos al usuario
- Validamos el código en un bucle while
- Creamos el objeto, lo configuramos y lo agregamos
- Incrementamos el contador (¡MUY IMPORTANTE!)

---

### Ejercicio 22: Menú Básico
```python
opc = 0
while opc != 3:
    print("--- MENÚ ---")
    print("1) Agregar libro")
    print("2) Mostrar libros")
    print("3) Salir")
    print("Introduce la opción:")
    opc = int(input())
    
    if opc == 1:
        # Código del ejercicio 21
        if cont < tam:
            print("Introduce el título:")
            titulo = input()
            print("Introduce el autor:")
            autor = input()
            print("Introduce la editorial:")
            editorial = input()
            print("Introduce la edición:")
            edicion = input()
            
            print("Introduce el código (4 dígitos):")
            codigo = input()
            while len(codigo) != 4 or not codigo.isdigit():
                print("Código inválido. Debe tener 4 dígitos:")
                codigo = input()
            
            libro = Libro(titulo, autor, editorial, edicion)
            libro.setCodigo(codigo)
            libros[cont] = libro
            cont = cont + 1
            print("Libro agregado correctamente")
        else:
            print("No hay espacio para más libros")
```

**Explicación:**
- Bucle while que se ejecuta mientras opc != 3
- Mostramos el menú en cada iteración
- Usamos if para cada opción
- La opción 1 ejecuta el código completo del ejercicio 21

---

### Ejercicio 23: Sistema de Préstamos
```python
class Prestamo:
    nombre_alumno = ""
    titulo_libro = ""
    __codigo_libro = ""
    fecha_prestamo = ""
    estado = 0  # 0 = prestado, 1 = devuelto
    
    def __init__(self, na, tl, fp):
        self.nombre_alumno = na
        self.titulo_libro = tl
        self.fecha_prestamo = fp
        self.estado = 0
    
    def getCodigo(self):
        return self.__codigo_libro
    
    def setCodigo(self, cod):
        self.__codigo_libro = cod
    
    def mostrar(self):
        print("Alumno:", self.nombre_alumno)
        print("Libro:", self.titulo_libro)
        print("Código:", self.__codigo_libro)
        print("Fecha préstamo:", self.fecha_prestamo)
        if self.estado == 0:
            print("Estado: Prestado")
        else:
            print("Estado: Devuelto")
```

**Explicación:**
- Clase completa para manejar préstamos
- Estado inicializado en 0 (prestado) en el constructor
- Método mostrar() imprime el estado en texto legible
- Atributo código privado con sus métodos de acceso

---

### Ejercicio 24: Registrar Préstamo Completo
```python
print("Nombre del alumno:")
nombre_alumno = input()

print("Fecha de préstamo (dd/mm/aaaa):")
fecha = input()

print("Título del libro a prestar:")
titulo_buscar = input()

encontrado = False
for i in range(cont):
    if titulo_buscar == libros[i].titulo:
        # Libro encontrado
        prestamo = Prestamo(nombre_alumno, titulo_buscar, fecha)
        prestamo.setCodigo(libros[i].getCodigo())
        
        prestamos[cont2] = prestamo
        cont2 = cont2 + 1
        
        print("Préstamo registrado correctamente")
        encontrado = True
        break

if not encontrado:
    print("Libro no encontrado")
```

**Explicación:**
- Pedimos todos los datos necesarios
- Buscamos el libro en el vector de libros
- Si existe, creamos un objeto Prestamo
- Copiamos el código del libro al préstamo
- Agregamos al vector de préstamos e incrementamos cont2
- Usamos dos vectores independientes: libros y prestamos

---

## NIVEL 7: DESAFÍOS AVANZADOS

### Ejercicio 25: Método de Modificación Interactivo
```python
def modificarFecha(self):
    print("Fecha actual:", self.fecha_prestamo)
    print("Introduce la nueva fecha (dd/mm/aaaa):")
    nueva_fecha = input()
    
    while not self.validarFecha(nueva_fecha):
        print("Fecha inválida. Intenta de nuevo (dd/mm/aaaa):")
        nueva_fecha = input()
    
    self.fecha_prestamo = nueva_fecha
    print("Fecha actualizada correctamente")
```

**Explicación:**
- Mostramos la fecha actual primero
- Pedimos nueva fecha y validamos
- Mientras sea inválida, seguimos pidiendo
- Solo salimos del while cuando la fecha es válida
- Actualizamos y confirmamos

---

### Ejercicio 26: Devolver Libro
```python
print("Introduce el título del libro:")
titulo = input()
encontrado = False

for i in range(cont2):
    if titulo == prestamos[i].titulo_libro and prestamos[i].estado == 0:
        prestamos[i].estado = 1
        print("Libro devuelto correctamente")
        encontrado = True
        break

if not encontrado:
    print("No se encontró el préstamo o ya está devuelto")
```

**Explicación:**
- Buscamos en el vector de préstamos
- Verificamos DOS condiciones: título coincide Y estado = 0
- Solo cambiamos el estado si ambas se cumplen
- Esto evita "devolver" un libro ya devuelto
- El mensaje final cubre ambos casos de error

---

### Ejercicio 27: Sistema Completo Integrado
```python
class Libro:
    titulo = ""
    autor = ""
    __codigo = ""
    editorial = ""
    edicion = ""
    
    def __init__(self, t, a, ed, edc):
        self.titulo = t
        self.autor = a
        self.editorial = ed
        self.edicion = edc
    
    def setCodigo(self, cod):
        self.__codigo = cod
    
    def getCodigo(self):
        return self.__codigo
    
    def mostrar(self):
        print("Título:", self.titulo)
        print("Autor:", self.autor)
        print("Código:", self.__codigo)
        print("Editorial:", self.editorial)
        print("Edición:", self.edicion)


class Prestamo:
    nombre_alumno = ""
    titulo_libro = ""
    __codigo_libro = ""
    fecha_prestamo = ""
    estado = 0
    
    def __init__(self, na, tl, fp):
        self.nombre_alumno = na
        self.titulo_libro = tl
        self.fecha_prestamo = fp
        self.estado = 0
    
    def getCodigo(self):
        return self.__codigo_libro
    
    def setCodigo(self, cod):
        self.__codigo_libro = cod
    
    def mostrar(self):
        print("Alumno:", self.nombre_alumno)
        print("Libro:", self.titulo_libro)
        print("Código:", self.__codigo_libro)
        print("Fecha:", self.fecha_prestamo)
        if self.estado == 0:
            print("Estado: Prestado")
        else:
            print("Estado: Devuelto")


# Inicializar vectores
tam = 20
libros = [0] * tam
prestamos = [0] * tam

# Cargar libros iniciales
l1 = Libro("Don Quijote", "Cervantes", "Planeta", "1a")
l1.setCodigo("LIB1")
l2 = Libro("Cien Años", "García Márquez", "Sudamericana", "2a")
l2.setCodigo("LIB2")
l3 = Libro("El Túnel", "Sábato", "Seix Barral", "3a")
l3.setCodigo("LIB3")

libros[0] = l1
libros[1] = l2
libros[2] = l3
cont = 3
cont2 = 0

# Menú principal
opc = 0
while opc != 6:
    print("\n--- SISTEMA DE BIBLIOTECA ---")
    print("1) Agregar libro")
    print("2) Mostrar libros")
    print("3) Registrar préstamo")
    print("4) Mostrar préstamos")
    print("5) Devolver libro")
    print("6) Salir")
    print("Opción:")
    opc = int(input())
    
    # Opción 1: Agregar libro
    if opc == 1:
        if cont < tam:
            print("Título:")
            titulo = input()
            print("Autor:")
            autor = input()
            print("Editorial:")
            editorial = input()
            print("Edición:")
            edicion = input()
            print("Código (4 dígitos):")
            codigo = input()
            while len(codigo) != 4 or not codigo.isdigit():
                print("Inválido. Código (4 dígitos):")
                codigo = input()
            
            libro = Libro(titulo, autor, editorial, edicion)
            libro.setCodigo(codigo)
            libros[cont] = libro
            cont = cont + 1
            print("✓ Libro agregado")
        else:
            print("✗ No hay espacio")
    
    # Opción 2: Mostrar libros
    elif opc == 2:
        print("\n--- LIBROS REGISTRADOS ---")
        for i in range(cont):
            libros[i].mostrar()
            print("---")
    
    # Opción 3: Registrar préstamo
    elif opc == 3:
        print("Nombre del alumno:")
        alumno = input()
        print("Fecha (dd/mm/aaaa):")
        fecha = input()
        # Aquí se podría validar la fecha
        print("Título del libro:")
        titulo_p = input()
        
        encontrado = False
        for i in range(cont):
            if titulo_p == libros[i].titulo:
                p = Prestamo(alumno, titulo_p, fecha)
                p.setCodigo(libros[i].getCodigo())
                prestamos[cont2] = p
                cont2 = cont2 + 1
                print("✓ Préstamo registrado")
                encontrado = True
                break
        
        if not encontrado:
            print("✗ Libro no encontrado")
    
    # Opción 4: Mostrar préstamos
    elif opc == 4:
        print("\n--- PRÉSTAMOS REGISTRADOS ---")
        if cont2 == 0:
            print("No hay préstamos")
        else:
            for i in range(cont2):
                prestamos[i].mostrar()
                print("---")
    
    # Opción 5: Devolver libro
    elif opc == 5:
        print("Título del libro a devolver:")
        titulo_d = input()
        encontrado = False
        
        for i in range(cont2):
            if titulo_d == prestamos[i].titulo_libro and prestamos[i].estado == 0:
                prestamos[i].estado = 1
                print("✓ Libro devuelto")
                encontrado = True
                break
        
        if not encontrado:
            print("✗ Préstamo no encontrado o ya devuelto")

print("¡Hasta luego!")
```

**Explicación:**
- Sistema completo con dos clases
- Dos vectores independientes con sus contadores
- Menú con 6 opciones funcionales
- Validaciones en agregar libro y registrar préstamo
- Control de estados en devolución
- Mensajes claros con símbolos ✓ y ✗

---

## EJERCICIOS BONUS

### Ejercicio 28: Búsqueda Parcial por Autor
```python
print("Introduce el autor a buscar:")
autor_buscar = input()
encontrado = False

for i in range(cont):
    autor_completo = libros[i].autor
    if autor_buscar in autor_completo:
        print("Libro encontrado:")
        libros[i].mostrar()
        print("---")
        encontrado = True

if not encontrado:
    print("No se encontraron libros de ese autor")
```

**Explicación:**
- Usamos el operador `in` para búsqueda parcial
- "Juan" in "María Juan López" retorna True
- Guardamos el autor completo en una variable para mayor claridad
- Mostramos todos los libros que coincidan
- No usamos `break` para encontrar todos

---

### Ejercicio 29: Estadísticas
```python
activos = 0
devueltos = 0

for i in range(cont2):
    if prestamos[i].estado == 0:
        activos = activos + 1
    else:
        devueltos = devueltos + 1

print("Préstamos activos:", activos)
print("Préstamos devueltos:", devueltos)
print("Total de préstamos:", cont2)
```

**Explicación:**
- Inicializamos dos contadores en 0
- Recorremos todos los préstamos
- Incrementamos el contador correspondiente según el estado
- Mostramos ambos totales y el total general

---

### Ejercicio 30: Validación de Código Complejo
```python
def validarCodigoLibro(self, cod):
    # Verificar longitud
    if len(cod) != 6:
        return False
    
    # Extraer partes
    letras = cod[0:3]
    numeros = cod[3:6]
    
    # Verificar que primeros 3 son letras mayúsculas
    for c in letras:
        if not c.isupper() or not c.isalpha():
            return False
    
    # Verificar que últimos 3 son números
    if not numeros.isdigit():
        return False
    
    return True
```

**Explicación:**
- Usamos slicing para separar letras y números
- `isupper()` verifica mayúsculas
- `isalpha()` verifica que son letras
- `isdigit()` verifica que son números
- Todos deben cumplirse para retornar True

**Ejemplos de prueba:**
```python
validarCodigoLibro("LIB123")  # True
validarCodigoLibro("lib123")  # False (minúsculas)
validarCodigoLibro("LIBRO1")  # False (longitud incorrecta)
validarCodigoLibro("123ABC")  # False (orden incorrecto)
validarCodigoLibro("LIB12A")  # False (letra en parte numérica)
```

---

## CONCEPTOS CLAVE REPASADOS

| Ejercicios | Concepto Principal |
|------------|-------------------|
| 1-5 | Clases básicas, objetos, vectores |
| 6-10 | Atributos privados, getters, setters |
| 11-14 | Validación de datos |
| 15-17 | Búsqueda con banderas |
| 18-20 | Modificación y eliminación |
| 21-24 | Sistemas integrados |
| 25-27 | Funcionalidades avanzadas |
| 28-30 | Técnicas especiales |

---

## ERRORES COMUNES Y SOLUCIONES

### Error 1: Olvidar `self`
```python
# ❌ Incorrecto
def mostrar():
    print(nombre)

# ✅ Correcto
def mostrar(self):
    print(self.nombre)
```

### Error 2: Acceder a privados directamente
```python
# ❌ Incorrecto
cuenta = CuentaBancaria("Ana", 1000)
print(cuenta.__saldo)  # Error

# ✅ Correcto
print(cuenta.getSaldo())
```

### Error 3: No inicializar bandera
```python
# ❌ Incorrecto (puede dar error)
for i in range(cont):
    if nombre == vec[i].nombre:
        encontrado = True

if encontrado:  # ¿Qué pasa si encontrado no existe?
    print("Encontrado")

# ✅ Correcto
encontrado = False  # Inicializar antes del bucle
for i in range(cont):
    if nombre == vec[i].nombre:
        encontrado = True
```

### Error 4: Olvidar incrementar contador
```python
# ❌ Incorrecto
libro = Libro(...)
libros[cont] = libro
# Falta: cont = cont + 1

# ✅ Correcto
libro = Libro(...)
libros[cont] = libro
cont = cont + 1  # ¡Importante!
```

### Error 5: Recorrer hasta tam en vez de cont
```python
# ❌ Incorrecto
for i in range(tam):  # Recorre espacios vacíos
    libros[i].mostrar()

# ✅ Correcto
for i in range(cont):  # Solo recorre los válidos
    libros[i].mostrar()
```

---

## TABLA DE MÉTODOS ÚTILES DE STRING

| Método | Qué hace | Ejemplo |
|--------|----------|---------|
| `len(s)` | Longitud | `len("hola")` → 4 |
| `s.isdigit()` | ¿Todo números? | `"123".isdigit()` → True |
| `s.isalpha()` | ¿Todo letras? | `"abc".isalpha()` → True |
| `s.isupper()` | ¿Todo mayúsculas? | `"ABC".isupper()` → True |
| `s.islower()` | ¿Todo minúsculas? | `"abc".islower()` → True |
| `"x" in s` | ¿Contiene x? | `"a" in "hola"` → True |
| `s.find(x)` | Posición de x | `"hola".find("l")` → 2 |
| `s[inicio:fin]` | Substring | `"hola"[0:2]` → "ho" |

---

## PATRONES DE CÓDIGO IMPORTANTES

### Patrón 1: Agregar al vector
```python
if cont < tam:
    # Crear objeto
    obj = Clase(...)
    # Configurar
    obj.setAtributo(...)
    # Agregar
    vector[cont] = obj
    cont = cont + 1
else:
    print("Sin espacio")
```

### Patrón 2: Buscar con bandera
```python
encontrado = False
for i in range(cont):
    if condicion:
        # Acción
        encontrado = True
        break
if not encontrado:
    print("No encontrado")
```

### Patrón 3: Validar con while
```python
dato = input()
while not validar(dato):
    print("Inválido:")
    dato = input()
# dato es válido aquí
```

### Patrón 4: Menú básico
```python
opc = 0
while opc != salir:
    print("Menú...")
    opc = int(input())
    if opc == 1:
        # Acción
    elif opc == 2:
        # Acción
```

---

**Fin de las respuestas** ✅

¡Compara tus soluciones con estas! Si hay diferencias, analiza por qué y aprende de ellas. 🎓
