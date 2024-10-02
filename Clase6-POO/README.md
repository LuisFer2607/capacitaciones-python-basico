# Clase 6: Programación Orientada a Objetos (POO)

### 1. Introducción a la POO en Python 

La Programación Orientada a Objetos (POO) es un paradigma de programación 
que organiza el diseño de software en torno a datos u objetos, en lugar de funciones y lógica. 
Python es un lenguaje de programación orientado a objetos.





Conceptos clave:
- Clase: plantilla para crear objetos
- Objeto: instancia de una clase
- Atributos: características o propiedades de un objeto
- Métodos: funciones que pertenecen a una clase


class coche:
    def __init__(self, color, marca, modelo):
        self.color = color
        self.marca = marca
        self.modelo = modelo
        
    def arrancar(self):
        print(f"Mi carro {self.marca}, que es {self.modelo}, tiene un {self.color}run run run.... ")
    

miCarro = coche("Arcoiris", "Elegante", "Unicornio")


miCarro.arrancar()




### 2. Creación de clases y objetos 

En Python, usamos la palabra clave `class` para definir una clase.

Ejemplo: Creación de una clase `Estudiante`

```python
class Estudiante:
    def __init__(self, nombre, edad, ciudad):
        self.nombre = nombre
        self.edad = edad
        self.ciudad = ciudad

    def presentarse(self):
        return f"Hola, soy {self.nombre}, tengo {self.edad} años y soy de {self.ciudad}."

# Creando objetos (instancias) de la clase Estudiante
maria = Estudiante("María", 20, "Quito")
luis = Estudiante("Luis", 22, "Guayaquil")

print(maria.presentarse())
print(luis.presentarse())
```

En este ejemplo:
- `__init__` es un método especial (constructor) que se llama cuando se crea un nuevo objeto.
- `self` se refiere a la instancia actual de la clase.

### 3. Métodos y atributos 

Los atributos son variables que pertenecen a una clase o instancia. Los métodos son funciones que pertenecen a una clase.

Ejemplo: Ampliando la clase `Estudiante`

```python
class Estudiante:
    universidad = "Universidad Central del Ecuador"  # Atributo de clase

    def __init__(self, nombre, edad, ciudad, carrera):
        self.nombre = nombre  # Atributo de instancia
        self.edad = edad
        self.ciudad = ciudad
        self.carrera = carrera
        self.calificaciones = []

    def agregar_calificacion(self, calificacion):
        self.calificaciones.append(calificacion)

    def promedio_calificaciones(self):
        if self.calificaciones:
            return sum(self.calificaciones) / len(self.calificaciones)
        return 0

    @classmethod #Medo
    def cambiar_universidad(cls, nueva_universidad):
        cls.universidad = nueva_universidad

# Uso de la clase
sol = Estudiante("Sol", 21, "Cuenca", "Ingeniería")
sol.agregar_calificacion(85)
sol.agregar_calificacion(90)

print(f"{sol.nombre} estudia en {Estudiante.universidad}")
print(f"Promedio de calificaciones: {sol.promedio_calificaciones()}")

Estudiante.cambiar_universidad("Universidad San Francisco de Quito")
print(f"Nueva universidad: {Estudiante.universidad}")
```

### 4. Herencia, polimorfismo y encapsulamiento (30 minutos)

#### Herencia

La herencia permite que una clase herede atributos y métodos de 
otra clase.

Ejemplo:

```python

class Persona:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad

    def presentarse(self):
        return f"Hola, soy {self.nombre} y tengo {self.edad} años."

class Profesor(Persona):
    def __init__(self, nombre, edad, materia):
        super().__init__(nombre, edad)
        self.materia = materia

    def presentarse(self):
        return f"{super().presentarse()} Soy profesor de {self.materia}."

fernando = Profesor("Fernando", 45, "Historia")
print(fernando.presentarse())


```

#### Polimorfismo

El polimorfismo permite que objetos de diferentes clases sean tratados 
como objetos de una clase común.

Ejemplo:

```python
class Ave:
    def sonido(self):
        pass

class Gallina(Ave):
    def sonido(self):
        return "Cacareo"

class Pato(Ave):
    def sonido(self):
        return "Cuac"

def hacer_sonido(ave):
    print(ave.sonido())

gallina = Gallina()
pato = Pato()

hacer_sonido(gallina)  # Imprime: Cacareo
hacer_sonido(pato)     # Imprime: Cuac
```

#### Encapsulamiento

El encapsulamiento restringe el acceso directo a los atributos de un objeto.

Ejemplo:

```python
class CuentaBancaria:
    def __init__(self, titular, saldo_inicial, noCuenta):
        self.__titular = titular #Atributo privado
        self.saldo = saldo_inicial
        self.noCuenta = noCuenta  #Atributo Publico

    def depositar(self, cantidad):
        if cantidad > 0:
            self.__saldo += cantidad
            return True
        return False

    def retirar(self, cantidad):
        if 0 < cantidad <= self.__saldo:
            self.__saldo -= cantidad
            return True
        return False

    def obtener_saldo(self):
        return self.__saldo
    

cuenta_emilia = CuentaBancaria("Emilia", 1000, 26862686)

print(cuenta_emilia.saldo)

print(cuenta_emilia.obtener_saldo())  # 1000
cuenta_emilia.depositar(500)
print(cuenta_emilia.obtener_saldo())  # 1500
cuenta_emilia.retirar(200)
print(cuenta_emilia.obtener_saldo())  # 1300

```

En este ejemplo, `__titular` y `__saldo` son atributos privados, accesibles solo dentro de la clase.

### 5. Ejercicio práctico

Crear un sistema simple de gestión de una tienda de artesanías ecuatorianas.

```python
class Artesania:
    def __init__(self, nombre, precio, origen):
        self.nombre = nombre
        self.precio = precio
        self.origen = origen

    def descripcion(self):
        return f"{self.nombre} de {self.origen} - ${self.precio}"

class TiendaArtesanias:
    def __init__(self, nombre):
        self.nombre = nombre
        self.inventario = []

    def agregar_artesania(self, artesania):
        self.inventario.append(artesania)

    def listar_artesanias(self):
        for artesania in self.inventario:
            print(artesania.descripcion())

    def buscar_por_origen(self, origen):
        return [art for art in self.inventario if art.origen.lower() == origen.lower()]

# Uso del sistema
tienda = TiendaArtesanias("Artesanías del Ecuador")

tienda.agregar_artesania(Artesania("Sombrero de paja toquilla", 50, "Montecristi"))
tienda.agregar_artesania(Artesania("Tapiz de Otavalo", 30, "Otavalo"))
tienda.agregar_artesania(Artesania("Cerámica de La Pila", 25, "Montecristi"))

print("Inventario completo:")
tienda.listar_artesanias()

print("\nArtesanías de Montecristi:")
for artesania in tienda.buscar_por_origen("Montecristi"):
    print(artesania.descripcion())
```

Este ejercicio combina los conceptos de clases, objetos, métodos y listas para crear un sistema simple pero funcional.