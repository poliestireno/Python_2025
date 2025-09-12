# **Introducción a la Programación en Python**

Este documento proporciona una introducción formal a los conceptos fundamentales de la programación en Python, utilizando ejemplos claros para facilitar la comprensión. Los conceptos se presentan en celdas de código independientes para una ejecución secuencial y modular.

## **1\. Variables y Tipos de Datos**

En Python, las variables son elementos de memoria que almacenan información. El lenguaje cuenta con un sistema de tipado dinámico, lo que permite asignar valores sin la necesidad de declarar explícitamente el tipo de dato de la variable.

```
# Celda 1: Variables y Tipos de Datos

# Declaración de una variable de tipo entero
numero_entero = 10

# Declaración de una variable de tipo flotante
numero_decimal = 3.14

# Declaración de una variable de tipo cadena de caracteres (string)
cadena_de_texto = "¡Hola, mundo!"

# Impresión de los valores y tipos de datos de las variables
print(f"La variable 'numero_entero' es un {type(numero_entero)} y su valor es: {numero_entero}")
print(f"La variable 'cadena_de_texto' es un {type(cadena_de_texto)} y su valor es: {cadena_de_texto}")

# Ejemplo con temática de Disney
# Variables para los personajes
nombre_personaje = "Mulan"
edad_personaje = 18
poder_magico = 8.5 # Valor en una escala del 1 al 10
es_heroina = True  # Variable booleana

print(f"El personaje {nombre_personaje} tiene {edad_personaje} años, un poder de {poder_magico} y su estatus de heroína es: {es_heroina}.")
```

## **2\. Operaciones Básicas**

Las operaciones permiten la manipulación de los datos almacenados en las variables. Se pueden realizar operaciones aritméticas con valores numéricos y concatenación con cadenas de caracteres.

```# Celda 2: Operaciones Básicas

# Operaciones aritméticas
resultado_suma = 15 + 5
resultado_resta = 10 - 2
resultado_multiplicacion = 4 * 6
resultado_division = 20 / 5

# Concatenación de cadenas
mensaje_completo = "El mundo es grande" + " y maravilloso."

print(f"El resultado de la suma es: {resultado_suma}")
print(f"El mensaje completo es: {mensaje_completo}")

# Ejemplo con temática de Disney
num_peticiones_genio = 3
amigos_de_aladdin = 2

# Cálculo del total de personas en la cueva
total_en_cueva = num_peticiones_genio + amigos_de_aladdin + 1

print(f"El total de personas en la Cueva de las Maravillas es: {total_en_cueva}.")
```
## **3\. Estructuras de Datos: Listas y Diccionarios**

Las estructuras de datos facilitan la organización de colecciones de información. Una **lista** es una colección ordenada de elementos, mientras que un **diccionario** almacena datos en pares de clave-valor para una recuperación eficiente.

```# Celda 3: Estructuras de Datos: Listas y Diccionarios

# Declaración de una lista (se define con corchetes [])
lista_de_numeros = [1, 5, 8, 10]
# El acceso a los elementos se realiza mediante índices, comenzando desde 0
print(f"El primer elemento de la lista es: {lista_de_numeros[0]}")

# Declaración de un diccionario (se define con llaves {})
diccionario_de_datos = {
    "nombre": "Pedro",
    "edad": 25,
    "ciudad": "Barcelona"
}
# El acceso a los valores se realiza a través de las claves
print(f"La edad de Pedro es: {diccionario_de_datos['edad']}")

# Ejemplo con temática de Disney
# Lista de los personajes principales de "El Rey León"
reyes_y_reinas = ["Mufasa", "Sarabi", "Simba", "Nala"]
print(f"El futuro rey de la selva es: {reyes_y_reinas[2]}.")

# Diccionario con información de "La Sirenita"
informacion_princesa = {
    "nombre": "Ariel",
    "pelicula": "La Sirenita",
    "animal_amigo": "Sebastián"
}
print(f"El animal amigo de {informacion_princesa['nombre']} es {informacion_princesa['animal_amigo']}.")
```

## **4\. Control de Flujo: Condicionales y Bucles**

Estas estructuras son esenciales para controlar la ejecución del código. Las **sentencias condicionales** (if/else) permiten tomar decisiones lógicas, mientras que los **bucles** (for) facilitan la repetición de acciones para cada elemento de una colección.

```# Celda 4: Control de Flujo: Condicionales y Bucles

# Estructura condicional (if, elif, else)
calificacion = 85

if calificacion >= 90:
    print("El desempeño califica como excelente.")
elif calificacion >= 70:
    print("El desempeño califica como bueno.")
else:
    print("Es necesario mejorar el rendimiento.")

# Bucle 'for' para iterar sobre una lista
nombres = ["Ana", "Luis", "Sofía"]
print("Nombres en la lista:")
for nombre in nombres:
    print(f"Presentando a: {nombre}.")

# Ejemplo con temática de Disney
# Bucle que itera sobre los 7 enanitos
enanitos = ["Grumpy", "Dopey", "Doc", "Happy", "Sneezy", "Bashful", "Sleepy"]
for enanito in enanitos:
    print(f"Presentando al enanito {enanito}.")

# Estructura condicional
tiene_varita = True
if tiene_varita:
    print("¡Bibidi Bobidi Bú!")
else:
    print("El hechizo requiere una varita.")
```
