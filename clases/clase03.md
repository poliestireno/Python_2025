**Estructuras de control y datos**  
**Presentación**  
En programación, rara vez un código se ejecuta de manera secuencial línea por línea sin necesidad de tomar decisiones o repetir partes del código. Las estructuras de control permiten que un programa pueda "elegir" distintos caminos de ejecución y repetir acciones automáticamente, lo que resulta en un código más eficiente y manejable. Además de las estructuras de control, las estructuras de datos permiten albergar en una sola variable un conjunto de elementos para poder accederlos de forma única. Dependiendo de las características de nuestro código, podremos utilizar listas, tuplas, diccionarios o conjutos  
  **1. Control del flujo**  
Si tenemos que hacer un código de programación, pocas veces debe tener una ejecución secuencial línea a línea, sin tener que realizar decisiones dependiendo de una condición lógica o repetir partes de este para ahorrar código. Es aquí donde entran las estrucutras que permiten controlar el flujo del programa, haciendo que éste pueda “elegir” distintos caminos de ejecución y repetir acciones de forma automática. Gracias a ellas ya no estaremos obligados a crear un flujo instrucciones secuencial y podremos tener la capacidad de tomar decisiones, iterar sobre datos y construir códigos mucho más potenter. Estas estructuras son de gran importancia debido a los siguientes aspectos:  
* Permiten la toma de decisiones mediante las estructuras condicionales y/o de selección como son if – if/ else – if / else if /else
* Permiten la repetición automática de código iterando sobre una colección o sobre una condición lógica mediante las estructuras de repeción como son for – while – do/while  
* Agregar claridad y facilidad de mantenimiento al código gracias a su capacidad de modulares partes de éste, haciéndolo más comprensible y gestionable  
­Separar bien las secciones de decisión y de iteración ayuda a estructurar el código, facilita su lectura y reduce errores a la hora de ampliar o corregir un programa.  

