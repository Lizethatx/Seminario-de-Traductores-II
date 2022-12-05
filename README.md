# Seminario-de-Traductores-II

Repositorio para la materia de Seminario de Traductores II

Profesor: Michel Emanuel Lopez Franco

Alumna: Lizeth Avendaño Garcia

2022-B CUCEI UDG

# _Proyecto Final - Compilador_

A continuación se muestran las fases desarrolladas a lo largo del curso para la creación de un compilador básico creado en el lenguaje de programación C++.

El código completo se pdorá descargar desde el apartado proyecto final en este mismo repositorio

## Analizador Léxico
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Módulo 1 Analizador léxico
El léxico de un lenguaje de programación u otro lenguaje usado en la informática, está constituido 
por todas las palabras y símbolos que lo componen. En los lenguajes de programación el léxico 
lo constituyen todos los elementos individuales del lenguaje, denominados frecuentemente como 
“tokens”.
Tiene como propósito, agrupar un texto ingresado en diferentes tipos de patrones que conforman 
las unidades léxicas como identificadores, palabras reservadas, operadores y símbolos, entre otros.
Dichas unidades son representadas internamente con un número, los cuales son llamados cuando se 
comienza a analizar la cadena de entrada.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Para la codificación de la primera parte del compilador se establecieron 23 tokens; según el tipo de símbolo se le asignó un número internamente con el fin de conocer el estado que cada uno tenía en el autómata creado (siguiente Caracter, siguiente Estado, Aceptación).
A su vez a cada token se le asigna una cadena que será la mostrada en la impresión de pantalla para reconocer las unidades léxicas.

*Reconoce los siguientes símbolos:*

•Identificadores= letra (letra|digito)* 

•Entero= digito+ 

•Real= entero.entero

•Operador de adición: + | -

•Operador de multiplicación: * | /

•Operador de asignación: =

•Operador relacional: < | > | <= | >= | != | ==

•Operador And: &&

•Operador Or: ||

•Operador Not: !

•Parentesis: ( , )

•Llave: { , }

•Punto y coma: ;

•Además de las siguientes palabras reservadas: if, while, return, else, int, float

