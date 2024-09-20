# 🧑‍🏫 Clase 4: Conjuntos y Diccionarios en Python (Enfoque en Guayaquil)

## 1. Estructuras de datos: Conjuntos y diccionarios 📚

### 1.1 Conjuntos

Los conjuntos son colecciones desordenadas de elementos únicos.

```python
# Creación de un conjunto de sitios turísticos de Guayaquil
sitios_guayaquil = {"Malecón 2000", "Las Peñas", "Parque Seminario", "Cerro Santa Ana", "Isla Santay"}

# Método add(): Añadir un elemento al conjunto
sitios_guayaquil.add("Parque Histórico")
print("Sitios turísticos de Guayaquil:", sitios_guayaquil)

# Método remove(): Eliminar un elemento del conjunto
sitios_guayaquil.remove("Duran")
print("Sitios después de remover Duran:", sitios_guayaquil)

# Método discard(): Eliminar un elemento si existe (no lanza error si no existe)
sitios_guayaquil.discard("Playa de Villamil")  # No existe, pero no genera error
print("Sitios después de discard:", sitios_guayaquil)

# Creación de otro conjunto
sitios_historicos = {"Las Peñas", "Cementerio General", "Parque Centenario"}

# Método union(): Unir dos conjuntos
todos_sitios = sitios_guayaquil.union(sitios_historicos)
print("Todos los sitios:", todos_sitios)

# Método intersection(): Encontrar elementos comunes
sitios_comunes = sitios_guayaquil.intersection(sitios_historicos)
print("Sitios en ambos conjuntos:", sitios_comunes)

# Método difference(): Encontrar elementos que están en un conjunto pero no en el otro
sitios_unicos = sitios_guayaquil.difference(sitios_historicos)
print("Sitios únicos de Guayaquil:", sitios_unicos)
```

> 🌴 **Dato curioso**: El Parque Seminario de Guayaquil también es conocido como "Parque de las Iguanas" debido a la gran cantidad de iguanas que viven libremente en él.

### 1.2 Diccionarios

Los diccionarios son estructuras de datos que almacenan pares clave-valor.

```python
# Creación de un diccionario con información sobre Guayaquil
info_guayaquil = {
    "nombre": "Guayaquil",
    "provincia": "Guayas",
    "población": 2698077,
    "fundación": 1538,
    "apodo": "Perla del Pacífico"
}

# Método get(): Obtener un valor (con valor predeterminado si la clave no existe)
clima = info_guayaquil.get("clima", "Información no disponible")
print("Clima de Guayaquil:", clima)

# Método keys(): Obtener todas las claves del diccionario
print("Información disponible sobre Guayaquil:", info_guayaquil.keys())

# Método values(): Obtener todos los valores del diccionario
print("Valores de la información:", info_guayaquil.values())

# Método items(): Obtener pares clave-valor
print("\nDetalles de Guayaquil:")
for clave, valor in info_guayaquil.items():
    print(f"{clave.capitalize()}: {valor}")

# Método update(): Actualizar el diccionario con nuevos pares clave-valor
info_guayaquil.update({
    "gentilicio": "guayaquileño",
    "río": "Guayas"
})
print("\nInformación actualizada:", info_guayaquil)

# Método clear(): Eliminar todos los elementos del diccionario
info_temporal = info_guayaquil.copy()  # Hacemos una copia para no perder la información original
info_temporal.clear()
print("Diccionario después de clear():", info_temporal)
```

> 🚢 **Dato curioso**: Guayaquil es el puerto principal de Ecuador y maneja alrededor del 70% del comercio exterior del país.

### 1.3 Aplicación práctica: Guía turística de Guayaquil

```python
guia_turistica = {
    "Malecón 2000": {
        "tipo": "Paseo ribereño",
        "longitud": "2.5 km",
        "atracciones": ["La Rotonda", "Torre Morisca", "Jardines"]
    },
    "Las Peñas": {
        "tipo": "Barrio histórico",
        "escalones": 444,
        "atracciones": ["Casas coloridas", "Galería de arte", "Vista panorámica"]
    },
    "Parque Seminario": {
        "tipo": "Parque urbano",
        "alias": "Parque de las Iguanas",
        "atracciones": ["Iguanas", "Estatua de Bolívar", "Árboles centenarios"]
    }
}

# Uso de métodos de diccionarios para explorar la guía turística
for sitio, info in guia_turistica.items():
    print(f"\n{sitio}:")
    for caracteristica, valor in info.items():
        if isinstance(valor, list):
            print(f"  {caracteristica.capitalize()}: {', '.join(valor)}")
        else:
            print(f"  {caracteristica.capitalize()}: {valor}")

# Añadir un nuevo sitio turístico
guia_turistica.update({
    "Cerro Santa Ana": {
        "tipo": "Mirador",
        "escalones": 444,
        "atracciones": ["Faro", "Capilla", "Restaurantes"]
    }
})

# Obtener todas las atracciones únicas
todas_atracciones = set()
for sitio in guia_turistica.values():
    todas_atracciones.update(sitio.get("atracciones", []))

print("\nTodas las atracciones únicas en Guayaquil:")
for atraccion in sorted(todas_atracciones):
    print(f"- {atraccion}")
```

> 🦎 **Dato curioso**: Las iguanas del Parque Seminario son tan famosas que incluso tienen su propia "casa de iguanas", una estructura diseñada específicamente para ellas en el parque.

## 2. Listas por comprensión (List comprehensions) 📜

Las listas por comprensión proporcionan una forma concisa de crear listas basadas en listas existentes u otros iterables.

```python
# Lista de barrios de Guayaquil
barrios = ["Urdesa", "Kennedy", "Alborada", "Samborondón", "Garzota", "Sauces", "Centenario"]

# Lista por comprensión: barrios que comienzan con 'S'
barrios_s = [barrio for barrio in barrios if barrio.startswith('S')]
print("Barrios que comienzan con 'S':", barrios_s)

# Lista por comprensión: longitud de los nombres de los barrios
longitudes_barrios = [len(barrio) for barrio in barrios]
print("Longitudes de los nombres de barrios:", longitudes_barrios)

# Lista por comprensión con condicional: barrios con más de 7 letras
barrios_largos = [barrio for barrio in barrios if len(barrio) > 7]
print("Barrios con más de 7 letras:", barrios_largos)

# Ejemplo más complejo: crear un diccionario de barrios y sus longitudes
dict_barrios = {barrio: len(barrio) for barrio in barrios}
print("\nDiccionario de barrios y longitudes:")
for barrio, longitud in dict_barrios.items():
    print(f"{barrio}: {longitud} letras")

# Ejemplo con temperaturas: convertir de Celsius a Fahrenheit
temperaturas_c = [28, 30, 29, 31, 27]  # Temperaturas típicas de Guayaquil en Celsius
temperaturas_f = [round((temp * 9/5) + 32, 1) for temp in temperaturas_c]
print("\nTemperaturas en Guayaquil:")
for c, f in zip(temperaturas_c, temperaturas_f):
    print(f"{c}°C = {f}°F")
```
