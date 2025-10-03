

**Índice**

Presentación

1.	Programación orientada a objetos

2.	Conceptos fundamentales	

2.1.	Clases	

2.2.	Atributos	

2.3.	Métodos	

3.	Principios de la POO	

3.1.	Abstracción	

3.2.	Encapsulamiento	

3.3.	Herencia	

3.4.	Polimorfismo	

Conclusiones	

Referencias bibliográficas
	

**Presentación**
<p align="justify">	
En este tema vamos a introducir uno de los paradigmas más utilizados en el desarrollo de software moderno: la programación orientada a objetos (POO). A diferencia de la programación estructurada, la POO permite organizar el código de manera más lógica y modular, simulando cómo funcionan los objetos del mundo real. Trabajaremos paso a paso sus elementos clave: clases, atributos, métodos, encapsulamiento, herencia, polimorfismo y abstracción. Además, aprenderemos cómo aplicar estos conceptos en Python con ejemplos prácticos y casos realistas. El objetivo es que al finalizar este bloque, cualquier estudiante pueda diseñar y construir sus propios programas aplicando correctamente los principios de la programación orientada a objetos. Este contenido no solo es esencial para escribir mejor código, sino también para poder abordar proyectos más complejos y trabajar de forma profesional en cualquier entorno de desarrollo.
</p>

1.  **Programación orientada a objetos** 

<p align="justify">
La programación orientada a objetos, también conocida como POO, es un paradigma de programación que permite organizar el código de forma más estructurada, reutilizable y cercana a cómo entendemos el mundo real. En lugar de pensar en funciones sueltas y bloques de código, la POO se basa en objetos, que son entidades que agrupan datos (atributos) y comportamientos (métodos) en una misma unidad llamada clase.

Este enfoque nos permite modelar elementos del mundo real dentro del programa, de forma que sean mucho más fácil de implementar la idea de ejecución dentro del proyecto. Por ejemplo, si queremos representar un coche, en lugar de usar varias variables sueltas, podemos crear una clase Coche con atributos como color, marca, velocidad, y métodos como acelerar() o frenar() para que todo pertenezca al mismo elemento. De esta manera, el código no solo es más fácil de entender, sino también más mantenible y escalable.

Es evidente que no es obligatorio utilizar el concepto de POO dentro de un código de programación, pero nos aportará las características necesarias para poder afrontar un proyecto grande y que sea mucho más sencillo de ejecutar. Alguna de las características que aporta este paradigma son:

1. Organización del código: agrupa datos y funciones relacionadas en un mismo lugar, perteneciendo estas a un objeto.

2. Reutilización: las clases se pueden reutilizar en diferentes programas o partes de un mismo proyecto, por lo que la cantidad de código que es necesario escribir es muchísimo menor.

3. Facilidad para ampliar: si queremos mejorar o extender una funcionalidad, lo hacemos sobre una clase concreta sin afectar el resto del sistema, mejorando la escalabilidad del sistema.

4. Simulación del mundo real: se modelan objetos como usuarios, productos, vehículos, etc., facilitando la lógica de negocio ya que es más fácil de representar dentro del código de programación .
</p>

2. **Conceptos fundamentales**

Antes de empezar con el código de programación, es básico entender una serie de conceptos que son en los que se basa este paradigma. Son los siguientes 

2.1.  **Clases** 

<p align="justify">	
Las clases representan los elementos o plantillas que se podrán utilizar dentro del código de programación. Podemos decir que son las plantillas con elementos (atributos y métodos) que luego podremos ir moldeando según las necesidades que tengamos a lo largo del programa. Aunque se definirán en los siguientes puntos, tenemos que saber que una clase cuenta con variables, que representan los atributos de un objeto, y métodos o funciones, que representan las acciones que el objeto puede desarrollar. Para poder definir una clase se utiliza la palabra reservada class dentro de un archivo independiente
```python
class Usuario:  
    def __init__(self, nombre, edad, nota):  
        self.nombre = nombre  
        self.edad = edad  
        self.nota = nota
```
El código muestra la creación de una clase llamada usuario que tiene como características un nombre, una edad y una nota. Para poder crear la clase, como se ha dicho es necesario utilizar la palabra reservada class seguida del nombre de la clase y dentro de esta utilizar una función (definiéndola con def) especial que se llama constructor, ya que precisamente lo que permite desde otro módulo es instanciar o hacer realidad un objeto de esta clase. Esta función se llama __init__ y como parámetros siempre tiene la misma estructura: primero el parámetro llamado self que hace referencia al propio objeto y los siguientes parámetros son aquellos atributos que forman parte del objeto. Por ello, dentro de del método se realiza la inicialización como self.nombre = nombre, ya que se iguala la variable de clase nombre con el parámetro pasado llamado nombre

