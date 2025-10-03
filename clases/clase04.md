**Índice**

Presentación	

1.	Funciones en Python	

2.	Definición y uso	

2.1.	Uso de parámetros	

2.2.	Tipos de parámetros	

2.3.	Uso de *args y **kwargs	

2.4.	Uso del retorno	

2.5.	Funciones lambda	

3.	Modularidad	

Conclusiones	

Referencias bibliográficas	


 **Presentación** 
<p align="justify">
En este tema vamos a profundizar en dos conceptos fundamentales en la programación estructurada: las funciones y la modularidad. A medida que los programas crecen en tamaño y complejidad, se hace indispensable dividir el código en bloques más manejables y reutilizables. Aquí es donde entran en juego las funciones: nos permiten organizar el código de forma lógica, mejorar su legibilidad y facilitar el mantenimiento.

Además, veremos cómo aplicar el principio de modularidad, que consiste en construir programas dividiéndolos en módulos o partes bien definidas, cada una con una función clara. Este enfoque no solo mejora la calidad del software, sino que también facilita el trabajo en equipo, la depuración de errores y la reutilización del código en diferentes proyectos. A lo largo del tema aprenderemos a crear y utilizar funciones propias, a entender cómo se comunican entre sí, y cómo sacar el máximo partido al diseño modular en nuestros desarrollos.
</p>

1. **Funciones en Python** 

<p align="justify">
Imaginemos que estamos haciendo un programa y ciertas funcionalidades son muy similares, coincidiendo en la mayoría de las líneas de código. Para un programador principiante, escribir dos veces el mismo código en partes diferentes del programa no sopone gran esfuerzo, pero sin embargo cuando el programador va adquiriendo soltura, este tipo de prácticas se hace pesada y nada recomendable. En el día a día, es muy común que tengamos que repetir ciertas acciones o que queramos organizar mejor nuestro código, no solo para que funcione de forma más eficaz, sino también para para que sea más fácil de leer, mantener y reutilizar. Imaginemos un código que debemos mantener tras 1 mes de inactividad, o simplemente leer un código que nos es heredado de otros equipos. Si este está bien realizado y modularizado, la tarea se simplifica en gran medida. En estos casos, las funciones juegan un papel fundamental.

Una función no es más que un bloque de código con un nombre, que se puede ejecutar siempre que se necesite sin necesidad de escribir nuevamente todo el código que se define dentro. La idea es que encapsule una tarea concreta: por ejemplo, mostrar un mensaje, calcular un promedio, validar una entrada, etc. De este modo, en lugar de escribir el mismo código en repetidas ocasiones, podemos definirlo una sola vez en una función y reutilizarlo cada vez que lo necesitemos.

En muchos casos, el código no es siempre el mismo, sino que hay datos que cambian, pero la estructura genera sigue siendo la misma. Es aquí donde entran los parámetros, que no son más que datos de entrada que la función admite para “personalizarla” cada vez que esta es llamada. 

Las funciones, además de ayudarnos a evitar la repetición, también nos permiten estructurar mejor el programa. En vez de tener todo el código seguido, podemos dividirlo en partes pequeñas, cada una con una función clara. Esto hace que nuestro código sea más comprensible, más fácil de mantener y más sencillo de depurar en caso de errores, siguiente uno de los principales dogmas de la informática: divide y vencerás

Otro punto clave es que las funciones también nos permiten trabajar en equipo de forma más organizada. Si varias personas están trabajando en el mismo proyecto, cada una puede encargarse de una parte del código que estará contenida en funciones diferentes. Luego, esas funciones se combinan para crear el programa completo.

En Python, existen funciones que ya están predefinidas, como print() input() len() pero el programador tiene la capacidad de crear las suyas propias e incorporarlas a la funcionalidad del programa.
</p>

2.  **Definición y uso** 

<p align="justify">
Antes de comenzar con las palabras reservadas para definir funciones, vamos hacer un inciso en el nombrado de las mismas. A la hora de nombrar una función en Python, lo más recomendable es utilizar nombres que describan claramente lo que hace. Deben ser lo más claros, específicos y descriptivos posible, evitando abreviaturas confusas o palabras genéricas. Por convención, se usan letras minúsculas y, si el nombre tiene varias palabras, se separan con guiones bajos (_), lo que se conoce como snake_case. Por ejemplo, si una función calcula la media de una lista de notas, un buen nombre sería calcular_media en lugar de algo genérico como funcion1 o mediaNotas. Esto facilita la lectura del código y hace que cualquiera que lo vea pueda entender rápidamente qué hace cada parte.

