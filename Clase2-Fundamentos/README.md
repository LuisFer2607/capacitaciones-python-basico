# 🧑‍🏫 Clase 2: Fundamentos de Programación en Python

## 1. Tipos de Datos Básicos en Python

Python tiene varios tipos de datos incorporados. Hoy nos centraremos en los tres más fundamentales:

### 1.1 Números 🔢

Python tiene tres tipos numéricos principales:

1. **Enteros (int)**: Números sin parte decimal.
   Ejemplo: `x = 5`

2. **Flotantes (float)**: Números con parte decimal.
   Ejemplo: `y = 3.14`

3. **Complejos (complex)**: Números con parte real e imaginaria.
   Ejemplo: `z = 1 + 2j`

```python
# Ejemplos de operaciones con números
a = 10
b = 3

print(a + b)  # Suma: 13
print(a - b)  # Resta: 7
print(a * b)  # Multiplicación: 30
print(a / b)  # División: 3.3333...
print(a // b) # División entera: 3
print(a % b)  # Módulo (resto): 1
print(a ** b) # Potencia: 1000
```

> 🧮 **Dato curioso**: Python puede manejar números enteros de cualquier tamaño, limitado solo por la memoria disponible en tu sistema. Esto lo hace ideal para cálculos matemáticos de alta precisión.

### 1.2 Cadenas (Strings) 🔤

Las cadenas son secuencias de caracteres, encerradas entre comillas simples o dobles.

```python
nombre = "Luis Fernando"
apellido = 'Flores Cuadros'

# Concatenación
nombre_completo = nombre + " " + apellido
print(nombre_completo)  # Imprime: Luis Fernando Flores Cuadros

# Longitud de una cadena
print(len(nombre_completo))  # Imprime: 13

# Indexación y slicing
print(nombre[0])  # Imprime: A
print(apellido[1:4])  # Imprime: ohn

# Métodos de cadenas
print(nombre_completo.upper())  # Imprime: LUIS FERNANDO FLORES CUADROS
print(nombre_completo.lower())  # Imprime: luis fernando flores cuadros
print(nombre_completo.split())  # Imprime: ['Luis', 'Fernando','Flores','Cuadros']
```

> 📚 **Dato curioso**: En Python, las cadenas son inmutables. Esto significa que una vez creada una cadena, no puedes cambiar su contenido. Cualquier operación que parezca modificar una cadena en realidad crea una nueva.

### 1.3 Booleanos ✅❌

Los booleanos representan dos valores: True (Verdadero) y False (Falso).

```python
es_python_divertido = True
es_dificil = False

print(es_python_divertido)  # Imprime: True
print(es_dificil)  # Imprime: False

# Operaciones lógicas
print(True and False)  # Imprime: False
print(True or False)   # Imprime: True
print(not True)        # Imprime: False

# Comparaciones que devuelven booleanos
print(5 > 3)   # Imprime: True
print(10 == 8) # Imprime: False
print(7 != 7)  # Imprime: False
```

> 🤔 **Dato curioso**: En Python, cualquier objeto puede ser evaluado en un contexto booleano. Los objetos considerados "falsos" incluyen: None, False, 0, 0.0, '' (cadena vacía), [] (lista vacía), {} (diccionario vacío), set() (conjunto vacío).

## 2. Variables y Operadores

### 2.1 Variables

En Python, las variables son nombres que se refieren a objetos en la memoria.

```python
# Asignación de variables
x = 5
y = "Hola, mundo"
z = 3.14

# Asignación múltiple
a, b, c = 1, 2, 3

# Intercambio de valores
x, y = y, x

# Nombres de variables
edad_usuario = 25  # Uso de snake_case (recomendado en Python)
edadUsuario = 25   # camelCase (no recomendado, pero válido)
_variable_privada = 100  # Las variables que comienzan con _ son consideradas "privadas" por convención

# Constantes (por convención, se escriben en mayúsculas)
PI = 3.14159
GRAVEDAD = 9.8

print(f"x = {x}, y = {y}, z = {z}")
print(f"a = {a}, b = {b}, c = {c}")
print(f"edad_usuario = {edad_usuario}")
print(f"PI = {PI}, GRAVEDAD = {GRAVEDAD}")
```

