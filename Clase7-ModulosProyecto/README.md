# Clase 7: Módulos, Bibliotecas y Proyecto Integrador en Python


### 1. Introducción a Módulos y Bibliotecas 

Los módulos en Python son archivos que contienen definiciones y declaraciones de Python. Las bibliotecas son colecciones de módulos. Usar módulos y bibliotecas nos permite reutilizar código y aprovechar funcionalidades ya implementadas.

### 2. Importación de Módulos Estándar 
Python viene con una biblioteca estándar rica en módulos útiles. Veremos algunos de los más comunes:

#### 2.1 Módulo `math`

```python
import math

# Uso de funciones matemáticas
print(math.pi)  # Devuelve el valor de π (pi) 3.141592653589793
print(math.e)  # (número de Euler): 2.718281828459045
print(math.sqrt(16))  # Devuelve la raíz cuadrada de (x) 4.0
print(math.pow(2, 3))  # Devuelve x elevado a la potencia de y Salida: 8.0
print(math.cos(0))  # Devuelve el coseno de x, donde x está en radianes. 1.0
print(math.sin(0)) # Devuelve el seno de x, donde x está en radianes.
print(math.ceil(4.2)) # Redondea x al entero superior más cercano. Salida: 5
print(math.floor(4.9)) # Redondea x al entero inferior más cercano. Salida: 4
```

#### 2.2 Módulo `random`

```python
import random

# Generación de números aleatorios
print(random.random())  # Número aleatorio entre 0 y 1
print(random.randint(1, 10))  # Entero aleatorio entre 1 y 10
frutas = ['manzana', 'banana', 'naranja']
print(random.choice(frutas))  # Elemento aleatorio de la lista
```

Ejemplos prácticos:

####  2.2.1 Simulación del lanzamiento de dos dados
```python

import random
dado_1 = random.randint(1, 6)
dado_2 = random.randint(1, 6)
suma = dado_1 + dado_2

print(f"Lanzamiento del dado 1: {dado_1}")
print(f"Lanzamiento del dado 2: {dado_2}")
print(f"Suma de los dos dados: {suma}")
```

####  2.2.2 Generar una contraseña aleatoria
```python
import random

# Simulación de moneda al aire
moneda = random.choice(['cara', 'cruz'])
print(f"Resultado del lanzamiento de la moneda: {moneda}")
```

####  2.2.3 Elegir un elemento aleatorio de una lista
```python
import random

# Lista de frutas
frutas = ['manzana', 'plátano', 'cereza', 'naranja', 'uva']

# Seleccionar una fruta al azar
fruta_seleccionada = random.choice(frutas)
print(f"Fruta seleccionada: {fruta_seleccionada}")
```

####  2.2.4 Generar una contraseña aleatoria
```python
import random
import string
# Definir los caracteres posibles para la contraseña
caracteres = string.ascii_letters + string.digits + string.punctuation

# Generar una contraseña aleatoria de longitud 12
longitud_contraseña = 12
contraseña = ''.join(random.choice(caracteres) for _ in range(longitud_contraseña))

print(f"Contraseña generada: {contraseña}")
```


#### 2.3 Módulo `datetime`

```python
from datetime import datetime, timedelta

# Trabajo con fechas y horas
ahora = datetime.now()
print(ahora)
futuro = ahora + timedelta(days=7)
print(f"Dentro de una semana será: {futuro}")
```

### 3. Instalación y Uso de Paquetes con `pip`

`pip` es el gestor de paquetes de Python. Se usa para instalar bibliotecas que no vienen en la biblioteca estándar.

Instalación de un paquete:
```
pip install nombre_del_paquete
```

Por ejemplo, para instalar pandas, numpy y matplotlib:
```
pip install pandas numpy matplotlib
```

### 4. Uso de Bibliotecas Externas

#### 4.1 Pandas

Pandas es una biblioteca para manipulación y análisis de datos.

#### 4.2 Crear un DataFrame
```python
import pandas as pd

data = {
    'Nombre': ['María', 'Juan', 'Ana'],
    'Edad': [25, 30, 28],
    'Ciudad': ['Quito', 'Guayaquil', 'Cuenca']
}
df = pd.DataFrame(data)

print(df)
print(df['Nombre'])  # Acceder a una columna
print(df.describe())  # Estadísticas descriptivas
```
#### 4.3 Describir datos estadisticos

```python
import pandas as pd

# Crear un DataFrame
datos = {
    'Edad': [30, 25, 22, 29, 35],
    'Altura': [1.75, 1.68, 1.80, 1.60, 1.82]
}

df = pd.DataFrame(datos)

# Obtener resumen estadístico de los datos
print(df.describe())
```

#### 4.2 NumPy

NumPy es una biblioteca para computación numérica en Python.

```python
import numpy as np

# Crear un array
arr = np.array([1, 2, 3, 4, 5])
print(arr)
print(arr * 2)  # Operaciones vectorizadas
print(np.mean(arr))  # Funciones estadísticas
```

#### 4.3 Matplotlib

Matplotlib es una biblioteca para crear visualizaciones estáticas, animadas e interactivas en Python.

```python
import matplotlib.pyplot as plt

# Crear un gráfico simple
x = [1, 2, 3, 4, 5]
y = [2, 4, 6, 8, 10]

plt.plot(x, y)
plt.title('Gráfico Simple')
plt.xlabel('Eje X')
plt.ylabel('Eje Y')
plt.show()
```

### 5. Proyecto Integrador

Vamos a crear un proyecto que integre varias de las bibliotecas que hemos visto. Crearemos un análisis simple de datos climáticos de ciudades ecuatorianas.

```python
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np
from datetime import datetime, timedelta

# Generar datos de ejemplo
np.random.seed(0)
fechas = [datetime(2023, 1, 1) + timedelta(days=i) for i in range(365)]
ciudades = ['Quito', 'Guayaquil', 'Cuenca']
datos = {}

for ciudad in ciudades:
    temperaturas = np.random.normal(loc=25, scale=5, size=365)
    datos[ciudad] = temperaturas

# Crear DataFrame
df = pd.DataFrame(datos, index=fechas)

# Análisis básico
print(df.describe())

# Gráfico de temperaturas promedio
promedios = df.mean()
plt.figure(figsize=(10, 6))
plt.bar(ciudades, promedios)
plt.title('Temperatura Promedio Anual por Ciudad')
plt.ylabel('Temperatura (°C)')
plt.show()

# Gráfico de series de tiempo
plt.figure(figsize=(12, 6))
for ciudad in ciudades:
    plt.plot(df.index, df[ciudad], label=ciudad)
plt.title('Temperaturas Diarias por Ciudad')
plt.xlabel('Fecha')
plt.ylabel('Temperatura (°C)')
plt.legend()
plt.show()

# Análisis estadístico
for ciudad in ciudades:
    print(f"\nEstadísticas para {ciudad}:")
    print(f"Temperatura máxima: {df[ciudad].max():.2f}°C")
    print(f"Temperatura mínima: {df[ciudad].min():.2f}°C")
    print(f"Desviación estándar: {df[ciudad].std():.2f}°C")
```