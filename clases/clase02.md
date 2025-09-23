**Sintaxis básica**  
Ya con todos los puntos clave aprendidos, vamos a ver ahora los elementos base de la sintaxis de Python. Como ya se ha comentado, Python es un lenguaje interpretado, por lo que no necesita de un compilador para poder ejecutar las líneas de código, las cuales son ejecutadas de una en una. Por ello, su sintaxis es bastante simple, dentro de las cuales cabe recordad los siguientes elementos:   
    • Comentarios: son las partes del código que no se ejecutan, sino que sirven como documentación. Para poder escribir un comentario se utilizan \# en el caso de ser una sola línea o “”” o ‘’’ en el caso de ser comentario de línea múltiple.  
\# petición de datos al usuario  
nombre \= input("¿Cuál es tu nombre? ")  
correo \= input("¿Cuál es tu correo? ")  
edad \= int(input("¿Cuál es tu edad? "))

“””  
salida de datos por consola  
método de salida por consola con print y mostrar los datos obtenidos  
“””  
print(  
    f"El correo de {nombre} es {correo}, el cual cuenta con {len(correo)} caracteres con {edad} años"  
)

    • Las variables no necesitan de tipado, ya que este se asigna con el valor en el momento de la asignación.  
    • Los bloques no tienen llaves: esto es una de las cosas que más llaman la atención, ya que para un bloque (función, sentencia de control o similar), no es necesario indicar las { } para marcar el ámbito, sino que se hace con una indentación,tabulación o sangría.

if edad \< 18:  
    print("El usuario es menor de edad, por lo que no puede acceder a la plataforma")  
else:  
    print(  
        f"El correo de {nombre} es {correo}, el cual cuenta con {len(correo)} caracteres con {edad} años"  
    )

	Otra de las cosas importantes en el lenguaje es que no es necesario el uso de ; para indicar el final de una línea, ya que el enter indica esto.

 **Elementos del lenguaje**  
Como en todo lenguaje de programación, los elementos base del lenguaje son: variables, métodos, operadores y estructuras de control. Estos elementos integrados entre sí, permiten la creación de cualquier código de programación y la ejecución de múltiples tareas. A continuación, se explica en detalle cada uno de ellos:

**Variables**  
Las variables representan aquellas partes de código donde se quiere almacenar datos de forma que estos sean accedidos desde diferentes partes en el código, bien sea para hacer referencia a ellas y capturar su valor o para modificarlo de alguna forma. Ya se ha explicado que a la hora de definir una variable no es necesario indicar que tipo de dato guarda dentro, ya que esto se hace en el momento de asignar el valor, pero si es necesario conocer los tipos de datos principales: 

    • int: números enteros sin decimal  
    • float: números con decimales, donde la parte decimal se representa con un .  
    • str: cadena de caracteres, definida entre “”  
    • bool: valor de true o false muy utilizado para decisiones lógicas  
    • list: lista ordenada y dinámica para poder guardar diferentes datos  
    • tuple: lista ordenada y estática para poder guardar diferentes datos  
    • dict: diccionario de datos asociando par clave-valor.

Si bien estos no son todos los tipos de datos que existen (ya que nosotros podemos crear nuestros propios datos con lo que se conoce como objeto), sí son los principales.

*Importante***:**  
Existe la posibilidad de cambiar entre tipos las variables, utilizando el método del tipo de dato al que quiero pasar y la variable que quiero pasar:  
Por ejemplo, para pasar un int a double habría que poner el siguiente código:  
numeroDecimal \= 34.87  
numeroEntero \= int(numeroDecimal)  
print(f"El número decimal es {numeroDecimal} y el número entero es {numeroEntero}")

En el caso de querer saber de qué tipo es una variable se puede utilizar el método type, indicando la variable en cuestión entre paréntesis  
print(type(numeroDecimal))

**Métodos**  
Los métodos representan las funcionalidades que se pueden ejecutar sobre un objeto cualquiera. Existe la posibilidad de crear nuestros propios métodos o utilizar aquellos que el lenguaje ya trae por defecto y nos aportan funcionalidades muy interesantes para poder trabajar con ellos. Antes de empezar a utilizarlos, es bueno recordar que a la hora de ejecutar un método basta con llamarlo por su nombre y poner entre paréntesis todos los parámetros que el método necesita para funcionar. De esta forma, en el caso de querer utilizar el método print que permite escribir un elemento por consola, tendríamos que pasarle por parámetros aquellos elementos que queramos mostrar.

print(“Mensaje a mostrar”)

Alguno de los métodos más interesantes que podemos encontrar en el lenguaje son:   
    • input(): permite leer por teclado un dato y asociarlo a una variable. Pide como parámetros el texto que se mostraré en la petición  
    • print(): escribe por consola el texto indicado como parámetro  
    • upper(), lower(): estos método permite pasar a mayúscula o minúscula respectivamente un texto indicado por parámetros  
    • strip(): permite eliminar espacios en blanco de un string pasado por parámetros  
    • replace(): permite sustituir un grupo de caracteres por otro en un string  
    • find(): permite obtener la posición de un grupo de caracteres en una palabra, retornando su posición  
    • len():  retorna la longitud del objeto que se pasa por parámetro, siendo la cantidad de letras en el caso de pasar un string o un número en el caso de pasar una lista  
    • type(): retorna la clase del objeto que se pasa por parámetros  
    • int(), float(): retorna el elemento pasado por parámetro en el tipo correspondiente