A diferencia de otros lenguajes, en Python definir una función es muy sencillo ya que al no contar con modificadores de acceso simplemente es necesario utilizar la palabra reservada def, seguido del nombre de la función.
```python
def saludar():  
    print("Hola desde la primera funcion")
```
Cabe recordar, que en el lenguaje no existen las llaves para delimitar el espacio de un bloque, sino que se realiza mediante indentación (4 espacios)

En el caso de querer ejecutar el código que está dentro de la función saludar, simplemente tendríamos que proceder a su llamada, incorporando los paréntesis en la llamada
```python
print("Vamos a prodecer a la llamada de la funcion")  
saludar()
```
</p>

2.1. **Uso de parámetros** 

<p align="justify">
	
Cuando creamos una función, tenemos la posibilidad de incorporar una serie de datos que esta puede tomas como entrada, de forma que se puede personalizar en cierto modo los datos que la función tiene para poder ejecutar. Esto datos toman el nombre de parámetros, y simplemente representan la referencia del elemento para poder utilizarlo dentro de la función, pero hasta que no la función no es llamada, estos argumentos no tienen ningún valor real
```python
def saludar(nombre):  
    print(f"Hola {nombre}, espero que te encuentres bien.")

saludar("Juan")
```
En este caso, función saluda admite un solo parámetro que se ha nombrado como nombre, y al llamarla, será necesario pasarlo dentro de los paréntesis. En este caso la salida sería: “Hola Juan, espero que te encuentres bien”. En el caso de llamar a la función sin pasar un parámetro, obtendríamos un error. 

Al igual que hemos pasado un parámetro, podríamos pasar tantos como nosotros quisiésemos, utilizándolos dentro de la misma función.
```python
def saludar(nombre, apellido, repeticiones):  
    for i in range(repeticiones):  
        print(f"Hola {nombre} {apellido}, espero que te encuentres bien.")

saludar("Juan", "Gomez", 3)
```
En este ejemplo obtendríamos el saludo tres veces, incorporando el apellido dentro de la impresión por consola. 

Se ha comentado antes, que en el caso de no pasar ningún parámetro obtendríamos un error, siempre y cuando no se hayan indicado parámetros por defecto. Esto es una opción dentro del lenguaje, que nos permite asociar un valor a un parámetro siempre y cuando este no sea indicado en la llamada. Siguiendo con el ejemplo del número de saludos, vamos a asociar al parámetro repeticiones un valor por defecto de 1, que será el que se le asigne si en la llamada no se pasa dicho parámetro
```python
def saludar(nombre, apellido, repeticiones=1):  
    for i in range(repeticiones):  
        print(f"Hola {nombre} {apellido}, espero que te encuentres bien.")

saludar("Marta", "Jiménez")
```
En este caso, al igualar el parámetro a uno y en la llamada no pasar un tercer parámetro, el valor que tendrá repeticiones es de 1, obteniendo una única salida por consola. Sin embargo, en el caso de que, si se pase un tercer parámetro en la llamada, el valor que se le asociará es el del parámetro pasado. En este ejemplo vemos como se le asociaría el número 3.
```python
saludar("Marta", "Jiménez", 3)
```
En el caso de querer utilizar parámetros por defecto, es muy importante que éstos sean los que están en la parte final de la función, ya que de lo contrario la llamada de ésta no se podría dar def saludar(nombre=”Juan”, apellido, edad) #Uso incorrecto def saludar(nombre, apellido, edad=18, experiencia=True) #Uso correcto Esto se debe a que la primera función al utilizar parámetros asociados a posiciones es imposible ubicar el segundo parámetro en caso de no indicar el primero. De la misma forma en la segunda función, tan solo será válida en caso de no indicar edad ni experiencia o no indicar experiencia. Lo que no podría darse es no indicar edad pero si experiencia, ya que al igual que antes sería imposible ubicar los parámetros. 

</p>
	
2.2 **Tipos de parámetros** 

<p align="justify">
	