> 🐍 **Dato curioso**: A diferencia de otros lenguajes, Python no tiene un tipo de dato específico para constantes. Por convención, se usan nombres en mayúsculas para indicar que una variable no debe ser modificada, pero técnicamente, aún se puede cambiar su valor.

### 2.2 Operadores

Python tiene varios tipos de operadores:

1. **Aritméticos**: `+, -, *, /, //, %, **`
2. **Comparación**: `==, !=, <, >, <=, >=`
3. **Lógicos**: `and, or, not`
4. **Asignación**: `=, +=, -=, *=, /=, %=, **=, //=`
5. **Identidad**: `is, is not`
6. **Pertenencia**: `in, not in`

```python
# Ejemplos de operadores
a = 10
b = 3

# Aritméticos
print(a + b, a - b, a * b, a / b, a // b, a % b, a ** b)

# Comparación
print(a == b, a != b, a < b, a > b, a <= b, a >= b)

# Lógicos
x = True
y = False
print(x and y, x or y, not x)

# Asignación
c = 5
c += 2  # Equivalente a c = c + 2
print(c)

# Identidad
lista1 = [1, 2, 3]
lista2 = [1, 2, 3]
lista3 = lista1
print(lista1 is lista2, lista1 is lista3)

# Pertenencia
print(2 in lista1, 4 not in lista1)
```

## 3. Estructuras de Control de Flujo

### 3.1 Condicionales (if, else, elif) ❓

Las estructuras condicionales permiten ejecutar diferentes bloques de código basados en condiciones.

```python
# Estructura básica if-else
edad = 18

if edad >= 18:
    print("Eres mayor de edad")
else:
    print("Eres menor de edad")

# Estructura if-elif-else
nota = 85

if nota >= 90:
    print("A")
elif nota >= 80:
    print("B")
elif nota >= 70:
    print("C")
elif nota >= 60:
    print("D")
else:
    print("F")

# Operador ternario
mensaje = "Aprobado" if nota >= 60 else "Reprobado"
print(mensaje)

# Condiciones anidadas
tiene_pasaporte = True
tiene_boleto = True

if tiene_pasaporte:
    if tiene_boleto:
        print("Puedes viajar")
    else:
        print("Necesitas comprar un boleto")
else:
    print("Necesitas un pasaporte")
```

> 🤯 **Dato curioso**: Python no tiene una declaración `switch` como otros lenguajes. En su lugar, se suele usar un diccionario de funciones o una serie de `elif` para lograr un efecto similar.

### 3.2 Bucles (for, while) 🔁

Los bucles permiten repetir un bloque de código varias veces.

#### Bucle for

```python
# Iterando sobre una lista
frutas = ["manzana", "banana", "cereza"]
for fruta in frutas:
    print(fruta)

# Iterando sobre un rango
for i in range(5):
    print(i)

# Enumerando elementos
for index, fruta in enumerate(frutas):
    print(f"Índice {index}: {fruta}")

# Iterando sobre un diccionario
persona = {"nombre": "Luis Fernando Flores", "edad": 69, "ciudad": "Manta"}
for clave, valor in persona.items():
    print(f"{clave}: {valor}")

# Comprensión de listas
cuadrados = [x**2 for x in range(10)]
print(cuadrados)
```

#### Bucle while

```python
# Bucle while básico
contador = 0
while contador < 5:
    print(contador)
    contador += 1

# Bucle while con break
while True:
    respuesta = input("Escribe 'salir' para terminar: ")
    if respuesta.lower() == 'salir':
        break

# Bucle while con continue
i = 0
while i < 10:
    i += 1
    if i % 2 == 0:
        continue
    print(i)
```
