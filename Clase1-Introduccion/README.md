# 🧑‍🏫 **Clase 1: Introducción**

## 📋 Temas de la Clase

### 1. Presentación personal y objetivos del curso 👨‍🏫
   - Breve introducción sobre el instructor y los objetivos generales del curso.
   - Explicación del enfoque y los resultados esperados al finalizar las capacitaciones.

### 2. Metodología y dinámica del curso 📅
   - Descripción de la estructura de las clases y cómo se desarrollarán los temas.
   - Información sobre las prácticas y actividades durante el curso.
   - Herramientas de evaluación y materiales adicionales.

### 3. Introducción a Python y su entorno (Spyder) 🛠️

#### 3.1 **¿Qué es Python y para qué se utiliza?**

##### Historia breve de Python 🐍
Python es un lenguaje de programación de alto nivel, creado por **Guido van Rossum** y lanzado por primera vez en 1991. Su diseño se enfoca en la legibilidad del código, lo que lo hace accesible tanto para principiantes como para programadores experimentados. Python toma su nombre de la famosa serie de comedia británica "Monty Python's Flying Circus", ya que van Rossum quería un nombre divertido y único para el lenguaje.

> **Dato curioso**: El nombre "Python" no tiene nada que ver con la serpiente. Guido van Rossum era fan del grupo cómico Monty Python, y decidió nombrar el lenguaje en su honor.

##### Áreas donde se utiliza Python 📊
Python es extremadamente versátil y se utiliza en muchas áreas de la tecnología moderna, entre las que destacan:

- **Desarrollo web**: Frameworks como Django y Flask permiten desarrollar sitios y aplicaciones web de manera rápida y eficiente.
- **Ciencia de datos**: Herramientas como Pandas, NumPy y Matplotlib hacen de Python una opción favorita para análisis de datos, visualización y machine learning.
- **Automatización y scripts**: Desde tareas simples como renombrar archivos hasta automatización en redes, Python es excelente para crear scripts que ahorran tiempo.
- **Desarrollo de videojuegos**: Frameworks como Pygame permiten a los desarrolladores crear videojuegos sencillos.
- **Inteligencia Artificial y Machine Learning**: Librerías como TensorFlow y Keras han convertido a Python en el lenguaje de referencia en este campo.

> **Empresas que usan Python**: 
> - Google: Usa Python en muchos de sus sistemas y aplicaciones.
> - Netflix: Utiliza Python para su motor de recomendaciones.
> - Spotify: Emplea Python para su backend y análisis de datos.
> - Instagram: Gran parte de su infraestructura está construida con Python.
> - NASA: Utiliza Python para el procesamiento de imágenes científicas y cálculos complejos.

> **IAs basadas en Python**:
> - GPT (OpenAI): Aunque la interfaz de ChatGPT está en JavaScript, el backend y el entrenamiento del modelo se realizan en Python.
> - BERT (Google): Utiliza TensorFlow, que está basado en Python.
> - Stable Diffusion: Desarrollado utilizando PyTorch, una biblioteca de Python para machine learning.

#### 3.2 **Instalación y configuración de Spyder** 🖥️

##### ¿Qué es Spyder?
Spyder es un entorno de desarrollo integrado (IDE) específicamente diseñado para científicos y analistas de datos que trabajan con Python. Su interfaz es similar a herramientas como MATLAB o RStudio, lo que lo hace ideal para aquellos que necesitan escribir código y realizar análisis de datos en tiempo real.

##### Instalación de Python y Anaconda 🚀
Para poder utilizar Spyder, primero es necesario instalar **Python** o la distribución **Anaconda**. Anaconda es altamente recomendable para principiantes, ya que incluye Python y muchas librerías útiles para ciencia de datos.