![Captura1](https://user-images.githubusercontent.com/75290686/186078769-e2d80094-ab56-4292-833d-a2db6beb730b.PNG)

![Captura2](https://user-images.githubusercontent.com/75290686/186078834-bc2ad2ed-83b5-44a1-a435-2c2bca16c92f.PNG)

![Captura3](https://user-images.githubusercontent.com/75290686/186078906-4b785d08-79ed-4c93-8538-863a437f6837.PNG)

## Analizador Sintáctico
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Módulo 2 Analizador sintáctico
El analizador sintáctico es la siguiente fase de un compilador, después del analizador léxico.
Su principal función consiste en la descomposición y transformación de las entradas en un 
formato utilizable para su posterior procesamiento. Se analiza una cadena de instrucciones 
en un lenguaje de programación y luego se descompone en sus componentes individuales. 
Este utiliza los tokens obtenidos del analizador léxico que sirven como caracteres de 
entrada para el analizador sintáctico.
Tiene como propósito, manejar la gramática de los datos de entrada, realiza un análisis 
sintáctico de éstos y como regla general crea un árbol de sintaxis (árbol de análisis), y esto 
se puede utilizar para el procesamiento posterior de los datos, por lo tanto, el analizador es 
el software que comprueba, procesa y reenvía las instrucciones del código fuente.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

### _Mini analizador sintáctico_:
La creación de este submódulo hace uso del analizador sintáctico LR, el cual se basa en una pila de enteros que es la que va guardando el estado y las reglas con forme se va analizando la cadena hasta que se llega a un estado de aceptación.

Generar un algoritmo para analizar los Ejercicios 1 y 2 del archivo

#### Ejercicio 1 hola+mundo

![image](https://user-images.githubusercontent.com/75290686/204434575-bc526d6d-b07b-4c9f-952e-13e832d83dbf.png)
![image](https://user-images.githubusercontent.com/75290686/204434547-96a8c81f-e9fb-4787-9397-706d726c79bc.png)

![image](https://user-images.githubusercontent.com/75290686/196600124-ecb2fbf0-4ad5-4943-85c9-3246cda1fbbf.png)

##### Ejercicio 2 a+b+c+d+e+f

![image](https://user-images.githubusercontent.com/75290686/204435207-591c3a58-d330-40a6-b5bf-48f783dea7b4.png)
![image](https://user-images.githubusercontent.com/75290686/204435286-dc5cfc71-2ee0-4435-af02-375eb8fbafab.png)


![image](https://user-images.githubusercontent.com/75290686/196600232-9b1b9350-1a97-4c1e-8c9a-80f6b87b8f85.png)
![image](https://user-images.githubusercontent.com/75290686/196600389-66303109-fe68-4796-b631-c074ceac14db.png)

### _Analizador sintáctico implementando objetos_:
En esta práctica se hizo uso de la pila de objetos a diferencia de la pasada que fue una pila de enteros. Al momento de imprimir la pila aparecen los símbolos
Para realizarla se necesitó implementar dentro del código 3 clases nuevas, las cuales heredan del Elemento Pila. Estas clases nuevas corresponden a Terminal, No terminal y Estado.

![image](https://user-images.githubusercontent.com/75290686/189804439-68c72ad3-092d-4983-a497-513ecc09c7bd.png)

### _Gramática del compilador_:
En esta entrega se cargó e implementó una gramática al analizador léxico. La gramática está contenida en un archivo .lr donde se encuentra la información de la gramática con las tabla LR(1) codificada para ser cargada en una matriz de enteros y la cual es leída por el programa. 
En el archivo .inf se indica la constante que se debe asignar al analizador léxico para cada símbolo. Además de que es en este archivo donde aparecen todas las reglas numeradas (necesarias para hacer reducciones).

_Ejemplo de gramática int hola;_

![image](https://user-images.githubusercontent.com/75290686/204452220-eea4c1ac-212b-4897-868c-1ea06645b3a9.png)
![image](https://user-images.githubusercontent.com/75290686/204452072-a993361b-139e-4480-9415-1aab55e9fa7c.png)
![image](https://user-images.githubusercontent.com/75290686/204452107-6c1f08ac-79e0-4d64-b794-3e2f7449999c.png)

## Analizador Semántico
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Modulo 3 Analizador semántico
El analizador semántico es la siguiente fase de un compilador, después del analizador 
sintáctico. Su principal función consiste en el análisis contextual de las instrucciones del 
lenguaje de programación para su posterior implementación en lenguaje máquina. Se analiza una
estructura de instrucciones en un árbol semántico y luego comparan los diferentes componentes 
individuales en búsqueda de errores en la programación. Este utiliza la estructura que generamos
en el analizador sintáctico a partir de los tokens obtenidos del analizador léxico.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

### _Árbol sintáctico_
En el programa anterior se utilizó una pila de objetos, ahora para realizar el análisis semántico fue necesario generar un arbol sintáctico en el cual se almacenan las definiciones de funciones, variables y expresiones.

_Ejemplo 
int a;
int suma(int a, int b){
return a+b;}_

![image](https://user-images.githubusercontent.com/75290686/205476146-b9dac526-4a61-4aa4-abc9-21c1c0d0e697.png)

### _Análisis semántico_

Para la creación de este módulo se aregaron tres atributos más a la clase nodo, así mismo se agregó un método encargado de validar los tipos de datos. Además se implementaron tres métodos más en la tabla de símobolos (agrega).

A continuación se muestra el funcionamiento del análisis semántico

_Ejemplo_

int main(){

float a;

int b;

int c;

c = a+b;

c = suma(8,9);

}

![image](https://user-images.githubusercontent.com/75290686/205480129-102dfb4c-d024-4055-a1d1-a6775e16136c.png)

_Ejemplo: int x ( int y ) { int j ; j = 7 ; char letra ; return 7 + 8 ; }_

El 0 mostrado al final del programa es el dato que se paso a memoria para complilar, de esta forma, se une la gramatica del compilador con el arbol sintactico.

![image](https://user-images.githubusercontent.com/75290686/205572942-54eba74c-5ce5-47e1-b03a-6129da2d552c.png)

## Generación de código
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Módulo 4 Generación de código
La generación de código consiste en relacionar todo lo que hemos hecho en nuestro compilador 
el cual ha llevado ya por tres fases de desarrollo. Se trata así pues de la última fase del 
compilador que se han desarrollado, el cual tiene como función vincular las funciones de nuestro
lenguaje con las puras de ensamblador.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Para la realización de este módulo se utilizó el lenguaje ASM embebido en C, la estructura utilizada fue crear pequeños bloques de código con diferentes funciones para realizar diversas operaciones.

_Ejemplo Suma:_
Se agregó un archivo en C++ en el que se encuentran las funciones en ensamblador
![image](https://user-images.githubusercontent.com/75290686/205579445-0992d5a1-2a5b-481c-88a5-e0482ceaf2aa.png)

Dicho código es leído desde el archivo principal para poder mostrar un resultado. Además se crearon dos archivos con formato txt, de esta forma será posible añadir los prototipos de funciones y las funciones respectivas que se establecieron en lenguaje ensamblador para que ésta última sea leída y se pueda realizar un análisis semántico y por supuesto, proporcionarnos el resultado final de la operación solicitada.

![image](https://user-images.githubusercontent.com/75290686/205588057-7241e56c-8a91-4c60-a419-9df83030a5d4.png)
![image](https://user-images.githubusercontent.com/75290686/205587320-f1a60a18-960c-42a2-824a-1cae1cc40abf.png)

El resultado al ejecutar el programa es el siguiente:

![image](https://user-images.githubusercontent.com/75290686/205587194-bd0a1e27-9343-428a-8f5b-b29754d05e77.png)


![image](https://user-images.githubusercontent.com/75290686/205587451-ebf0de62-7540-4002-8600-cb50b33d3025.png)