Para poder utilizar este objeto y hacerlo realidad, desde otro fichero se tendría que llamar a este constructor para poder instanciar el objeto y que tuviese una representación en el programa y que pueda ser utilizado.
```python
import objetos

alumno = objetos.usuario("Gilbert", "Martin", 9)  
print(alumno.nombre)
```
A diferencia de otros lenguajes de programación como java o C#,  Pyhton no cuenta con la posibilidad de constructores múltiples, por lo que tan solo se puede utiliza el método __init__ de una forma definida. Lo que si se puede es utilizar el constructor con parámetros por defecto para que se pueda llamar de forma diferente
```python
class usuario:  
    def __init__(self, nombre, edad, *datos, nota=0):  
        self.nombre = nombre  
        self.edad = edad  
        self.nota = nota  
        self.datos = datos  
          
    def mostrar_datos(self):  
        print(f"Nombre: {self.nombre}")  
        print(f"Edad: {self.edad}")  
        print(f"Nota: {self.nota}")  
        for dato in self.datos:  
            print(f"Datos adicionales: {dato}")
```
Como se puede ver, en este constructor se ha utilizado además de un parámetro por defecto nota donde se le asigna un valor de 0 en el caso de no pasar parámetro, un parámetro de tupla llamado datos para que a la hora de crear el objeto se puedan introducir tantos como se consideren necesarios. Además del constructor, las clases donde se definen objetos puede tener definidos tantos métodos como se consideren necesarios, con la restricción de poner como primer parámetro la palabra reservada self para hacer referencia l propio objeto y así poder acceder a cada una de las variables de este. Con esta definición de clases se podría utilizar la siguiente forma de crear objetos:
```python
alumno = objetos.usuario(  
    "Juan",  
    20,  
    "Estudiante de Ingeniería",  
    "Becado por la univeridad",  
    "Convalidaciones en curso",  
    nota=9,  
)  
alumno1 = objetos.usuario("Pedro", 22) # nota=0 y datos=()
```
</p>

2.2.  **Atributos** 

<p align="justify">
Los atributos dentro de una clase representan las características que tiene el objeto y que representan su estado. Estos atributos al pertenecer al objeto, tienen diferentes valores, siempre dependiendo de la creación de este. Para poder crearlos y asignarlos valor, basta con nombrarlos en el constructor __init__ e igualarlos dentro a través del parámetro self.
```python
class empleado:  
    def __init__(self, nombre, puesto, salario=1500, *tareas):  
        self.nombre = nombre  
        self.puesto = puesto  
        self.salario = salario    
```    

Cada uno de los atributos definidos en el constructor se definen como atributos de instancia, ya que pertenecen al objeto.

En el caso de querer ser accedidos dentro del propio objeto, el método que quiera hacer dicha funcionalidad tan solo necesitará del parámetro self para poder acceder a ellos 
```python
    def mostrar_info(self):  
        print(f"Nombre: {self.nombre}")  
        print(f"Puesto: {self.puesto}")  
        print(f"Salario: {self.salario} €")  
```        

Además de los atributos de instancia (recordemos que son aquellos que han sido definidos e igualados en el constructor por medio del parámetro self), también existe lo que se conoce como parámetros de clase. Se trata de aquellos que se definen dentro de la clase pero no se asignan en el constructor vía self, sino que se hace directamente
```python
class empleado:

    contratado = True
```
</p>

2.3.  **Métodos** 

<p align="justify">
Si bien las variables representaban cada uno de los atributos o características del objeto, los métodos representan la funcionalidad que estos podrán ejecutar cuando el método sea llamado. Se definen como una función normal (recordemos que también se pueden utilizar funciones lambda), con tantos parámetros como sea necesario (pudiendo utilizar valores por defecto, valores *args o valores **kwargs). Lo único destacable de los métodos es el uso del argumento self, el cual representa la instancia del objeto donde el método está definido. Su uso es muy importante, ya que permite acceder a todas los atributos y métodos de este, por lo que de forma general siempre se pasará como parámetro en la primera posición.
	