###### Paso 1: Instalación de Python
1. **Descargar Python**: Visita la página oficial [python.org](https://www.python.org/) y descarga la última versión de Python para tu sistema operativo (Windows, macOS o Linux).
2. **Instalación**: Durante la instalación, asegúrate de marcar la opción "Add Python to PATH" para que Python se configure correctamente en tu sistema.
3. **Verificación**: Una vez instalado, abre una terminal (o CMD en Windows) y escribe:
   ```
   python --version
   ```

> **Tip**: Si estás en Windows, puedes instalar Python directamente desde la Microsoft Store para una configuración más sencilla.

###### Paso 2: Instalación de Anaconda 🚀

Anaconda es una distribución de Python que incluye todas las librerías y herramientas necesarias para trabajar en ciencia de datos, análisis y programación. Sigue estos pasos para instalar Anaconda:

1. **Descargar Anaconda**: Visita la página oficial de Anaconda [aquí](https://www.anaconda.com/products/individual) y selecciona tu sistema operativo (Windows, macOS o Linux).
2. **Ejecutar el instalador**: Descarga el instalador correspondiente y sigue las instrucciones en pantalla. Asegúrate de seleccionar las opciones por defecto, a menos que se indique lo contrario.
3. **Verificación de la instalación**: Abre una terminal (o "Anaconda Prompt" en Windows) y ejecuta el siguiente comando para verificar que Anaconda se haya instalado correctamente:
   ```
   conda --version
   ```

> **Tip**: Anaconda ocupa bastante espacio en disco. Si tienes limitaciones de almacenamiento, considera instalar Miniconda, una versión más ligera.

##### Instalación de Spyder usando Anaconda ⚙️
Spyder viene preinstalado con Anaconda, pero si necesitas reinstalarlo o instalar una versión específica, sigue estos pasos:

1. **Abrir Anaconda Navigator**: Una vez que Anaconda esté instalado, abre el Anaconda Navigator desde el menú de tu sistema operativo.
2. **Instalar Spyder**: En el Anaconda Navigator, deberías ver Spyder en la lista de aplicaciones disponibles. Si no lo ves, puedes instalarlo desde la terminal:
   ```
   conda install spyder
   ```
3. **Abrir Spyder**: Una vez que esté instalado, haz clic en el botón de "Launch" para iniciar Spyder.

##### Configuración básica de Spyder ⚙️
Una vez que Spyder esté abierto, verás una interfaz dividida en varias secciones:

- **Editor de Código**: Esta es la ventana principal donde escribirás y guardarás tu código Python.
- **Consola**: Aquí se mostrarán los resultados de la ejecución de tu código.
- **Explorador de Variables**: Te permite visualizar las variables que se crean en tu programa, útil para depuración y análisis de datos.
- **Gráficos y Resultados**: Spyder tiene una ventana especial para mostrar gráficos interactivos generados por librerías como Matplotlib.

##### Configuraciones recomendadas
- **Indentación automática**: Ve a Tools > Preferences > Editor y asegúrate de que la opción de indentación automática esté habilitada para mantener un código ordenado.
- **Tema de color**: Puedes cambiar el tema del editor (oscuro o claro) desde Tools > Preferences > Appearance.
- **Explorador de Variables**: Activa el explorador de variables si no lo ves, desde View > Panes > Variable explorer.

> **Tip**: Familiarízate con los atajos de teclado de Spyder. Por ejemplo, F5 para ejecutar todo el script, y F9 para ejecutar la línea o selección actual.

#### 3.3 🐍 Primer programa en Python: "Hello, World!" 👨‍💻
Vamos a escribir nuestro primer programa en Python en Spyder, que imprimirá el mensaje "Hello, World!" en la consola.

##### Pasos para escribir el programa:
1. **Abrir Spyder**: Una vez que Spyder esté configurado, abre el editor de código.
2. **Escribir el código**: En el editor, escribe el siguiente código:
   ```python
   print("Hello, World!")
   ```
3. **Ejecutar el código**: Presiona F5 o haz clic en el botón de "Run" (triángulo verde) en la barra de herramientas.
4. **Observar el resultado**: Verás "Hello, World!" impreso en la consola de Spyder.

> **Dato curioso**: El concepto de un programa "Hello, World!" se originó en 1972 en el libro "The C Programming Language" de Brian Kernighan. Desde entonces, se ha convertido en una tradición para aprender nuevos lenguajes de programación.

> **Tip final**: Practica escribiendo y ejecutando pequeños programas en Python regularmente. La constancia es clave para aprender programación.
