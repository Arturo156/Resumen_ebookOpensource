# Resumen EbookOpensource
# Capitulo 1.

**1.1.1. Características generales de la arquitectura ARM**

ARM es una arquitectura RISC (Reduced Instruction Set Computer=Ordenador con Conjunto Reducido de Instrucciones) de 32 bits, salvo la versión del core ARMv8- A que es mixta 32/64 bits (bus de 32 bits con registros de 64 bits). 

**Registros** La arquitectura ARMv6 presenta un conjunto de 17 registros (16 principales más uno de estado) de 32 bits cada uno.

-a-

**Registros Generales.** Su función es el almacenamiento temporal de datos. Son los 13 registros que van R0 hasta R12.

**Registros Especiales.** Son los últimos 3 registros principales: R13, R14 y R15. Como son de propósito especial, tienen nombres alternativos.

**Registro CPSR.** Almacena las banderas condicionales y los bits de control. Los bits de control definen la habilitación de interrupciones normales (I), interrupciones rápidas (F), modo Thumb 1 (T) y el modo de operación de la CPU.

**Esquema de almacenamiento** Cuando escribimos un dato en una posición de memoria, dependiendo de sies byte, half word o word,... se ubica en memoria según el esquema de la figura 1.2.La dirección de un dato es la de su byte menos significativo. La memoria siempre sereferencia a nivel de byte, es decir si decimos la posición N nos estamos refiriendo
al byte N-ésimo, aunque se escriba media palabra, una palabra.

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