```python
class empleado:

    contratado = True

    def __init__(self, nombre, puesto, salario=1500, *tareas):  
        self.nombre = nombre    
        self.puesto = puesto    
        self.salario = salario    
        self.tareas = tareas  

    def mostrar_info(self):  
        print(f"Nombre: {self.nombre}")  
        print(f"Puesto: {self.puesto}")  
        print(f"Salario: {self.salario} €")  
        print(f"Contradado: {self.contratado}")  
        print("Tareas asignadas:")  
        if self.tareas:  
            for t in self.tareas:  
                print(f" - {t}")  
        else:  
            print(" (Sin tareas asignadas)")
```
En el caso de no pasar como parámetro self, estaremos creando un método de clase, en vez de ser de instancia, por lo que el método no tiene una pertenencia al objeto (recordad que no podrá acceder a los atributos de éste). 

Para poder acceder a cualquiera de estos dos métodos (de instancia y de clase) es necesario tener un objeto de la clase para poder llamarlo:
```python
empleado1 = objetos.empleado("Laura", "Recepcionista")  
empleado1.mostrar_info()
```
La única excepción para que esto no sea necesario, es crear un método estático que pueda ser accesible directamente con la llamada al nombre de la clase. Para ello, antes de definir el método, es necesario agregar un decorador para que el intérprete sepa que ese método es estático
```python
    @staticmethod  
    def mostrar_informacio_estatico():  
        print("Ejecucion directa del método")
```
Y su llamada sería de la siguiente forma
```python   
    objetos.empleado.mostrar_informacio_estatico()
```
En el caso de haber realiza de un método de instancia de la misma forma, obtendríamos un error indicando la falta del parámetro self.
</p>

3.  **Principios de la POO**

<p align="justify">
Como se ha visto, la poo es un paradigma que permite organizar el código de forma modular, diferenciando elementos dentro de este y pudiéndolos tratar de manera independiente. Este modelado del comportamiento de los objetos se debe gracias a los 4 principios de la poo: encapsulamiento, herencia, polimorfismo y abstracción.
</p>

3.1.  **Abstracción** 

<p align="justify">
Uno de los principales principios de la poo es la abstracción, la cual consiste en ocultar los detalles internos de funcionamiento de un objeto y mostrar solo lo necesario para su uso. En programación, esto se consigue mediante la creación de clases que representan conceptos del mundo real con sus atributos (datos) y métodos (comportamientos). Recordemos que una de las potencias y facilidades que ofrece la programación orientada a objetos es la de poder crear un objeto que se asimile a lo que se maneja en la vida real, pudiendo aí proponer e implementar una solución sencilla.
</p>

3.2.  **Encapsulamiento** 

<p align="justify">
Todos los objetos que se crean dentro del código cuentan con propiedades (atributos) y funcionalidades (métodos) que son definidos dependiendo de cuáles son las necesidades que se tienen. El encapsulamiento hace referencia a estos elementos, ya que es el principio por el cual los datos de un objeto se protegen para que no puedan ser modificados directamente desde otra parte del programa. En otros lenguajes, esto es muy sencilla ya que se cuenta con modificadores de acceso que permiten regular esto, pero en Python, al no contar con estos modificadores, solo se puede controlar el acceso a los atributos mediante convenciones y el uso de propiedades. La defincion de la siguiente clase, muestra como un atibuto llamado nota se crea como privado mediante __
	
```python
class estudiante:

    def __init__(self, nombre, nota):  
        self.nombre = nombre  
        self.__nota = nota

    def modificar_nota(self, nueva_nota):  
        self.__nota = nueva_nota

    def mostrar_nota(self):  
        print(f"Nota: {self.__nota}")
```
Además de la definición del atributo, en el caso de querer acceder a él, es necesario un método getter para mostrar su valor. En el caso de querer llamarlo sería de la siguiente forma:
```python
from objetos import estudiante

estudiante = estudiante("Juan", 8)  
estudiante.modificar_nota(10)  
print(estudiante.mostrar_nota())  
print(estudiante.__nota)  # error al declarar la variable como "privada"
```
</p>

3.3.  **Herencia**

<p align="justify">
Nos vamos a detener en este principio. La herencia se conoce como uno de los principales principios ya que permite modelar el código de muy diferentes formas, aprovechando códigos ya realizados.  Cuando hablamos de herencia en programación orientada a objetos, nos referimos a la posibilidad de crear una nueva clase que aprovecha el comportamiento de otra clase existente. Es como si la nueva clase heredara de la clase original todas sus características, y pudiera además añadir las suyas propias o modificar algunas de las heredadas. Esta potencialidad ofrece la posibilidad de reutilizar gran parte de código entre clases. En lugar de repetir ese código común en todas ellas, puedes colocarlo en una clase "padre" o "base", y luego hacer que las clases "hijas" o "derivadas") hereden de ella. Antes de ponernos a programar, es necesario crear un diagrama de clases que muestren estos pasos de elementos entre clases. 