Cuando se crean funciones, hemos podido comprobar que, para poder indicarles un dato de entrada a la función es necesario utilizar los parámetros separados por comas, pudiendo incluso darles un valor por defecto. Este tipo de parámetros se conocen como parámetros posicionales, ya que se asocian a una posición concreta:
```python
def funcionParametros(param1, param2, param3):  
    print(f"param1: {param1}, param2: {param2}, param3: {param3}")

funcionParametros("valor1", "valor2", "valor3")
```
En este caso param1 se asocia al “valor1”, param2 al “valor2” y param3 al “valor3”, ya que así se ha indicado en cada una de las posiciones de la llamada. Sin embargo, para poder mejorar la forma en la que se lee una función y al final la manera en la que se interpreta el código, es posible el uso de parámetros nombrados. Para ello, simplemente hay que sustituir las posiciones por el nombre del parámetro en concreto. Siguiendo el ejemplo anterior y utilizando parámetros nombrados en este caso, obtendríamos el siguiente código
```python
funcionParametros(param1="valor2", param2="valor3", param3="valor1")
```
De esta forma, queda bastante más claro cuál es el dato asociado a cada uno de los parámetros

</p>
	
2.3 **Uso de args y kwargs**

<p align="justify">
	
En algunas ocasiones, es necesario pasar por parámetros un numero indeterminado de datos, por lo que el uso tanto de parámetros posicionales como de parámetros nombrados no es posible. Imaginemos una función que me permite calcular la media de una serie de números, pero no se sabe cuántos son ni tampoco están ubicados en una estructura de datos. En este caso sería necesario utilizar como parámetro *args, el cual convierte a todos los parámetros pasados en una tupla (no mutable) para poder utilizarla dentro de la función. Veamos el siguiente ejemplo:
```python
def calculo_media(*notas):  
    media = 0.0  
    print(f"Procedo a calcular la media de {len(notas)} notas")  
    for i in notas:  
        media += i

    media = len(notas)  
    print(f"La media obtenida es de : {media}")

calculo_media(1, 5, 7, 3)  
calculo_media(4, 9, 6)
```
En este caso, al utilizar un *args cuando se llama a la función se pueden pasar tantos parámetros como se quieran.

La salida obtenida de la ejecución del código sería la siguiente:

Procedo a calcular la media de 4 notas  
La media obtenida es de : 4.0  
Procedo a calcular la media de 3 notas  
La media obtenida es de : 6.333

Otro de las posibilidades es utilizar los parámetros *kwargs. Su uso es muy similar al anterior, con la diferencia que los elementos indicados como parámetros (pueden ser tantos como se quieran) deben ser nombrados y se convertirán en diccionario dentro de la función. Veamos el siguiente ejemplo
```python
def imporatar_usaurio(**kwargs):  
    print("Los datos pasados del usuarios son:")  
    for key, value in kwargs.items():  
        print(f"{key}: {value}")

imporatar_usaurio(nombre="Juan", apellido="Gomez", edad=25, ciudad="Madrid")
```
Cada uno de los parámetros nombrados en la función se convierten en parte de un diccionario, donde la clave es el nombre del parámetro y el valor el dato asociado. La salida de la ejecución del código anterior sería la siguiente

Los datos pasados del usuarios son:  
nombre: Juan  
apellido: Gomez  
edad: 25  
ciudad: Madrid

Esta característica es bastante útil cuando la información que se debe pasar a la función no siempre es la misma, teniendo la función la capacidad de convertir todos los datos pasados en una misma estructura. Ambos todos de parámetros se pueden combinar, lo único a tener en cuenta es el orden de los parámetros, ya que se debe guardar la nomenclatura de cada uno de los elementos, siendo *args posicionales y * kwargs nombrados. Un ejemplo sería la siguiente función
```python
def suma_mixta(*args, **kwargs):  
    suma = 0  
    for i in args:  
        suma += i  
    print(f"La suma de los argumentos es: {suma}")  
    for key, value in kwargs.items():  
        print(f"{key}: {value}")

suma_mixta(  
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, proyecto="Sumatorio", unidad="2", curso="python"  
)
```
En este caso los parámetros que son posicionales se quedan asociados a la tupla args, mientras que los que son nombrados forman parte del diccionario kwargs. Es importante decir que después del parámetro *kwargs no se puede definir ningún otro tipo de parámetro.

</p>
	
2.4. **Uso del retorno**

<p align="justify">
	
