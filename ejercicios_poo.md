# 📝 EJERCICIOS DE PROGRAMACIÓN ORIENTADA A OBJETOS
## Sistema de Biblioteca - De Básico a Avanzado

**Nombre:** ______________________ **Fecha:** ______________________

**Instrucciones:** 
- Resuelve cada ejercicio en orden
- Escribe el código completo y legible
- Presta atención a la sintaxis
- No olvides los métodos `__init__` y `self`

---

## NIVEL 1: CONCEPTOS BÁSICOS (Ejercicios 1-5)

### Ejercicio 1: Tu Primera Clase
Crea una clase llamada `Persona` con los siguientes atributos públicos:
- nombre
- edad
- ciudad

Crea un constructor `__init__` que inicialice estos tres atributos.

```python
# Escribe tu código aquí:






```

---

### Ejercicio 2: Crear Objetos
Usando la clase `Persona` del ejercicio anterior, crea tres objetos con los siguientes datos:

1. persona1: Juan, 25 años, Monterrey
2. persona2: María, 30 años, Guadalajara
3. persona3: Carlos, 22 años, CDMX

```python
# Escribe tu código aquí:






```

---

### Ejercicio 3: Método Mostrar
Agrega un método llamado `mostrar()` a la clase `Persona` que imprima todos los atributos del objeto en el siguiente formato:

```
Nombre: Juan
Edad: 25
Ciudad: Monterrey
```

Escribe la clase completa con el método incluido:

```python
# Escribe tu código aquí:











```

---

### Ejercicio 4: Acceso a Atributos
Dado el siguiente código:

```python
class Carro:
    marca = ""
    modelo = ""
    año = 0
    
    def __init__(self, ma, mo, a):
        self.marca = ma
        self.modelo = mo
        self.año = a

c1 = Carro("Toyota", "Corolla", 2020)
```

Escribe el código para:
1. Imprimir la marca del carro
2. Cambiar el año a 2021
3. Imprimir el nuevo año

```python
# Escribe tu código aquí:






```

---

### Ejercicio 5: Vector Simple
Crea un vector de tamaño 5 para almacenar objetos `Carro`. Agrega dos carros en las posiciones 0 y 1:
- Carro 1: Honda, Civic, 2019
- Carro 2: Mazda, 3, 2022

Luego, recorre el vector y muestra solo los dos carros agregados.

```python
# Escribe tu código aquí:











```

---

## NIVEL 2: ATRIBUTOS PRIVADOS Y ENCAPSULAMIENTO (Ejercicios 6-10)

### Ejercicio 6: Primer Atributo Privado
Crea una clase `CuentaBancaria` con:
- titular (público)
- `__saldo` (privado)

Constructor que inicialice ambos atributos.

```python
# Escribe tu código aquí:









```

---

### Ejercicio 7: Getter y Setter
Usando la clase `CuentaBancaria` del ejercicio anterior, agrega:
- `getSaldo()`: retorna el saldo
- `setSaldo(nuevo_saldo)`: establece el saldo solo si es mayor o igual a 0

Escribe la clase completa:

```python
# Escribe tu código aquí:
















```

---

### Ejercicio 8: Clase Producto Completa
Crea una clase `Producto` con:
- nombre (público)
- `__precio` (privado)
- stock (público)

Incluye:
- Constructor
- `getPrecio()`
- `setPrecio(p)` con validación (precio >= 0)
- `mostrar()` que imprima todos los datos

```python
# Escribe tu código aquí:





















```

---

### Ejercicio 9: Método de Negocio
Agrega a la clase `Producto` del ejercicio anterior un método llamado `vender(cantidad)` que:
- Verifique que hay suficiente stock
- Si hay, reste la cantidad del stock
- Si no hay, imprima "Stock insuficiente"

Escribe solo el método `vender`:

```python
# Escribe tu código aquí:









```

---

### Ejercicio 10: Uso Completo
Usando la clase `Producto` completa (con todos los métodos), escribe el código para:
1. Crear un producto: "Laptop", precio 15000, stock 10
2. Intentar vender 3 unidades
3. Mostrar los datos del producto
4. Intentar vender 8 unidades (debería quedar stock negativo, ¿funciona tu validación?)

```python
# Escribe tu código aquí:











```

---

## NIVEL 3: VALIDACIONES (Ejercicios 11-14)

### Ejercicio 11: Validar Longitud
Crea un método `validarTelefono(tel)` dentro de una clase `Contacto` que verifique:
- El teléfono tiene exactamente 10 dígitos
- Todos los caracteres son números
- Retorna True si es válido, False si no

