# Guía Completa de Python

## Introducción

Python es un lenguaje de programación de alto nivel, interpretado y de propósito general. Esta guía cubre desde los conceptos más básicos hasta las características más avanzadas del lenguaje.

## 1. Fundamentos Básicos

### 1.1 Sintaxis Básica

Python utiliza la indentación para definir bloques de código. La indentación estándar es de 4 espacios. Cada línea de código representa una instrucción.

### 1.2 Comentarios

Python permite dos tipos de comentarios:
- Comentarios de una línea: comienzan con #
- Comentarios de múltiples líneas: se encierran entre triple comillas (''' o """)

Ejemplo:
```python
# Esto es un comentario de una línea

'''
Esto es un comentario
de múltiples líneas
'''
```

### 1.3 Variables

Las variables en Python no necesitan ser declaradas explícitamente. El tipo se infiere automáticamente.

Reglas para nombrar variables:
- Deben comenzar con una letra o guion bajo
- Solo pueden contener letras, números y guiones bajos
- Son sensibles a mayúsculas y minúsculas

Ejemplos:
```python
nombre = "Juan"         # String (cadena de texto)
edad = 25              # Integer (número entero)
altura = 1.75          # Float (número decimal)
es_estudiante = True   # Boolean (verdadero/falso)
```

## 2. Tipos de Datos Básicos

### 2.1 Números

Python tiene tres tipos numéricos principales:

**Enteros (int):**
```python
edad = 25
numero_grande = 1000000
numero_negativo = -100
```

**Números de Punto Flotante (float):**
```python
precio = 19.99
temperatura = -5.7
notacion_cientifica = 1e-10
```

**Números Complejos (complex):**
```python
complejo = 3 + 4j
```

### 2.2 Strings (Cadenas de Texto)

Los strings son secuencias inmutables de caracteres. Se pueden definir usando comillas simples o dobles.

Operaciones comunes:
```python
nombre = "Python"
print(nombre.upper())      # Convierte a mayúsculas: PYTHON
print(nombre.lower())      # Convierte a minúsculas: python
print(len(nombre))         # Longitud del string: 6
print(nombre[0])          # Primer carácter: P
print(nombre[-1])         # Último carácter: n
```

### 2.3 Booleanos

Los valores booleanos pueden ser True o False. Se usan en expresiones lógicas y condicionales.

Operadores lógicos:
- and: Y lógico
- or: O lógico
- not: Negación

## 3. Estructuras de Control

### 3.1 Condicionales

La estructura if-elif-else permite ejecutar diferentes bloques de código según condiciones:

```python
edad = 18

if edad < 13:
    print("Niño")
elif edad < 20:
    print("Adolescente")
else:
    print("Adulto")
```

### 3.2 Bucles

**Bucle for:**
```python
for i in range(5):
    print(i)  # Imprime números del 0 al 4

for letra in "Python":
    print(letra)  # Imprime cada letra
```

**Bucle while:**
```python
contador = 0
while contador < 5:
    print(contador)
    contador += 1
```

## 4. Estructuras de Datos

### 4.1 Listas

Las listas son colecciones ordenadas y mutables:

```python
frutas = ["manzana", "banana", "naranja"]
numeros = [1, 2, 3, 4, 5]

# Operaciones comunes
frutas.append("pera")          # Añadir elemento
frutas.remove("banana")        # Eliminar elemento
print(len(frutas))            # Longitud
print(frutas[0])              # Acceder a elemento
frutas.sort()                 # Ordenar
```

### 4.2 Tuplas

Las tuplas son similares a las listas pero inmutables:

```python
coordenadas = (10, 20)
fecha = (25, "Diciembre", 2024)
```

### 4.3 Diccionarios

Los diccionarios almacenan pares clave-valor:

```python
persona = {
    "nombre": "Ana",
    "edad": 25,
    "ciudad": "Madrid"
}

# Operaciones comunes
print(persona["nombre"])      # Acceder a valor
persona["telefono"] = "123456"  # Añadir nuevo par
del persona["edad"]           # Eliminar par
```

## 5. Funciones

### 5.1 Definición de Funciones

```python
def saludar(nombre):
    """
    Esta función saluda a la persona especificada
    """
    return f"Hola, {nombre}!"

# Función con parámetros por defecto
def saludar_formal(nombre, titulo="Sr."):
    return f"Hola, {titulo} {nombre}"
```

### 5.2 Argumentos de Funciones

```python
# Argumentos posicionales y nombrados
def describir_persona(nombre, edad, ciudad="Desconocida"):
    return f"{nombre} tiene {edad} años y vive en {ciudad}"

# Uso
print(describir_persona("Juan", 25))
print(describir_persona(edad=30, nombre="Ana", ciudad="Madrid"))
```

## 6. Programación Orientada a Objetos

### 6.1 Clases y Objetos

```python
class Persona:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad
    
    def presentarse(self):
        return f"Me llamo {self.nombre} y tengo {self.edad} años"

# Crear objeto
persona1 = Persona("Juan", 25)
print(persona1.presentarse())
```

### 6.2 Herencia

```python
class Estudiante(Persona):
    def __init__(self, nombre, edad, carrera):
        super().__init__(nombre, edad)
        self.carrera = carrera
    
    def estudiar(self):
        return f"Estoy estudiando {self.carrera}"
```

## 7. Manejo de Errores

### 7.1 Try-Except

```python
try:
    numero = int(input("Introduce un número: "))
except ValueError:
    print("No es un número válido")
except Exception as e:
    print(f"Error: {e}")
else:
    print("Número válido")
finally:
    print("Proceso completado")
```

## 8. Módulos y Paquetes

### 8.1 Importación

```python
# Importar módulo completo
import math

# Importar funciones específicas
from random import randint, choice

# Importar con alias
import pandas as pd
```

## 9. Características Avanzadas

### 9.1 Comprensión de Listas

```python
# Crear lista de cuadrados
cuadrados = [x**2 for x in range(10)]

# Lista con condición
pares = [x for x in range(10) if x % 2 == 0]
```

### 9.2 Generadores

```python
def contador(max):
    n = 0
    while n < max:
        yield n
        n += 1

# Uso
for num in contador(5):
    print(num)
```

### 9.3 Decoradores

```python
def mi_decorador(funcion):
    def wrapper():
        print("Antes de la función")
        funcion()
        print("Después de la función")
    return wrapper

@mi_decorador
def saludar():
    print("¡Hola!")
```

## Conclusión

Esta guía cubre los aspectos fundamentales y avanzados de Python. Para profundizar en cualquier tema, se recomienda consultar la documentación oficial de Python (python.org) y practicar con ejercicios.

Recuerda que la mejor manera de aprender Python es practicando y escribiendo código regularmente. Comienza con conceptos básicos y ve avanzando gradualmente hacia características más complejas.
