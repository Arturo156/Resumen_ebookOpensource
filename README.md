# Resumen EbookOpensource


**1.1.1. Características generales de la arquitectura ARM**

En este primer subtema conocemos ARM que es una arquitectura RISC de 32 bits, salvo la versión del core ARMv8- A que es mixta 32/64 bits. 

**Registros** En los registros la arquitectura ARMv6 presenta un conjunto de 17 registros de 32 bits cada uno. Como se puede apreciar en la imagen.

-a-

**Registros Generales.** Su función es el almacenamiento temporal de datos. Son los 13 registros que van R0 hasta R12.

**Registros Especiales.** Son los últimos 3 registros principales: R13, R14 y R15. Como son de propósito especial, tienen nombres alternativos.

**Registro CPSR.** Almacena las banderas condicionales y los bits de control. Los bits de control definen la habilitación de interrupciones normales (I), interrupciones rápidas (F), modo Thumb 1 (T) y el modo de operación de la CPU.

**Esquema de almacenamiento** Cuando escribimos un dato en una posición de memoria, dependiendo de sies byte, half word o word,... se ubica en memoria según la imagen que vemos a continuacion. La dirección de un dato es la de su byte menos significativo. La memoria siempre sereferencia a nivel de byte, es decir si decimos la posición N nos estamos refiriendo al byte N-ésimo, aunque se escriba media palabra, una palabra.

-a-

**1.1.2. El lenguaje ensamblador**

El ensamblador presenta una serie de ventajas e inconvenientes con respecto a otros lenguajes de más alto nivel. Al ser un lenguaje de bajo nivel, presenta como
principal característica la flexibilidad y la posibilidad de acceso directo a nivel de registro. En contrapartida, programar en ensamblador es laborioso puesto que los
programas contienen un número elevado de líneas y la corrección y depuración de éstos se hace difícil.

**1.1.3. El entorno**
Los pasos habituales para hacer un programa (en cualquier lenguaje) son los siguientes: lo primero es escribir el programa en el lenguaje fuente mediante un editor de programas. El resultado es un fichero en un lenguaje que puede entender el usuario, pero no la máquina. Para traducirlo a lenguaje máquina hay que utilizar
un programa traductor. Éste genera un fichero con la traducción de dicho programa, pero todavía no es un programa ejecutable.

-a-

**1.1.4. Configuración del entorno para realizar las prácticas en casa**

En este subtema explica lo que vimos en clase, como instalar QEMU y raspberryOS.

**1.1.5. Aspecto de un programa en ensamblador**

En el listado 1.1 se muestra el código de la primera práctica que probaremos. En el código hay una serie de elementos que aparecerán en todos los programas y que estudiaremos a continuación.

-a-
-c-

La principal característica de un módulo fuente en ensamblador es que existe una clara separación entre las instrucciones y los datos. La estructura más general
de un módulo fuente es:

**Sección de datos** Viene identificada por la directiva .data. En esta zona se definen todas las variables que utiliza el programa con el objeto de reservar memoria para contener los valores asignados.

**Sección de código.** Se indica con la directiva .text, y sólo puede contener código o datos no modificables. Como todas las instrucciones son de 32 bits no hay que tener especial cuidado en que estén alineadas.

**Directivas**

Las directivas son expresiones que aparecen en el módulo fuente e indican al
compilador que realice determinadas tareas en el proceso de compilación. Son fácilmente distinguibles de las instrucciones porque siempre comienzan con un punto.

**Directivas de asignación:** Se utilizan para dar valores a las constantes o reservar posiciones de memoria para las variables.

```
a1 : .byte 1 /* tipo byte, inicializada a 1 */
var2 : .byte ’A ’ /* tipo byte, al caracter ’A’ */
var3 : .hword 25000 /* tipo hword (16 bits ) a 25000 */
var4 : .word 0x12345678 /* tipo word de 32 bits */
b1 : .ascii " hola " /* define cadena normal */
b2 : .asciz " ciao " /* define cadena acabada en NUL */
dat1 : .zero 300 /* 300 bytes de valor cero */
dat2 : .space 200, 4 /* 200 bytes de valor 4 */
```

**Directivas de control:** .text y .data sirven para delimitar las distintas secciones de nuestro módulo. .align alineamiento es para alinear el siguiente dato, rellenando con ceros, de tal forma que comience en una dirección múltiplos del número que especifiquemos en alineamiento, normalmente potencia de 2.
```
a1 : .byte 25 /* definimos un byte con el valor 25 */
.align /* directiva que rellena con 3 bytes */
a2 : .word 4 /* variable alineada a tama ño palabra */
```

**Directivas de operando:** Se aplican a los datos en tiempo de compilación. En general, incluyen las operaciones lógicas &, |, ∼, aritméticas +, -, *, /, % y de
desplazamiento <, >, <<, >>.
```
.equ pies, 9 /* definimos a 9 la constante pies */
.equ yardas, pies / 3 /* calculamos las yardas = 3 */
.equ pulgadas, pies * 12 /* calculamos pulgadas = 108 */
```

**Directivas de Macros:** Una .macro es un conjunto de sentencias en ensamblador que pueden aparecer varias veces repetidas en un programa con algunas modificaciones.
```
.macro CuadM1 input, aux, output
mul aux, input, input
add output, aux, # 1
.endm
```

**1.1.6. Ensamblar y linkar un programa**
Este tema ya lo vimos en clase, explica como compilar el progama .s y crear el ejecutador.

**intro 1**
**intro 2**
**intro 3**

**1.2. Enunciados de la práctica**

**1.2.4. Rotaciones y desplazamientos** En este apartado veremos el funcionamiento de las instrucciones de desplamiento y rotación. Las instrucciones de desplazamiento pueden ser lógicas o aritméticas. Los desplazamientos lógicos desplazan los bit del registro fuente introduciendo ceros. 

**intro 4**

**intro 5**