Antes de empezar a ver cada una de las estructuras, es muy importante recordar que en Python no se usan llaves para delimitar bloques de código (como en Java, C# o JavaScript). En lugar de esto, el bloque se marca con la indentación (una tabulación). Es decir, el bloque que pertenece a un if, un for, un while, una definición de función, etc., debe escribirse con sangría (4 espacios) para indicar que esa parte del código pertenece al bloque. Cuando la indentación vuelve al nivel anterior, el bloque termina. A continuación podemos ver un ejemplo:
```python
edad = 10  
if edad < 18:  
    print("El usuario es mejor de edad")  
elif edad < 65:  
    print("El usuario está en edad labora")  
else:  
    print("El usuario que ha ganado la jubilacion")

print("Mensaje ejecutado fuera de bloque")
```
**1.1. Estructuras de selección**  
Este tipo de estructura es la más sencilla dentro de Python, ya que permite indicar cual es la parte de código que se debe ejecutar dependiendo de un valor o condición lógica. Entre estas estructuras podemos encontrar  
  **1.1.1. If – if/else – if/elif/else**

Cuando queramos que nuestro programa tome decisiones en tiempo de ejecución, utilizaremos la estructura if ya que, gracias a ella, Python podrá ejecutar un bloque u otro en función de si se cumple o no una condición booleana. En este caso tendremos la posibilidad de utilizar una sola condición (if), dos (if/else) o varias (if – elif – else), teniendo en cuenta que solo una de ellas podrá ser la correcta, y en el caso de cumplirse una, el resto no se analizarán. A continuación, podemos ver un ejemplo de esta estructura combinando diferentes if  
numero = int(input("Por favor introduce el valor numérico que quieres evaluar "))
```python
if numero<0 or numero>=100:  
    if numero<10:  
        print("valor entre 0 y 10")  
    elif numero<100:  
        print("valor de 2 cifras mayor que 100")  
else:  
    print("Valor no válido")
```
**1.1.2. Match**

En el caso de querer ejecutar un código directamente asociado al valor de una variable, la estructura if puede resultar muy tediosa. Para ello, es recomendable utiliza la estructura Match la cual evalua el valor de una variable y ejecuta de forma directa el caso correspondiente, pudiendo seleccionar un caso por defecto utilizando el carácter _

Importante: La estructura de control match tan solo funciona de Python 3.10 en adelante

A continuación, podemos ver un ejemplo de esta estructura combinando con la estructura if  
opcion = input("Selecciona una opción (1, 2, 3):")  
```python
match opcion:  
    case "1":  
        print("Has seleccionado la opción 1: Ver perfil.")  
    case "2":  
        print("Has seleccionado la opción 2: Editar perfil.")  
    case "3":  
        print("Has seleccionado la opción 3: Cerrar sesión.")  
    case _:  
        print("Opción no válida. Inténtalo de nuevo.")
```
**1.2. Estructuras de repetición**

Otro tipo de estructuras muy utilizadas son las de repetición. Éstas no permiten realizar ejecución de bloques de código recurrente sin necesidad de escribir n veces las mismas líneas. Son muy útiles para recorrer colecciones de datos o para ejecutar recursivamente una función sobre una condición lógica  
**1.2.1. For**  
La primera opción dentro de las estructuras de repetición es la del for. Esta estructura permite ejecutar un bloque de código en un rango determinado (indicando un incremento). Para ello se utiliza el método range(), pasando como parámetros el valor inicial, final e incrementeo del código. En cada iteración, la variable definida tomará un nuevo valor:  
```python
for i in range(1,10,3):  
    print(i)
```
En este caso la salida sería 1,4,7 que que se ha indicado un incrementeo de 3. En el caso de querer hacer un decremento sería con un range a negativo  
```python
for i in range(10,1,-3):  
    print(i)
```
Otra de las opciones es indicar una colección de datos en vez del método range, pudiendo así asignar a la variable creada cada uno de los elementos de la colección. Para ello, la colección se puede indicar de forma interna en la estructura o crearla fuera y nombrarla en la estructura  
```python
for i in [1,2,3,4,5,6,7,8,9,10]:  
    print(i)

alumnos = ["Juan","Maria", "Jorge","Claudia", "Marcos","Celia"]  
for i in alumnos:  
    print(i)

# donde i va tomando los valores de la coleccion
```
Nota

Dentro de la estructura de control, se pueden utilizar tantas estructuras como sean necesarias, incluso anidar el mismo tipo de estructura.
```python
for i in range(1,10):  
    print(f"Tabla del {i}")  
    for j in range(1,10):  
        print(f"{i}*{j}={i*j}")
```
**1.2.2. While**
Esta estructura de control permite repetir un bloque de código dependiendo de una condición lógica. Una de las cosas importante cuando se utiliza este tipo de estructura, es que antes de ejecutar el bloque, se analiza la condición de repetición, por lo que puede no llegar a ejecutarse nunca

Importante: La condición de evaluación tiene que cambiar en algún momento. De no ser así, el bloque de repetición entrará en un bucle infinito a no ser que se aplique un break

Un ejemplo del uso de la estructura sería la siguiente  
```python
contador = 1

contador = 1  
while contador <= 5:  
    print("Valor:", contador)  
    contador += 1   
print("Saliendo del bloque while")
```
Como podemos ver, el bloque se repetirá siempre y cuando la variable contador sea inferior o igual a 5. Dentro del bloque es importante lo que comentábamos de modificar dicha condición para que pueda salir de la ejecución. Si hacemos un ejemplo más cercando al mundo informático, podemos utilizar un bloque while para dejar la aplicación bloqueada hasta realizar un login correcto:
```python
nombre = input("introduce el nombre del usuario")  
password = input("introduce la pass del usuario")

while nombre != "admin" or password != "admin":  
    print("Login incorrecto")  
    nombre = input("introduce el nombre del usuario")  
    password = input("introduce la pass del usuario")

print("Login correcto, puedes continuar")
```
**Nota**

En Pyhton no existe la estructura de control do-while. Sin embargo podríamos similar su uso con un while (true) y un break en el caso de no cumplir la condición correspondiente.
```python
while True:  
    numero = int(input("Introduce la opción a mostrar:"))  
    if numero == 7:  
        print("Has seleccionado la opción de salir")  
        break  
    print("Vuelve a seleccionad una opción.")  
print("Saliendo el ")
```
**2. Estructuras de datos**
Cuando hablamos de variables en un lenguaje de programación, nos referimos a la capacidad del lenguaje a guardar un dato para utilizarlo a posteriori bien sea referenciándolo para acceder al valor guardado o para poder modificarlo. En el caso de querer guardar más de un valor, la primera posibilidad es utilizar más de una variable, pero en algunos casos esta no es la mejor opción, siendo las estructuras de datos la solución. Es por tanto que las estructuras de datos representan un conjuto de datos guardados en una misma unidad. Las estructuras principales dentro de Python son list, tuplas, diccionarios y conjunto o set.  
**2.1. List**
Una lista de datos, es una estructura de datos ordenada, lo cual quiere decir que los elementos están asociados a posiciones siendo el 0 la primera, y mutable de elementos los cuales pueden ser de cualquier tipo. Para poder crear una lista se utilizan []
```python
listaElementos = ["Elemento1", "Elemento2", "Elemento3"]
```
Las acciones que se pueden hacer sobre estos elementos son: 
1. Acceder a un dato: utilizando la posición del elemento se puede acceder a él indicando el índice.  
```python
print(listaElementos[0])
```
2. Modificar un dato: utilizando la posición del elemento que se quiere modificar e igualando al nuevo valor que se quiere asociar.  
```python
listaElementos[0] = "Elemento1 modificado"
```
3. Agregar un elemento: como se trata de una estructura mutable en cualquier momento se pueden agregar elemento, haciéndolo en la última posición de la lista.  
```python
listaElementos.append("Elemento nuevo")
```
4. Agregar un elemento en una posición determinada: muy similar al caso anterior, pero indicando la posición donde se agrega. El resto de los elementos de la derecha, se moverán una posición.  
```python
listaElementos.insert("Elemento adicional", 1)
```
5. Eliminar un elemento: indicando el valor del elemento que se quiere borrar, la lista eliminará el primer elemento que coincida con el valor indicado. El resto de elemento de la derecha se moverán una posición.  
Existe también la posibilidad de eliminar el elemento indicando la posición que se quiere borrar  
```python
listaElementos.remove("Elemento1")  
del listaElementos[0]
```
Estas son las acciones básicas sobre una lista, pero también podemos utilizar alguno de los métodos asociados para acceder a acciones avanzadas  
1. Iterar sobre los elementos: para ello es necesario utilizar la estructura de control for, obteniendo cada uno de los elementos de la colección de uno en uno.  
```python
for item in listaElementos:  
    print(item)
```
2. Obtener la posición de un elemento: Para ello se utiliza el método index(), retornando la posición del valor indicado. En el caso de no encontrarlo se retorna un ValueError  
```python
listaElementos.index("Elemento2")
```
3. Filtrar elemento: no se trata de un método como tal, sino una concatenación de sentencias de control, utilizando el for y el if de forma conjunta  
```python
p = [p for p in listaElementos if "2" in p]
```
4. Ordenar una lista: utilizando el método sort(), pudiendo indicar entre los paréntesis la condición de ordenación  
```python
listaElementos.sort(key=len)
```
Importante: En Python se puede acceder a la posición de un elemento a través de de posiciones negativas, siendo el elemento en la posición -1 el último elemento de la lista, el -2 el antepenúltimo y así sucesivamente.

**Ejercicio**
Realiza el siguiente ejercicio para practicar las listas:  
Crea una aplicación en consola donde se permitan gestionar las calificaciones de la asignatura. Para ello, mediante un menú permite las siguientes acciones  
    • Introducir notas: el usuario introducirá notas hasta que meta un -1. Esto indicará que la introducción ha terminado. Una vez realizado esto volverá a aparecer el mené  
    • Listar notas: se mostrarán todas las notas de una en una.  
    • Obtener extremos: se mostrarán la nota más alta y baja.  
    • Obtener información: se mostrarán los siguientes datos sobre las notas: total introducidas, número suspensos, número aprobador, nota media

**2.2. Tuplas**
Las tuplas son una estructura de datos muy similar a las listas apartado anterior con la diferencia que son no mutables, es decir que no pueden alterar su tamaño (no se puede ni agregar elementos y eliminarlos). Para poder crear una tupla se indican los elementos que forman parte de ella
```python
trabajadores = ("Juan", "Patricia", "Maria")
```
Los métodos de acceso, modificación de valor, obtención de longitud y recorrido son idénticos a los vistos en las listas, siendo la diferencia la no posibilidad de agregar elementos y los paréntesis a la hora de crear la colección.

Nota: Es posible desempaquetar una tupla, o lo que es lo mismo crear variables asignándolas de forma directa a los elementos que forman parte de esta.  
```python
  datos = ("Ford", "Mustang", 2025, 500, 60000)  
  marca, modelo, anio, cv, precio = datos
```
En las listas también existe esta posibilidad, pero al ser una colección dinámica el uso es más marginal (se puede utilizar el * al lado de la variable para indicar la extracción de la parte parcial de la lista)

**2.3. Diccionarios**
Otra de las posibilidades a la hora de utilizar la colección de datos son los diccionarios. A diferencia de las vistas, los diccionarios me permiten no solo meter datos en una colección mutable, sino que lo hacen relacionando una clave a un valor. Para la creación de un diccionario realizaremos 
```python
trabajador = {  
    "nombre": "Celia",  
    "edad": 23,  
    "especialidad": "Informática",  
    "titulación": "Ingeniería",  
    "conocimientos": ["Programación", "Sistemas", "BigData"]  
}
```
Con esta forma de gestionar los datos, podemos jerarquizar la información, accediendo a ella a través de su clave asociada. A la hora de asignar claves, lo que tenemos que tener en cuenta es lo siguiente: no pueden ser mutables (un string, int, float, bool) y deben ser únicas (una clave no puede ser duplicada en un mismo diccionario). Los principales métodos que se utilizan en este tipo de colecciones son los siguientes:  
   
1. Acceso a elementos: Para poder acceder a un elemento de un diccionario, se utiliza la clave asociada. También se puede utilizar el método get para el acceso
```python
print(trabajador["nombre"])
```
2. Modificar elementos: Muy similar al acceso del elemento, con la diferencia que hay que indicar el nuevo valor de este  
```python
trabajador["edad"] = trabajador["edad"]+1
```
3. Eliminar elementos: Para poder eliminar un elemento del diccionario se utiliza la función del, indicando cual es el elemento que se quiere eliminar  
```python
del trabajador["titulación"]
```
4. Añadir elementos: En el caso de querer añadir un elemento que no exista en el diccionario, se indica la clave y el valor que tendrá.   
```python
trabajador["especialidad"] = "Inteligencia artificial"
```
5. Recorrer elementos: Utilizando la estructura de control for podemos acceder a las claves del diccionario, y una vez tenemos esta acceder elementos de forma iterativa  
```python
for item in trabajador:  
    print(f"{item}: {trabajador[item]}")  
    if item == "conocimientos":  
        for c in trabajador[item]:  
            print(f"t{c}")
```
Además de estas acciones, se pueden utilizar funciones avanzadas

1. Obtener todos los elementos: para ello se utiliza el método values  
```python
for item in trabajador.values():  
    print(item)
```
2. Obtener todas las claves: para ello se utiliza el método keys  
```python
for item in trabajador.keys():  
    print(item)
```
3. Saber si un elemento está dentro del diccionario: para ello se evalúa mediante el operador in
**2.4. Conjuntos**
La última de las colecciones que veremos son los conjuntos o set. Estas colecciones son muy similares a las listas, con la diferencia que no se permiten elementos duplicados y además son no ordenadas. Para poder definir un conjunto se utilizan las llaves o la función set:
```python
numeros = {1, 2, 3}  
numerosSet = set([2, 3, 4])
```
ImportanteEn caso de tener elementos duplicados dentro de un conjunto, Python elimina automáticamente los segundos datos duplicados

Las acciones comunes con este tipo de elementos son:

1. Agregar datos: se utiliza el método add  
```python
numeros.add(4)
```
2. Eliminar datos: se utiliza el método distart (si no existe el elemento a borrar no da error) o remove (si no existe el elemento a borrar da error)  
```python
numeros.discard(1)  
numeros.remove(5)  
```
en este caso obtendíamos un error al no estar el elemento 5

3. Vaciar datos: se utiliza el método clear.  
```python
numeros.clear()
```
4. Recorrer los elementos: se utiliza una estructura for  
```python
for i in numeros:  
    print(i)
```
Nota: Es como se trata de una estructura no ordenada, no se puede acceder a los datos directamente, sino que tan solo se puede hacer un recorrido de los mismos. En el caso de querer hacer un acceso directo, tendríamos que convertir el conjunto en lista o tupla para poder accederlo, utilizando el método list() o tuple()

Además de las operaciones normales, sobre los conjuntos también se puede operar para realizar uniones:  
    1. Unión: se obtienen un set con los valores de dos conjuntos, eliminando aquellos datos que están duplicados  
    2. Intersección: se obtiene un set con los valores duplicados de dos conjuntos, eliminando aquellos que no lo son  
    3. Diferencia: se obtiene un set con los valores que están en el conjunto A pero no en el B  
    4. Diferencia simétrica: se obtiene un set con los valores que están en el conjunto A y B pero obviando los comunes

Un ejemplo de cada una de ellas sería el siguiente código  
```python
conjunto1 = {1,2,3,4,5}  
conjunto2 = {3,4,5,6,7}  
# {1234567}  
conjuntoUnion = conjunto1.union(conjunto2)  
# {345}  
conjuntoInters = conjunto1.intersection(conjunto2)  
# {12}  
conjuntoDif = conjunto1.difference(conjunto2)  
# {1267}  
conjuntoDif = conjunto1.symmetric_difference(conjunto2)
```
**Ejercicio**

Realiza el siguiente ejercicio para practicar lo visto en esta unidad:  
Crea una aplicación que permita gestionar los proyectos de una empresa. Para ello sigue estos pasos:  
    • Pregunta al usuario cuantos proyectos va a registrar  
    • Por cada proyecto, pide el código, nombre, responsable y presupuesto del proyecto  
    • Guarda la información de todos los proyectos en un diccionario (puedes utilizar el código como la clave y como valor puedes utilizar otro diccionario o lista  
    • Muestra por consola solo el nombre y presupuesto de cada uno de los proyectos  
Conclusiones  
Cuando se realiza un código de programación, se ha comprobado a lo largo de la unidad que las estructuras de control representan un elemento básico para poder modelar y “reconducir” el código dependiendo de condiciones lógicas o ejecuciones recurrentes. Además, también hemos podido ver que el uso de estructuras de datos permite juntar diferentes tipos de datos en un mismo elemento para poder así.

**Referencias bibliográficas**
 * Página web oficial de Pyhton <https://www.python.org>  
 * Página web w3c <https://www.w3schools.com/python/>  
 * Página web oficial de Python <https://docs.python.org/3/tutorial/controlflow.html>  
 * Página web oficial de Python <https://docs.python.org/3/tutorial/datastructures.html>  
​