Además de poder ejecutar todo el código que se ubica dentro del bloque de la función, ésta puede retornar un valor determinado para que sea utilizado en aquellos sitios que sea necesario. Para poder indicar el tipo de retorno tan solo es necesario poner como última línea del método la palabra return, acompañada del dato que se quiera retornar para así poder utilizarlo en la llamada de la función. Veamos un ejemplo:
```python
def procesar_informe(*datos):  
    print("Los datos se han recibido correctamente")  
    if len(datos) > 0:  
        return f"Nombre {datos[0]}nApellido {datos[1]}"  
    elif len(datos) > 2:  
        return "Cantidad de datos incorrecta"  
    else:  
        return "No se han recibido datos"  
print(procesar_informe("Borja", "Martinez"))
```
En este caso la llamada a la función procesar_informe retorna un string con los datos pasados por parámetros en el caso de ser 2 (recordar que el parámetro *args es una tupla). En caso contrario retornara o “cantidad incorrecta” o “no se han recibido datos”. Una vez llamada la función, al obtenerse el string, este puede ser utilizado desde cualquier parte, como por ejemplo dentro de una función print() como en el ejemplo.

</p>
	
2.5.  **Funciones lambda**

<p align="justify">


   Con lo visto hasta aquí, ha quedado claro que para poder definir una función es necesario el uso de la palabra reservada def así como el uso de opcional de parámetros y argumentos para poder escribir una función válida. Sin embargo, existe otro dipo de función que tiene la misma validez y realiza la misma ejecución pero que es más simple de crear. Su nombre es el de funciones lambda, funciones de flecha también llamadas funciones de flecha. Reciben este nombre porque no es necesario asociarle nombre alguno, simplemente es necesario igualarlo a una variable o definirla como parámetro dentro de una función. 

   Para poder crear un tipo de estas funciones se utiliza la palabra reservada lambda acompañada de los parámetros y el cuerpo de la función separado por : . Como se ha dicho antes, generalmente este tipo de funciones se asocia a una variable para que, al ser llamada, se ejecute la función lambda definida. Veamos un ejemplo:
```python
# definición normal de la función  
def suma(a, b):  
    return a + b

# definición y uso de una función lambda  
sumaVar = lambda a, b: a + b  
print(sumaVar(7, 9))

Esta forma de utilizar las funciones es bastante útil, pero cobra especial relevancia cuando se utiliza como parámetro dentro de otra función:

alumnos = [("Ana", 7), ("Luis", 5), ("Pedro", 9)]  
ordenados = sorted(alumnos, key=lambda x: x[1])  
print(ordenados)
```
En este caso, la función lambda indicada en el parámetro key, indica que la forma de ordenación que tendrá la tupla es sobre la primera posición del elemento, es decir sobre la nota.

</p>
	
3.  **Modularidad**

<p align="justify">


Cuando un programa empieza a crecer y tener muchas líneas de código, se vuelve cada vez más difícil de leer, mantener y reutilizar. Para evitar que todo quede mezclado en un solo archivo enorme, existe un concepto muy importante en programación: el modularidad**.** La idea de ésta es muy sencilla: dividir el programa en partes más pequeñas y organizadas, que se puedan trabajar por separado y luego juntar cuando sea necesario. En Python, esto se consigue gracias a los módulos.

Un módulo en Python no es más que un archivo .py que contiene funciones, variables o clases, y que se puede usar desde otros archivos. Esto te permite, por ejemplo, tener un archivo con todas las funciones matemáticas que usas, otro con validaciones, otro con menús, etc. Para poder utilizar esta funcionalidad es necesario cumplir dos cosas:

1. Que el archivo que se quiera utilizar está completo y no tenga ningún fallo de codificación

2. Que el archivo donde queremos utilizar el módulo definido en el punto 1 incorpore como primera línea la palabra reservada import. Esto hará que se importe todo el contenido del fichero y pueda ser utilzado en el fichero actual. En el caso de querer importar solo parte del fichero se utilizará la nomenclatura from nombre__modulo import nombre_funcion

Vamos a ver un ejemplo el código:

