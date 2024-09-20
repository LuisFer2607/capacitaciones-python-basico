# 🧑‍🏫 Clase 3: Funciones y Estructuras de Datos

## 1. Funciones en Python 🔧

Las funciones son bloques de código reutilizables que realizan una tarea específica. En Python, las funciones se definen usando la palabra clave `def`.

### 1.1 Definición y uso de funciones

```python
def saludar_manabita():
    print("¡Hola, manabita!")

# Llamada a la función
saludar_manabita()
```

> 🌴 **Dato curioso**: Manta, tu ciudad natal, es conocida como "La Puerta del Pacífico" debido a su importante puerto marítimo.

### 1.2 Parámetros y retorno de valores

Las funciones pueden recibir parámetros y devolver valores.

```python
def calcular_edad(anio_nacimiento):
    anio_actual = 2024
    return anio_actual - anio_nacimiento

# Uso de la función
tu_edad = calcular_edad(1955)
print(f"Luis Fernando, tu edad es: {tu_edad}")

def describir_persona(nombre, edad, ciudad):
    return f"{nombre} tiene {edad} años y vive en {ciudad}."

# Uso de la función
descripcion = describir_persona("Luis Fernando Flores", 69, "Manta")
print(descripcion)
```

> 🦈 **Dato curioso**: Manta es famosa por su pesca de atún y otras especies marinas. Podrías usar funciones para calcular estadísticas de pesca.

### 1.3 Funciones anónimas (lambda) 📎

Las funciones lambda son pequeñas funciones anónimas que pueden tener cualquier número de argumentos pero solo una expresión.

```python
# Función lambda para convertir temperaturas de Celsius a Fahrenheit
celsius_a_fahrenheit = lambda celsius: (celsius * 9/5) + 32

# Uso de la función lambda
temp_guayaquil = 30
temp_f = celsius_a_fahrenheit(temp_guayaquil)
print(f"La temperatura en Guayaquil es de {temp_f}°F")

# Uso de lambda con map()
ciudades_ecuador = ["Quito", "Guayaquil", "Cuenca", "Manta"]
longitudes = list(map(lambda ciudad: len(ciudad), ciudades_ecuador))
print(f"Longitudes de los nombres de ciudades: {longitudes}")
```

> 🌡️ **Dato curioso**: Ecuador, a pesar de estar en la línea ecuatorial, tiene una variedad de climas debido a su geografía diversa, desde el cálido Manta hasta el fresco Quito.

## 2. Estructuras de datos: Listas y tuplas 📋

### 2.1 Creación y manipulación de listas

Las listas son colecciones ordenadas y mutables de elementos.

```python
# Creación de una lista de platos típicos de Manabí
platos_manabi = ["Viche", "Corviche", "Encebollado", "Ceviche"]

# Añadir un elemento a la lista
platos_manabi.append("Bollo de pescado")

# Acceder a elementos de la lista
print(f"Un plato famoso de Manta es: {platos_manabi[2]}")

# Modificar un elemento
platos_manabi[1] = "Corviche de camarón"

# Recorrer la lista
print("Platos típicos de Manabí:")
for plato in platos_manabi:
    print(f"- {plato}")

# Longitud de la lista
print(f"Número de platos en la lista: {len(platos_manabi)}")
```

> 🍽️ **Dato curioso**: El viche, un plato típico de Manabí, es una sopa espesa hecha con pescado o mariscos, maní y vegetales.

### 2.2 Operaciones comunes con listas y tuplas

```python
# Lista de provincias de la costa ecuatoriana
provincias_costa = ["Esmeraldas", "Manabí", "Santa Elena", "Guayas", "Los Ríos", "El Oro"]

# Slicing
print(f"Las tres primeras provincias costeras son: {provincias_costa[:3]}")

# Ordenar lista
provincias_costa.sort()
print(f"Provincias costeras ordenadas alfabéticamente: {provincias_costa}")

# Tupla de coordenadas de Manta
coordenadas_manta = (-0.9675, -80.7089)

# Desempaquetado de tupla
latitud, longitud = coordenadas_manta
print(f"Manta está ubicada en la latitud {latitud} y longitud {longitud}")

# Lista de listas (matriz)
temperaturas_ecuador = [
    ["Manta", 28, 30, 29],
    ["Quito", 10, 22, 15],
    ["Guayaquil", 24, 32, 28]
]

print("Temperaturas en Ecuador:")
for ciudad in temperaturas_ecuador:
    print(f"{ciudad[0]}: Mín {ciudad[1]}°C, Máx {ciudad[2]}°C, Promedio {ciudad[3]}°C")
```

> 🌊 **Dato curioso**: Ecuador tiene más de 2,200 km de costa en el Océano Pacífico, y Manta es uno de sus puertos más importantes.

### 2.3 Combinando funciones y estructuras de datos

```python
def filtrar_ciudades_calidas(ciudades_temp, umbral):
    return [ciudad for ciudad in ciudades_temp if ciudad[3] > umbral]

ciudades_calidas = filtrar_ciudades_calidas(temperaturas_ecuador, 25)
print("Ciudades con temperatura promedio mayor a 25°C:")
for ciudad in ciudades_calidas:
    print(f"- {ciudad[0]}")

# Uso de lambda con filter()
provincias_largas = list(filter(lambda prov: len(prov) > 6, provincias_costa))
print(f"Provincias costeras con nombres de más de 6 letras: {provincias_largas}")
```

> 🏖️ **Dato curioso**: Manta es famosa por sus hermosas playas como El Murciélago y Tarqui, que atraen a turistas de todo Ecuador y el mundo.
