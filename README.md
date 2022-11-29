# Seminario-de-Traductores-II

Repositorio para la materia de Seminario de Traductores II

Profesor: Michel Emanuel Lopez Franco

Alumna: Lizeth Avendaño Garcia

2022-B CUCEI UDG

# _Proyecto Final - Compilador_

A continuación se muestran las fases desarrolladas a lo largo del curso para la creación de un compilador básico creado en el lenguaje de programación C++.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Módulo 1 Analizador léxico
El léxico de un lenguaje de programación u otro lenguaje usado en la informática, está constituido por todas las palabras 
y símbolos que lo componen. En los lenguajes de programación el léxico lo constituyen todos los elementos individuales del 
lenguaje, denominados frecuentemente como “tokens”.
Tiene como propósito, agrupar un texto ingresado en diferentes tipos de patrones que conforman las unidades léxicas como 
identificadores, palabras reservadas, operadores y símbolos, entre otros. Dichas unidades son representadas internamente 
con un número, los cuales son llamados cuando se comienza a analizar la cadena de entrada.


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

## Analizador Léxico

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

### Capturas de pantalla
![Captura1](https://user-images.githubusercontent.com/75290686/186078769-e2d80094-ab56-4292-833d-a2db6beb730b.PNG)

![Captura2](https://user-images.githubusercontent.com/75290686/186078834-bc2ad2ed-83b5-44a1-a435-2c2bca16c92f.PNG)

![Captura3](https://user-images.githubusercontent.com/75290686/186078906-4b785d08-79ed-4c93-8538-863a437f6837.PNG)
