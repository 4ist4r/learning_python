# Guía Completa de la Sintaxis de Python

## Índice
1. [Fundamentos Básicos](#fundamentos-básicos)
2. [Tipos de Datos](#tipos-de-datos)
3. [Control de Flujo](#control-de-flujo)
4. [Funciones](#funciones)
5. [Estructuras de Datos](#estructuras-de-datos)
6. [Programación Orientada a Objetos](#programación-orientada-a-objetos)
7. [Características Avanzadas](#características-avanzadas)
8. [Gestión de Errores](#gestión-de-errores)
9. [Módulos y Paquetes](#módulos-y-paquetes)
10. [Características Especiales](#características-especiales)

## Fundamentos Básicos

### Comentarios
```python
# Comentario de una línea
'''
Comentario
de múltiples
líneas
'''
```

### Variables y Asignación
```python
nombre = "Python"           # String
edad = 30                  # Integer
precio = 19.99            # Float
es_verdadero = True       # Boolean

# Asignación múltiple
x, y, z = 1, 2, 3

# Asignación del mismo valor
a = b = c = 0
```

### Operadores Básicos
```python
# Aritméticos
suma = 5 + 3
resta = 5 - 3
multiplicacion = 5 * 3
division = 5 / 3          # División flotante
division_entera = 5 // 3  # División entera
modulo = 5 % 3           # Resto
potencia = 5 ** 3        # Exponenciación

# Comparación
igual = 5 == 3           # False
diferente = 5 != 3       # True
mayor = 5 > 3            # True
menor = 5 < 3            # False
mayor_igual = 5 >= 3     # True
menor_igual = 5 <= 3     # False

# Lógicos
and_logico = True and False  # False
or_logico = True or False   # True
not_logico = not True      # False
```

## Tipos de Datos

### Números
```python
# Enteros (int)
entero = 42
entero_grande = 1_000_000  # Separador de miles

# Flotantes (float)
flotante = 3.14
notacion_cientifica = 1e-10

# Complejos (complex)
complejo = 3 + 4j
```

### Cadenas (Strings)
```python
# Creación de strings
simple = 'Hola'
doble = "Mundo"
triple = '''Múltiples
líneas'''

# Métodos de strings
texto = "python"
mayusculas = texto.upper()        # 'PYTHON'
minusculas = texto.lower()        # 'python'
capitalizado = texto.capitalize() # 'Python'
conteo = texto.count('t')        # 1
reemplazo = texto.replace('p', 'P')  # 'Python'

# Formateo de strings
nombre = "Ana"
edad = 25
# f-strings (Python 3.6+)
mensaje = f"Me llamo {nombre} y tengo {edad} años"
# format()
mensaje = "Me llamo {} y tengo {} años".format(nombre, edad)
# % operador
mensaje = "Me llamo %s y tengo %d años" % (nombre, edad)

# Slicing
texto = "Python"
primero = texto[0]      # 'P'
ultimo = texto[-1]      # 'n'
subcadena = texto[1:4]  # 'yth'
reverso = texto[::-1]   # 'nohtyP'
```

## Control de Flujo

### Condicionales
```python
# if-elif-else
edad = 18
if edad < 18:
    print("Menor de edad")
elif edad == 18:
    print("Justo 18")
else:
    print("Mayor de edad")

# Operador ternario
mensaje = "Adulto" if edad >= 18 else "Menor"

# match (Python 3.10+)
status = 404
match status:
    case 200:
        print("OK")
    case 404:
        print("Not Found")
    case _:
        print("Unknown")
```

### Bucles
```python
# for
for i in range(5):
    print(i)

# for con enumerate
frutas = ['manzana', 'pera', 'uva']
for indice, fruta in enumerate(frutas):
    print(f"{indice}: {fruta}")

# while
contador = 0
while contador < 5:
    print(contador)
    contador += 1

# break y continue
for i in range(10):
    if i == 3:
        continue  # Salta esta iteración
    if i == 8:
        break    # Sale del bucle
    print(i)

# else en bucles
for i in range(5):
    print(i)
else:
    print("Bucle completado sin break")
```

## Funciones

### Definición y Llamada
```python
# Función básica
def saludar(nombre):
    return f"Hola, {nombre}"

# Función con argumentos por defecto
def saludar(nombre="Mundo"):
    return f"Hola, {nombre}"

# Argumentos posicionales y nombrados
def funcion(pos1, pos2, *, kw1="default", kw2="default"):
    pass

# Args y kwargs
def funcion_flexible(*args, **kwargs):
    print(f"Args: {args}")
    print(f"Kwargs: {kwargs}")

# Anotaciones de tipo (type hints)
def suma(a: int, b: int) -> int:
    return a + b
```

### Funciones Lambda
```python
# Lambda básica
cuadrado = lambda x: x**2

# Lambda con múltiples argumentos
suma = lambda a, b: a + b

# Lambda en funciones de orden superior
numeros = [1, 2, 3, 4, 5]
pares = list(filter(lambda x: x % 2 == 0, numeros))
```

## Estructuras de Datos

### Listas
```python
# Creación
lista = [1, 2, 3, 4, 5]
lista_mixta = [1, "dos", 3.0, True]

# Métodos de lista
lista.append(6)        # Añadir al final
lista.insert(0, 0)    # Insertar en posición
lista.extend([7, 8])  # Extender con otra lista
lista.remove(1)       # Eliminar primer valor 1
elemento = lista.pop() # Eliminar y devolver último elemento
indice = lista.index(3) # Encontrar índice de valor
lista.sort()          # Ordenar in-place
lista.reverse()       # Invertir in-place

# List comprehension
cuadrados = [x**2 for x in range(10)]
pares = [x for x in range(10) if x % 2 == 0]
```

### Tuplas
```python
# Creación
tupla = (1, 2, 3)
tupla_un_elemento = (1,)

# Métodos de tupla
conteo = tupla.count(1)    # Contar ocurrencias
indice = tupla.index(2)    # Encontrar índice

# Named tuples
from collections import namedtuple
Punto = namedtuple('Punto', ['x', 'y'])
p = Punto(11, y=22)
```

### Diccionarios
```python
# Creación
dict1 = {'a': 1, 'b': 2}
dict2 = dict(a=1, b=2)

# Métodos de diccionario
valor = dict1.get('c', 'default')  # Obtener con valor por defecto
dict1.update({'c': 3})             # Actualizar/añadir elementos
claves = dict1.keys()              # Obtener claves
valores = dict1.values()           # Obtener valores
items = dict1.items()              # Obtener pares clave-valor
dict1.pop('a')                     # Eliminar y devolver valor
dict1.setdefault('d', 4)          # Establecer si no existe

# Dict comprehension
cuadrados = {x: x**2 for x in range(5)}
```

### Sets
```python
# Creación
set1 = {1, 2, 3}
set2 = set([1, 2, 3])

# Métodos de set
set1.add(4)           # Añadir elemento
set1.remove(1)        # Eliminar elemento (error si no existe)
set1.discard(1)       # Eliminar elemento (sin error)
set1.update({5, 6})   # Actualizar con múltiples elementos

# Operaciones de conjunto
union = set1 | set2
interseccion = set1 & set2
diferencia = set1 - set2
diff_simetrica = set1 ^ set2

# Set comprehension
pares = {x for x in range(10) if x % 2 == 0}
```

## Programación Orientada a Objetos

### Clases Básicas
```python
class Persona:
    # Variable de clase
    especie = "Humano"
    
    # Constructor
    def __init__(self, nombre, edad):
        self.nombre = nombre  # Atributo de instancia
        self.edad = edad
    
    # Método de instancia
    def saludar(self):
        return f"Hola, soy {self.nombre}"
    
    # Método de clase
    @classmethod
    def crear_anonimo(cls):
        return cls("Anónimo", 0)
    
    # Método estático
    @staticmethod
    def es_adulto(edad):
        return edad >= 18
```

### Herencia
```python
class Empleado(Persona):
    def __init__(self, nombre, edad, salario):
        super().__init__(nombre, edad)
        self.salario = salario
    
    # Sobrescribir método
    def saludar(self):
        return f"{super().saludar()} y soy empleado"
```

### Propiedades y Descriptores
```python
class Temperatura:
    def __init__(self):
        self._celsius = 0
    
    @property
    def celsius(self):
        return self._celsius
    
    @celsius.setter
    def celsius(self, valor):
        if valor < -273.15:
            raise ValueError("Temperatura por debajo del cero absoluto")
        self._celsius = valor
    
    @property
    def fahrenheit(self):
        return (self.celsius * 9/5) + 32
```

### Métodos Especiales
```python
class Vector:
    def __init__(self, x, y):
        self.x = x
        self.y = y
    
    def __str__(self):
        return f"Vector({self.x}, {self.y})"
    
    def __repr__(self):
        return f"Vector(x={self.x}, y={self.y})"
    
    def __add__(self, otro):
        return Vector(self.x + otro.x, self.y + otro.y)
    
    def __len__(self):
        return 2
    
    def __getitem__(self, indice):
        if indice == 0:
            return self.x
        elif indice == 1:
            return self.y
        raise IndexError("Vector índice fuera de rango")
```

## Características Avanzadas

### Decoradores
```python
# Decorador básico
def mi_decorador(func):
    def wrapper():
        print("Antes de la función")
        func()
        print("Después de la función")
    return wrapper

@mi_decorador
def saludar():
    print("¡Hola!")

# Decorador con argumentos
def repetir(veces):
    def decorador(func):
        def wrapper(*args, **kwargs):
            for _ in range(veces):
                resultado = func(*args, **kwargs)
            return resultado
        return wrapper
    return decorador

@repetir(3)
def saludar(nombre):
    print(f"¡Hola {nombre}!")
```

### Generadores
```python
# Generador básico
def contador(max):
    n = 0
    while n < max:
        yield n
        n += 1

# Expresión generadora
cuadrados = (x**2 for x in range(10))

# Enviar valores al generador
def acumulador():
    total = 0
    while True:
        valor = yield total
        if valor is None:
            break
        total += valor
```

### Context Managers
```python
# Using with
class MiContextManager:
    def __enter__(self):
        print("Entrando al contexto")
        return self
    
    def __exit__(self, exc_type, exc_value, traceback):
        print("Saliendo del contexto")

# Usando decorador contextlib
from contextlib import contextmanager

@contextmanager
def tempfile():
    print("Creando archivo temporal")
    try:
        yield "nombre_archivo"
    finally:
        print("Eliminando archivo temporal")
```

### Type Hints Avanzados
```python
from typing import List, Dict, Optional, Union, Callable, TypeVar

# Tipos básicos
def suma(a: int, b: int) -> int:
    return a + b

# Tipos compuestos
Vector = List[float]
Matriz = List[List[float]]

def procesar_vector(v: Vector) -> float:
    return sum(v)

# Tipos opcionales y uniones
def buscar(texto: str) -> Optional[int]:
    return texto.find('x')

# Tipos genéricos
T = TypeVar('T')
def primero(lista: List[T]) -> Optional[T]:
    return lista[0] if lista else None

# Tipos callable
Operacion = Callable[[int, int], int]
def aplicar_operacion(f: Operacion, x: int, y: int) -> int:
    return f(x, y)
```

## Gestión de Errores

### Try-Except
```python
# Manejo básico de excepciones
try:
    resultado = 10 / 0
except ZeroDivisionError:
    print("División por cero")
except Exception as e:
    print(f"Error: {e}")
else:
    print("Sin errores")
finally:
    print("Limpieza")

# Lanzar excepciones
def dividir(a, b):
    if b == 0:
        raise ValueError("No se puede dividir por cero")
    return a / b

# Crear excepciones personalizadas
class MiError(Exception):
    def __init__(self, mensaje):
        self.mensaje = mensaje
        super().__init__(self.mensaje)
```

## Módulos y Paquetes

### Estructura de Módulos
```python
# modulo.py
def funcion():
    pass

class Clase:
    pass

if __name__ == "__main__":
    # Código que se ejecuta solo si el módulo
    # se ejecuta directamente
    pass
```

### Importación
```python
# Importar módulo completo
import modulo

# Importar elementos específicos
from modulo import