```python
# Escribe tu código aquí:











```

---

### Ejercicio 12: Validar Email
Crea un método `validarEmail(email)` que verifique:
- Contiene exactamente un símbolo @
- Tiene al menos 5 caracteres
- Contiene al menos un punto (.) después del @
- Retorna True si es válido, False si no

```python
# Escribe tu código aquí:
















```

---

### Ejercicio 13: Validar Fecha Completa
Crea un método `validarFecha(fecha)` que verifique el formato dd/mm/aaaa:
- Longitud exacta de 10 caracteres
- Tiene diagonales en las posiciones correctas (índices 2 y 5)
- Día entre 1 y 31
- Mes entre 1 y 12
- Año entre 2020 y 2025

```python
# Escribe tu código aquí:





















```

---

### Ejercicio 14: Usar Validación en Constructor
Crea una clase `Evento` con:
- nombre (público)
- `__fecha` (privado)
- lugar (público)

En el constructor, usa el método `validarFecha()` para asegurarte que la fecha es válida antes de asignarla. Si no es válida, asigna "01/01/2023" por defecto.

```python
# Escribe tu código aquí:


























```

---

## NIVEL 4: BÚSQUEDA Y BANDERAS (Ejercicios 15-17)

### Ejercicio 15: Búsqueda Simple
Dado un vector de 5 estudiantes (ya creados), escribe el código para:
1. Pedir al usuario un nombre
2. Buscar ese nombre en el vector usando una bandera
3. Si se encuentra, imprimir "Estudiante encontrado"
4. Si no, imprimir "Estudiante no encontrado"

Asume que existe una clase `Estudiante` con atributo `nombre` y que el vector `estudiantes` tiene 5 elementos (cont = 5).

```python
# Escribe tu código aquí:
















```

---

### Ejercicio 16: Búsqueda y Mostrar
Mejora el ejercicio anterior para que cuando encuentre al estudiante, muestre todos sus datos usando el método `mostrar()` del objeto.

```python
# Escribe tu código aquí:
















```

---

### Ejercicio 17: Búsqueda Múltiple
Escribe código para buscar y mostrar TODOS los estudiantes que vivan en una ciudad específica (no solo el primero). No uses break, deja que el bucle recorra todo el vector.

```python
# Escribe tu código aquí:
















```

---

## NIVEL 5: MODIFICACIÓN Y ELIMINACIÓN (Ejercicios 18-20)

### Ejercicio 18: Modificar Atributo
Dado un vector de libros, escribe código para:
1. Buscar un libro por título
2. Si existe, cambiar su editorial
3. Mostrar mensaje de confirmación
4. Si no existe, mostrar "Libro no encontrado"

Asume: clase `Libro` con atributos `titulo` y `editorial`, vector `libros[]`, contador `cont`.

```python
# Escribe tu código aquí:





















```

---

### Ejercicio 19: Eliminación Lógica
Escribe código para eliminar un libro de forma lógica (marcando sus atributos como " "):
1. Buscar por título
2. Si existe, marcar titulo = " ", autor = " ", codigo = " "
3. Mostrar "Libro eliminado"
4. Si no existe, mostrar mensaje apropiado

```python
# Escribe tu código aquí:





















```

---

### Ejercicio 20: Mostrar Solo Válidos
Escribe código para recorrer un vector de libros y mostrar solo los que NO han sido eliminados (los que NO tienen titulo = " ").

```python
# Escribe tu código aquí:













```

---

## NIVEL 6: SISTEMAS COMPLETOS (Ejercicios 21-24)

### Ejercicio 21: Agregar con Validación
Escribe el código completo para agregar un nuevo libro al vector con:
- Verificar que hay espacio (cont < tam)
- Pedir datos al usuario (titulo, autor, editorial, edicion)
- Pedir código y validar que tenga 4 dígitos
- Crear el objeto y agregarlo al vector
- Incrementar el contador

```python
# Escribe tu código aquí:


























```

---

### Ejercicio 22: Menú Básico
Crea un menú con las siguientes opciones (solo la estructura del while y el if para opción 1):
1. Agregar libro
2. Mostrar libros
3. Salir

Al seleccionar opción 1, debe ejecutar el código del ejercicio 21.

```python
# Escribe tu código aquí:


























```

---

### Ejercicio 23: Sistema de Préstamos
Crea una clase `Prestamo` con:
- nombre_alumno (público)
- titulo_libro (público)
- `__codigo_libro` (privado)
- fecha_prestamo (público)
- estado (0 = prestado, 1 = devuelto)

