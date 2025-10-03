**Presentación**

  <p align="justify">
En el ámbito de la programación, estamos inmersos en una época en la que todos los días surgen nuevas herramientas y lenguajes de programación capaces de aportar nuevas funcionalidades a los desarrolladores de software. Sin embargo, por mucho que aparezcan estos nuevos lenguajes, siempre hay una constante en el mundo: Python es uno de los principales lenguajes de programación en el mundo. Esta afirmación tan tajante se corrobora con los numerosos rankings de consultoras tecnológicas y repositorios de código, se debe a la gran capacidad que tiene el lenguaje para adaptarse a infinidad de usos: desde un simple servicio desarrollado para su uso por consola, hasta un sistema para generar dashboard tras el análisis de cantidad ingente de datos, pasando por el desarrollo de una interfaz gráfica o la parte front y back de un servicio web. Por ello es muy importante tener las bases del lenguaje muy clara, ya que estamos ante el que se conoce como la navaja suiza de los lenguajes de programación.
  </p>

**Qué es Python**
  <p align="justify">
Python es un lenguaje de programación interpretado de alto nivel, lo que quiere decir que no necesita de un compilador para poder pasar el código para ejecutarlo, sino que lo hace de forma directa línea a línea. Sus primeros usos son de los años 90, pero es en estos últimos años cuando ha cobrado especial importancia gracias a ámbitos de programación como la ciencia de datos y la inteligencia artificial.

El principal objetivo del lenguaje es facilitar la programación, reduciendo la complejidad sin perder potencia. Es un lenguaje fácil de leer y escribir, con una sintaxis clara que se acerca al lenguaje humano, lo que lo convierte en una opción ideal para los principiantes. Su diseño enfatiza la legibilidad del código, lo que mejora la colaboración entre programadores y reduce la probabilidad de errores.

Al tratarse de un lenguaje de alto nivel, abstrae muchas de las complejidades técnicas que otros lenguajes requieren, como la gestión manual de memoria, punteros o trabajo de relación de elementos. Esto permite centrarse en resolver problemas sin preocuparse por detalles como la administración de memoria o la optimización del hardware.

Otra de las características que hacen de Python un lenguaje muy utilizado es su multiparadigma, lo que significa que admite varios estilos de programación, incluidos los enfoques imperativos, orientado a objetos **y** funcional. Esto lo convierte en una herramienta versátil que puede adaptarse a diversos tipos de proyectos y necesidades.
</p>

**Usos de Python**
  <p align="justify">
Python es conocido por su versatilidad y es utilizado en una amplia gama de campos y aplicaciones. Algunos de sus principales usos incluyen:
  </p>
  
* **Desarrollo web**: Python es ampliamente utilizado para construir aplicaciones web utilizando frameworks como Django y Flask.  
* **Ciencia de datos y análisis**: Gracias a librerías como NumPy, Pandas, Python se ha convertido en el lenguaje de referencia para análisis de datos, estadísticas y machine learning.  
* **Automatización**: Muchos programadores usan Python para automatizar tareas repetitivas, como la manipulación de archivos o la interacción con APIs.  
* **Desarrollo de aplicaciones de escritorio**: Python permite crear aplicaciones de escritorio con interfaces gráficas usando bibliotecas como Tkinter.  
* **Inteligencia artificial y aprendizaje automático**: Librerías como TensorFlow y Keras hacen que Python sea el lenguaje predilecto para desarrollar proyectos en IA y ML.  
* **Scripting y administración de sistemas**: Python es utilizado en la administración de sistemas para escribir scripts que gestionen servidores, sistemas de archivos y redes.

**Instalación y configuración del entorno**
  <p align="justify">
Antes de empezar con el desarrollo, uno de los puntos claves es la configuración del entorno de trabajo, su correcta configuración y la elección de los programas que se utilizaran para hacer nuestros códigos. Cuando hablamos de Python, podemos definir dos grandes tipos de entornos, los online y los locales. En el caso de querer ejecutar códigos en la nube para ejecuciones rápidas o comprobación de scripts, se puede utilizar Google Colab, el cual permite ejecutar código muy rápido y sencillo ya que no requiere de ninguna instalación ni configuración previa, simplemente el acceso al recurso web:
  </p>
**Google Colab** representa una magnífica solución para crear apuntes o cuadernos online donde se pueden ubicar los scripts Python para su ejecución en cualquier entorno.

Puedes acceder a él desde el siguiente enlace \<[https://colab.research.google.com](https://colab.research.google.com)\>
  <p align="justify">
En el caso de optar por un servicio local, lo primero que tendremos que instalar es instalar Python como tal, para lo que tendremos que descargar desde la página oficial \<[https://www.python.org](https://www.python.org/)\> el instalador para el sistema operativo correspondiente desde el apartado Download. En el caso de Windows, es **muy importante** que se seleccione la opción Add Python to PATH ya que de esta manera Python quedará configurado como variable de entorno. Por último y antes de la instalación del IDE para poder desarrollar nuestros primeros scripts, podemos comprobar que la instalación se ha realizado de forma correcta si abrimos la terminal o cmd y ejecutamos el siguiente comando:

python –-version // en el caso de windows

python3 –-version // en el caso de macOS

Una vez ejecutado esto y obtenido el número de versión estamos listos para poder instalar y configurar el IDE.
</p>

**Selección del IDE**
  <p align="justify">
Con el entorno preparado, el IDE representa el programa donde se crearán y ejecutarán los script de Python. Como en nuestro caso estamos hablando de un entorno local, existen varias posibilidades como son Visual Studio Code, PyCharm, Jupyter (que aunque también se puede utilizar con código online, su uso puede ser local). Por facilidad de uso y cantidad de extensiones que pueden ayudar a la realización de código, utilizaremos Visual Studio Code.

Para descargar VSC se debe acceder a la página oficial y descargarlo desde la sección download \<[https://code.visualstudio.com](https://code.visualstudio.com)\>

Una vez instalado, el siguiente punto es trabajar con las extensiones. Estas, aportan dentro del IDE una ayuda para el programador de forma que se pueden realizar tareas comunes de forma muy eficiente. Las extensiones recomendadas con las que vamos a trabajar son:

* Python: librería oficial de Microsoft que permite la generación y ejecución de código de forma sencilla  
* Pylance: librería oficial de Microsoft que permite el análisis de código para su correcta ejecución  
* Black Formatter: librería oficial de Microsoft que permite formatear código Python siguiendo los estándares

Con las extensiones instaladas y el IDE instalado, es momento de crear nuestro primer script para poder ejecutar código Python
</p>

**Comprobado que todo funciona de forma correcta**
  <p align="justify">
Una vez creada una carpeta dentro del VSC, podemos crear un fichero pulsando botón derecho \-\> Nuevo archivo y nombrándolo como 01\_inicio.py y escribimos el siguiente código
    
```python
print("Ejecución correcta")
```
Con esto escrito en el fichero, pulsamos el botón ejecutar situado en la parte superior derecha y aparecerá el mensaje “ejecución correcta” en la consola de ejecución. Esto se debe a que el método print() hace referencia a la salida por consola más básica,
</p>