Recuerda:Para poder hacer buenos diagramas UML puedes utilizar herramientas online gratuitas como por ejemplo lucidchart <https://www.lucidchart.com>. Dentro de la herramienta puedes encontrar plantillas para poder hacer los diagramas de clase necesarios.

Una vez creado esto, será más fácil aplicar la herencia. Antes de continuar, es importante decir que en Pyhton, una clase puede heredar de varias clases al mismo tiempo, cosa que en otros lenguajes de programación no es posible. 

Imaginemos un programa que necesita realizar el control de los trabajadores de una empresa, pudiendo diferenciar entre gerente y desarrolladores, donde cada uno de ellos tienen características similares en algunos puntos (nombre y salario), pero diferentes en otros (lenguaje dominante en un Desarrollador y departamento en un Gerente). Según lo comentado, podemos suponer que existirá una clase común entre ambos que represente todas las características y funcionalidades comunes
```python
class Empleado:  
    def __init__(self, nombre, salario):  
        self.nombre = nombre  
        self.salario = salario

    def mostrar_info(self):  
        print(f"Empleado: {self.nombre}, Salario: ${self.salario}")
```
Esta clase base servirá para todas aquellas que tengan las mismas características de nombre, salario y como funcionalidad mostrar_info (sin necesidad de escribirlos en código). El siguiente paso es crear las clases hijas
```python
class Gerente(Empleado):  
    def __init__(self, nombre, salario, departamento):  
        super().__init__(nombre, salario)  
        self.departamento = departamento

    def mostrar_info(self):  
        super().mostrar_info()  
        print(f"Departamento a cargo: {self.departamento}")

class Desarrollador(Empleado):  
    def __init__(self, nombre, salario, lenguaje):  
        super().__init__(nombre, salario)  
        self.lenguaje = lenguaje

    def mostrar_info(self):  
        super().mostrar_info()  
        print(f"Lenguaje de programación: {self.lenguaje}")
```
Si nos fijamos en estas dos clases, a la hora de definirlas es necesario indicar cual es la clase padre de la cual se hereda, indicando esto al lado del nombre de la clase. Desde este punto y sin necesidad de escribir los métodos, ya podríamos acceder a ellos. 

En el caso de querer cambiar el comportamiento de alguno de los métodos es necesario utilizar el operador super(), el cual indica el acceso al elemento declarado en la superclase (lo podemos ver en el método mostrar_info). Este operador se puede utilizar tanto en los métodos como en el constructor, llamando al constructor de la superclase. 

En el caso de querer utilizar los objetos generados en el ejemplo anterior, lo podríamos hacer de la siguiente forma: 
```python
desarollador = Desarrollador("Gilbert", 50000, "Python")  
gerente = Gerente("Laura", 70000, "IT")  
desarollador.mostrar_info()  
gerente.mostrar_info()
```
y la salida del código sería el siguiente

Empleado: Gilbert, Salario: $50000  
Lenguaje de programación: Python  
Empleado: Laura, Salario: $70000

Departamento a cargo: IT

Además de todas estas características, dentro de herencia Python cuenta con una posibilidad que no todos los lenguajes ofrecen: herencia múltiple. Siguiendo el concepto que se ha visto, esto permite que una clase pueda capturar métodos y atributos de una clase (también llamada superclase). Para poder realizar la herencia múltiple tendremos que indicarlo en la firma de la clase hija. Para ello veamos el siguiente ejemplo partiendo de las clases Empleado, Desarrollador y Gerente que desarrollamos anteriormente. En el caso de querer tener un objeto que herede de las dos clases al mismo tiempo, tendríamos que realizar el siguiente código
```python
class DirectorTecnico(Gerente, Desarrollador):  
    def __init__(self, nombre, salario, departamento, lenguaje):  
        Gerente.__init__(self, nombre, salario, departamento)  
        Desarrollador.__init__(self, nombre, salario, lenguaje)

    def mostrar_info(self):  
        super().mostrar_info()    
        print(f"(También programa en: {self.lenguaje})")
```
Como se puede ver, la clase DirectorTécnico ha heredado todas las características de las clases de las que hereda, pudiendo acceder a cada una de ellas mediante la notación del super() o de NombreClase.__init__. La única cosa que se debe tener en cuenta en estos casos es los métodos que tienen el mismo nombre en las clases de las que se hereda. En este caso, el método mostrar_info está presente tanto en Gerente como en Desarrollador, por lo que la pregunta sería: ¿Si llamo a super.mostrar_info(), a que método se hace referencia? En este caso Pyhton utiliza una característica llamada MRO (method resulution order), la cual indica que se capturará el método de la primera clase que es llamada en la firma, siendo en este caso la clase Gerente, por lo que el método mostrar_info haría referencia al de esta clase.