En el siguiente código podemos ver ejemplos de uso de los métodos explicados  
\# Pedimos al usuario que introduzca su nombre  
nombre \= input("Introduce tu nombre: ")

\# Limpiamos los espacios en blanco  
nombre\_limpio \= nombre.strip()

\# Mostramos el nombre en diferentes formatos  
print("En mayúsculas:", nombre\_limpio.upper())  
print("En minúsculas:", nombre\_limpio.lower())

\# Reemplazamos un nombre por otro, por ejemplo si alguien se llama "Juan"  
nombre\_modificado \= nombre\_limpio.replace("Juan", "Juanjo")  
print("Nombre con modificación:", nombre\_modificado)

\# Buscamos si el apellido "Gómez" está en el nombre  
posicion \= nombre\_limpio.find("Gómez")  
if posicion \!= \-1:  
    print("El apellido 'Gómez' empieza en la posición:", posicion)  
else:  
    print("El apellido 'Gómez' no se encuentra en el nombre.")

\# Mostramos la longitud del nombre  
print("Número de caracteres:", len(nombre\_limpio))

\# Mostramos el tipo de dato que es la variable nombre\_limpio  
print("El tipo de dato de la variable es:", type(nombre\_limpio))

\# Convertimos edad a número entero  
edad\_str \= input("¿Cuántos años tienes? ")  
edad \= int(edad\_str)  
print("Edad como número entero:", edad)

\# Mostramos también esa edad como número decimal (float)  
edad\_float \= float(edad)  
print("Edad como número decimal:", edad\_float)

**Operadores**  
Binarios  
\-  
Resta aritmética entre dos operadores.  
\+  
Suma aritmética entre dos operadores.  
\*  
Multiplicación aritmética entre dos operadores.  
\*\*  
Potencia aritmética de la base y el exponente  
/  
División aritmética entre dos operadores. En este caso hay que tener en cuenta que la división entre dos números enteros es un número entero.  
%  
Módulo o resto aritmético entre dos operadores. Se trata del resto de la división entre dos números.  
Un ejemplo del uso de estos operadores sería el siguiente  
\# Operadores aritméticos binarios  
a \= 10  
b \= 3

suma \= a \+ b  \# Suma: 13  
resta \= a \- b  \# Resta: 7  
multiplicacion \= a \* b  \# Multiplicación: 30  
division \= a / b  \# División 3.333 (periodo en este caso float)  
division\_entera \= a // b  \# División entera: 3  
modulo \= a % b  \# Módulo: 1  
potencia \= a\*\*b  \# Potencia: 10^3 \= 1000

Operadores comparación  
\>  
Obtiene como resultado el booleano de comparar que un operando es mayor que otro  
\>=  
Obtiene como resultado el booleano de comparar que un operando es mayor o igual que otro  
\<  
Obtiene como resultado el booleano de comparar que un operando es menor que otro  
\<=  
Obtiene como resultado el booleano de comparar que un operando es menor o igual que otro  
\==  
Obtiene como resultado el booleano de comparar que un operando es igual que otro  
\!=  
Obtiene como resultado el booleano de comparar que un operando es diferente que otro  
Un ejemplo de uso de estos operadores sería el siguiente  
\# Operadores de comparación  
a \= 10  
b \= 5

igual \= a \== b          \# ¿a es igual a b? → False  
diferente \= a \!= b      \# ¿a es distinto de b? → True  
mayor\_que \= a \> b       \# ¿a es mayor que b? → True  
menor\_que \= a \< b       \# ¿a es menor que b? → False  
mayor\_o\_igual \= a \>= b  \# ¿a es mayor o igual que b? → True  
menor\_o\_igual \= a \<= b  \# ¿a es menor o igual que b? → False

Operadores lógicos  
and  
Obtiene como resultado true todas las condiciones de la sentencia son verdaderas. En caso contrario el resultado es false. A diferencia del operador & es que si la primera condición es false el resto no se evalúa  
or  
Obtiene como resultado true si una de las condiciones de la sentencia es verdaderas. En caso contrario el resultado es false. A diferencia del operador & es que si la primera condición es true el resto no se evalúa  
not  
Obtiene el valor booleano inverso del booleano indicado  
Un ejemplo de uso de estos operadores sería el siguiente  
\# Operadores lógicos  
a \= True  
b \= False

resultado\_and \= a and b   \# AND lógico: True si ambos son True  
resultado\_or \= a or b     \# OR lógico: True si al menos uno es True  
resultado\_not\_a \= not a   \# NOT lógico: invierte el valor de a

**Ejercicio**  
Imagina que tienes dos jugadores que introducen sus puntuaciones. El programa debe:  
    • Pedir el nombre y la puntuación de cada jugador.  
    • Mostrar operaciones aritméticas entre las puntuaciones (suma, diferencia, etc.).  
    • Comparar las puntuaciones y mostrar los resultados (==, \>, \<, etc.).  
    • Mostrar expresiones lógicas compuestas sobre quién tiene más puntos, si son iguales, etc.  
    • Mostrar todos los resultados como parte de un resumen.
