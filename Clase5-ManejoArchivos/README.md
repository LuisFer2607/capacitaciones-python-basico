# Clase 5: Manejo de archivos y excepciones en Python

### 1. Manejo de archivos en Python 

#### 1.1 Leer y escribir archivos de texto

Python proporciona funciones integradas para leer y escribir archivos de texto. La función `open()` se utiliza para abrir un archivo y devuelve un objeto de archivo.

Ejemplo de lectura de un archivo de texto:

```python
# Leer un archivo de texto
with open('ejemplo.txt', 'r') as archivo:
    contenido = archivo.read()
    print(contenido)

# Leer línea por línea
with open('ejemplo.txt', 'r') as archivo:
    for linea in archivo:
        print(linea.strip())
```

Ejemplo de escritura en un archivo de texto:

```python
# Escribir en un archivo de texto
with open('nuevo_archivo.txt', 'w') as archivo:
    archivo.write('Hola, este es un nuevo archivo.\n')
    archivo.write('Esta es otra línea.')

# Añadir contenido a un archivo existente
with open('nuevo_archivo.txt', 'a') as archivo:
    archivo.write('\nEsta línea se añade al final del archivo.')
```

#### 1.2 Manejo de archivos CSV

Python tiene un módulo `csv` que facilita la lectura y escritura de archivos CSV (Valores Separados por Comas).

Ejemplo de lectura de un archivo CSV:

```python
import csv

# Leer un archivo CSV
with open('datos.csv', 'r') as archivo_csv:
    lector_csv = csv.reader(archivo_csv)
    for fila in lector_csv:
        print(fila)

# Leer un archivo CSV con diccionarios
with open('datos.csv', 'r') as archivo_csv:
    lector_dict = csv.DictReader(archivo_csv)
    for fila in lector_dict:
        print(fila)
```

Ejemplo de escritura en un archivo CSV:

```python
import csv

# Escribir en un archivo CSV
datos = [
    ['Nombre', 'Edad', 'Ciudad'],
    ['Sol', '20', 'Quito'],
    ['Estela', '30', 'Manta'],
    ['Luis', '69', 'Guayaquil']
]

with open('nuevo_datos.csv', 'w', newline='') as archivo_csv:
    escritor_csv = csv.writer(archivo_csv)
    escritor_csv.writerows(datos)

# Escribir un diccionario en un archivo CSV
datos_dict = [
    {'Nombre': 'Sol', 'Edad': '20', 'Ciudad': 'Quito'},
    {'Nombre': 'Estela', 'Edad': '30', 'Ciudad': 'Manta'},
    {'Nombre': 'Luis', 'Edad': '69', 'Ciudad': 'Guayaquil'}
]

with open('nuevo_datos_dict.csv', 'w', newline='') as archivo_csv:
    campos = ['Nombre', 'Edad', 'Ciudad']
    escritor_dict = csv.DictWriter(archivo_csv, fieldnames=campos)
    escritor_dict.writeheader()
    escritor_dict.writerows(datos_dict)
```

#### 1.3 Uso de los modos de apertura (`r`, `w`, `a`)

Python proporciona diferentes modos para abrir archivos:

- `'r'`: Modo de lectura (por defecto)
- `'w'`: Modo de escritura (sobrescribe el archivo si existe)
- `'a'`: Modo de anexado (añade al final del archivo)
- `'r+'`: Modo de lectura y escritura
- `'b'`: Modo binario (se puede añadir a otros modos, por ejemplo, `'rb'` o `'wb'`)

Ejemplos:

```python
# Modo de lectura
with open('archivo.txt', 'r') as f:
    contenido = f.read()

# Modo de escritura
with open('nuevo_archivo.txt', 'w') as f:
    f.write('Este es un nuevo archivo.')

# Modo de anexado
with open('archivo_existente.txt', 'a') as f:
    f.write('\nEsta línea se añade al final.')

# Modo de lectura y escritura
with open('archivo.txt', 'r+') as f:
    contenido = f.read()
    f.write('\nNueva línea al final.')

# Modo binario (útil para archivos no de texto)
with open('imagen.jpg', 'rb') as f:
    datos_binarios = f.read()
```

### 2. Manejo de excepciones

#### 2.1 Gestión de errores con `try`, `except`, `finally`

Python utiliza bloques `try`/`except` para manejar excepciones. El bloque `finally` se ejecuta siempre, independientemente de si se produce una excepción o no.

Estructura básica:

```python
try:
    # Código que puede generar una excepción
    resultado = 10 / 0
except ZeroDivisionError:
    # Manejo de la excepción específica
    print("Error: División por cero")
except Exception as e:
    # Manejo de cualquier otra excepción
    print(f"Se produjo un error: {e}")
else:
    # Se ejecuta si no hubo excepciones
    print("La operación se realizó con éxito")
finally:
    # Se ejecuta siempre, haya o no excepciones
    print("Fin del bloque try/except")
```

Ejemplos prácticos:

```python
# Manejo de excepciones al abrir un archivo
try:
    with open('archivo_inexistente.txt', 'r') as f:
        contenido = f.read()
except FileNotFoundError:
    print("El archivo no existe")
except IOError:
    print("Error de entrada/salida")

# Manejo de excepciones en una función
def dividir(a, b):
    try:
        resultado = a / b
    except ZeroDivisionError:
        print("Error: División por cero")
        return None
    else:
        return resultado

print(dividir(10, 2))  # Imprime: 5.0
print(dividir(10, 0))  # Imprime: Error: División por cero None

# Uso de finally para cerrar recursos
try:
    f = open('archivo.txt', 'r')
    # Operaciones con el archivo
except IOError:
    print("Error al abrir el archivo")
finally:
    f.close()  # Esto se ejecutará siempre, asegurando que el archivo se cierre
```

#### Ejercicio práctico

Crear un programa que lea un archivo CSV con información de estudiantes (nombre, edad, calificación), calcule el promedio de las calificaciones y escriba los resultados en un nuevo archivo de texto. El programa debe manejar posibles excepciones como archivo no encontrado, errores de formato, etc.

```python
import csv

def calcular_promedio(archivo_entrada, archivo_salida):
    try:
        with open(archivo_entrada, 'r') as f_entrada:
            lector = csv.DictReader(f_entrada)
            suma_calificaciones = 0
            count = 0
            
            with open(archivo_salida, 'w') as f_salida:
                f_salida.write("Resumen de calificaciones:\n\n")
                
                for fila in lector:
                    try:
                        nombre = fila['nombre']
                        edad = int(fila['edad'])
                        calificacion = float(fila['calificacion'])
                        
                        suma_calificaciones += calificacion
                        count += 1
                        
                        f_salida.write(f"{nombre} ({edad} años): {calificacion}\n")
                    except ValueError:
                        print(f"Error en el formato de datos para {fila.get('nombre', 'estudiante desconocido')}")
                    except KeyError as e:
                        print(f"Falta la columna {e} en el archivo CSV")
                
                if count > 0:
                    promedio = suma_calificaciones / count
                    f_salida.write(f"\nPromedio de calificaciones: {promedio:.2f}")
                else:
                    f_salida.write("\nNo se pudieron procesar calificaciones")
        
        print("Procesamiento completado. Resultados guardados en", archivo_salida)
    
    except FileNotFoundError:
        print(f"No se encontró el archivo {archivo_entrada}")
    except IOError:
        print("Error de entrada/salida al procesar los archivos")
    except Exception as e:
        print(f"Se produjo un error inesperado: {e}")

# Uso de la función
calcular_promedio('estudiantes.csv', 'resultados.txt')
```