Incluye:
- Constructor que inicialice nombre_alumno, titulo_libro, fecha_prestamo
- Estado inicial = 0
- getCodigo() y setCodigo()
- mostrar() que imprima todos los datos y el estado en texto ("Prestado" o "Devuelto")

```python
# Escribe tu código aquí:































```

---

### Ejercicio 24: Registrar Préstamo Completo
Escribe el código para registrar un préstamo:
1. Pedir nombre del alumno
2. Pedir fecha de préstamo
3. Pedir título del libro a prestar
4. Buscar el libro en el vector de libros
5. Si existe:
   - Crear objeto Prestamo
   - Asignar el código del libro al préstamo
   - Agregar al vector de préstamos
   - Incrementar contador de préstamos
6. Si no existe, mostrar "Libro no encontrado"

Asume: vector `libros[]` con cont, vector `prestamos[]` con cont2, clase Prestamo creada.

```python
# Escribe tu código aquí:

































```

---

## NIVEL 7: DESAFÍOS AVANZADOS (Ejercicios 25-27)

### Ejercicio 25: Método de Modificación Interactivo
Crea un método `modificarFecha()` dentro de la clase Prestamo que:
1. Muestre la fecha actual
2. Pida una nueva fecha al usuario
3. Valide la fecha usando validarFecha()
4. Si es válida, actualice la fecha
5. Si no, siga pidiendo hasta que sea válida
6. Muestre mensaje de confirmación

```python
# Escribe tu código aquí:


























```

---

### Ejercicio 26: Devolver Libro
Escribe código para devolver un libro:
1. Pedir el título del libro
2. Buscar en el vector de préstamos un préstamo con:
   - Ese título
   - Estado = 0 (prestado)
3. Si se encuentra, cambiar estado a 1
4. Mostrar "Libro devuelto correctamente"
5. Si no se encuentra o ya está devuelto, mostrar mensaje apropiado

```python
# Escribe tu código aquí:


























```

---

### Ejercicio 27: Sistema Completo Integrado
Crea un programa completo que:
1. Tenga un vector de Libros con 3 libros pre-cargados
2. Tenga un vector de Prestamos vacío
3. Tenga un menú con:
   - Agregar libro
   - Mostrar libros
   - Registrar préstamo
   - Mostrar préstamos
   - Devolver libro
   - Salir

Implementa TODAS las opciones del menú con validaciones completas.

**Este ejercicio es extenso, usa hojas adicionales si es necesario.**

---

## EJERCICIOS BONUS (Opcionales)

### Ejercicio 28: Búsqueda Parcial por Autor
Escribe código para buscar libros por autor de forma parcial (si el texto buscado está CONTENIDO en el nombre del autor). Ejemplo: buscar "Juan" debería encontrar "Juan Pérez" y "María Juan López".

```python
# Escribe tu código aquí:
















```

---

### Ejercicio 29: Estadísticas
Escribe código que recorra el vector de préstamos y cuente:
- Cuántos préstamos están activos (estado = 0)
- Cuántos han sido devueltos (estado = 1)
- Muestre ambos totales

```python
# Escribe tu código aquí:
















```

---

### Ejercicio 30: Validación de Código Complejo
Crea un método `validarCodigoLibro(cod)` que verifique:
- Longitud de 6 caracteres
- Los primeros 3 son letras mayúsculas
- Los últimos 3 son números
- Retorna True/False

Ejemplo válido: "LIB123"
Ejemplo inválido: "lib123", "LIBRO1", "123ABC"

```python
# Escribe tu código aquí:





















```

---

## AUTOEVALUACIÓN

Marca las casillas conforme completes cada sección:

- [ ] Nivel 1 completo (Ejercicios 1-5)
- [ ] Nivel 2 completo (Ejercicios 6-10)
- [ ] Nivel 3 completo (Ejercicios 11-14)
- [ ] Nivel 4 completo (Ejercicios 15-17)
- [ ] Nivel 5 completo (Ejercicios 18-20)
- [ ] Nivel 6 completo (Ejercicios 21-24)
- [ ] Nivel 7 completo (Ejercicios 25-27)
- [ ] Ejercicios Bonus (Ejercicios 28-30)

**Tiempo estimado total: 3-4 horas**

---

## NOTAS Y OBSERVACIONES

_Usa este espacio para escribir dudas o conceptos que necesites repasar:_

<br><br><br><br><br><br>

---

**¡Mucho éxito! Recuerda revisar tus respuestas con el archivo de soluciones.** 🎓