En el fichero operaciones.py incorporamos todas las operaciones matemáticas que queremos ejecutar a lo largo de nuestro programa
```python
def sumar(a, b):  
    return a + b

def restar(a, b):  
    return a - b

def multiplicar(a, b):  
    return a * b

def dividir(a, b):  
    if b == 0:  
        return "Error: no se puede dividir entre cero."  
    return a / b

def potencia(base, exponente):  
    return base ** exponente

def raiz_cuadrada(x):  
    if x < 0:  
        return "Error: no se puede calcular la raíz de un número negativo."  
    return x ** 0.5
```
Una vez tenemos el fichero que realiza todas las operaciones, vamos a crear otro fichero llamado calculadora.py que pide al usuario dos operandos y realiza las operaciones sobre estos, pero llamando a las funciones ya definidas en el módulo anterior:
```python
import operaciones

operando1 = int(input("Introduce el operando 1: "))  
operando2 = int(input("Introduce el operando 2: "))  
operacion = input("Indica la operación a realizar: ").strip()  
print(operacion)

if operacion == "suma":  
    resultado = operaciones.sumar(operando1, operando2)  
elif operacion == "resta":  
    resultado = operaciones.restar(operando1, operando2)  
elif operacion == "multiplicacion":  
    resultado = operaciones.multiplicar(operando1, operando2)  
elif operacion == "division":  
    resultado = operaciones.dividir(operando1, operando2)  
elif operacion == "potencia":  
    resultado = operaciones.potencia(operando1, operando2)  
elif operacion == "raiz":  
    resultado = operaciones.raiz_cuadrada(operando1)  
else:  
    resultado = None

print(f"El resultado de la operación es: {resultado}")
```
En el caso de solo querer importar alguna de las funciones se utilizaría como primera from X import X, ya no siendo necesaria la llamada al módulo dentro del código:
```python
from operaciones import sumar, restar, multiplicar, dividir, potencia, raiz_cuadrada

operando1 = int(input("Introduce el operando 1: "))  
operando2 = int(input("Introduce el operando 2: "))  
operacion = input("Indica la operación a realizar: ").strip()  
print(operacion)

if operacion == "suma":  
    resultado = sumar(operando1, operando2)  
elif operacion == "resta":  
    resultado = restar(operando1, operando2)  
elif operacion == "multiplicacion":  
    resultado = multiplicar(operando1, operando2)  
elif operacion == "division":  
    resultado = dividir(operando1, operando2)  
elif operacion == "potencia":  
    resultado = potencia(operando1, operando2)  
elif operacion == "raiz":  
    resultado = raiz_cuadrada(operando1)  
else:  
    resultado = None

print(f"El resultado de la operación es: {resultado}")
```
En estos ejemplos hemos visto como poder importar un módulo creado por nosotros mismo, pero también existe la posibilidad de importar módulos del sistema o descargados para poder utilizar funcionalidades que ya están presentes en el lenguaje. Un ejemplo de uso de de módulos importados desde el sistema sería el siguiente:
```python
import datetime  
now = datetime.datetime.now()  
print("Fecha y hora actual:", now)

date = datetime.datetime(2025, 5, 15)  
print("Fecha personalizada:", date.strftime("%d/%m/%Y"))
```
En este ejemplo se ha importado el módulo datetime que se encargad de la gestión de fechas, utilizando el método datetime.now para obtener la fecha actual y el constructor datetime para crear una fecha concreto así como el método srtftime para poder formatear una fecha.

</p>
	
**Ejercicio**

<p align="justify">


Realiza el siguiente ejercicio para practicar lo visto en esta unidad: Crea un programa en Python que permita gestionar una lista de productos de una tienda. El programa debe utilizar funciones para realizar las siguientes operaciones: Agregar productos con su nombre y precio. Mostrar todos los productos disponibles. Buscar un producto por su nombre y mostrar su precio. Calcular el precio total de todos los productos. Organiza tu código en funciones separadas para cada una de estas acciones. El usuario debe poder elegir qué hacer mediante un menú simple. Además, tendrás que utilizar estructuras de control como listas para poder almacenar todos los productos 

**Conclusiones**

Como hemos podido comprobar, el uso de funciones y la aplicación del diseño modular son herramientas clave para escribir programas más eficientes, ordenados y fáciles de mantener. Saber dividir un problema en partes más pequeñas y tratables no solo nos permite trabajar de manera más estructurada, sino también comprender mejor el código que escribimos y detectar errores con mayor facilidad.

Dominar estos conceptos nos prepara para afrontar proyectos complejos, donde la claridad y la reutilización del código son esenciales para poder llevar a buen puerto el proyecto. Además de esto, nos acerca a las buenas prácticas de programación que se utilizan en el mundo laboral, haciendo que nuestros programas sean más robustos y escalables. 

</p>
	
**Referencias bibliográficas**

* Página web oficial de Pyhton <https://www.python.org>

* Página web oficial de Pyhton sobre modularidad <[https://docs.python.org/es/3.13/tutorial/modules.html:contentReference[oaicite:0]{index=0}](https://docs.python.org/es/3.13/tutorial/modules.html:contentReference%5Boaicite:0%5D%7Bindex=0%7D)>

* Página web oficial de Pyhton sobre funciones <https://docs.python.org/es/3.13/library/functions.html>