Importante: En Pyhton la sobreescritura de los métodos sigue estando presente (modificar el comportamiento de un método heredado). Sin embargo, no es necesario utilizar ninguna palabra reservada, ya que simplemente basta con definir el método a sobreescribir con el nuevo comportamiento (con la opción de utiliza el super si se quiere reutilizar funcionalidad de la clase superior).
</p>
	
3.4.  **Polimorfismo** 

<p align="justify">	
El último de los principios de la POO es el de polimormismo. Como su nombre indica, esta característica permite a un objeto tomar diferentes formas dependiendo de cuál sea la manera en la que ha sido creado. Para poder aplicar este principio, previamente se ha tenido que realizar una línea de herencia válida, posibilitando a la clase que ha heredado tomar tanto su forma como la forma de la clase padre. Siguiente el ejemplo de las clases desarrolladas podemos ver como poder aplicarlo.
	
```python
class Empleado:  
    def __init__(self, nombre, salario):  
        self.nombre = nombre  
        self.salario = salario

    def trabajar(self):  
        print(f"{self.nombre} está trabajando en tareas generales.")

class Gerente(Empleado):  
    def __init__(self, nombre, salario, departamento):  
        super().__init__(nombre, salario)  
        self.departamento = departamento

    def trabajar(self):  
        print(f"{self.nombre} está gestionando el departamento de {self.departamento}.")

class Desarrollador(Empleado):  
    def __init__(self, nombre, salario, lenguaje):  
        super().__init__(nombre, salario)  
        self.lenguaje = lenguaje

    def trabajar(self):  
        print(f"{self.nombre} está programando en {self.lenguaje}.")

empleados = [  
    Gerente("Ana", 5000, "Marketing"),  
    Desarrollador("Luis", 4000, "Python"),  
    Empleado("Marta", 3000)  
]

for empleado in empleados:  
    empleado.trabajar()
```
Como podemos ver, todas las clases se podrían instancias como su defición:
```python
empleado = Empleado("Carlos", 3000)  
desarollador = Desarrollador("Gilbert", 50000, "Python")    
gerente = Gerente("Laura", 70000, "IT")
```
Sin embargo, como tanto desarrollador como gerente han heredado de Empleado, se pueden juntar en una misma forma y así poder ejecutar un método común, siendo cada una de estas ejecuciones diferentes ya que el método que realmente se ejecuta es el de la clase final
</p>

**Ejercicio:** 
<p align="justify">
Imagina que estás desarrollando un pequeño sistema para una cafetería. El sistema debe permitir registrar distintos tipos de productos que se pueden pedir (por ejemplo, cafés, tés y bollería), llevar un control de los pedidos y calcular el precio total.  Para ello deberás crear una clase Producto con los siguientes datos: Nombre, precio y método mostrar_info Además de esta clase deberás crear tres clases derivadas llamadas  Bebida: con un atributo adicional llamado tipo (string), sobreescribiendo el método mostrar_info Comida: con un atributo adicional llamado caliente (boolean), sobreescribiendo el método mostrar_info Menú: con un atributo adicional llamado completo (boolean), sobreescribiendo el método mostrar_info Por último, crea una clase llamada Pedido, el cual pueda contener tantos productos como el cliente considere necesario, además de un atributo coste total donde se calcule el coste del pedido Puedes generar un par de pedidos con productos dentro o realizar un menú para la gestión de los pedidos.
</p>
	
 **Conclusiones** 

<p align="justify">
A lo largo de este tema hemos aprendido los fundamentos de la programación orientada a objetos en Python. Hemos visto cómo utilizar clases, atributos y métodos para modelar objetos del mundo real, y cómo aplicar principios como la herencia, la encapsulación, la abstracción y el polimorfismo para escribir código más limpio, reutilizable y fácil de mantener. La importancia de la POO radica en su capacidad para organizar el código de forma estructurada, lo cual es fundamental en proyectos medianos y grandes. Gracias a este enfoque, podemos dividir problemas complejos en partes más pequeñas, reutilizar soluciones previas y facilitar el trabajo en equipo dentro de un proyecto. Entender y aplicar correctamente la POO no solo mejora nuestra forma de programar, sino que también nos prepara para usar frameworks y librerías modernas que se basan en este paradigma. Por eso, dominar estos conceptos es un paso clave en la formación como desarrollador.
</p>
	
**Referencias bibliográficas**

* Página web oficial de Pyhton <https://www.python.org>

* Página web oficial de Python < https://docs.python.org/es/3.13/tutorial/classes.html >

