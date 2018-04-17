# Trabajo #1 — Fases de la Traducción y Errores
## Autor
 * Ezrá Matías Blanca
 * 155530-3
 * matiasblanca
## Objetivo
 * Identificar las fases de traducción y errores.
 ### Paso 1
 1. cd C:\Users\Matias Blanca\Desktop\UTN\Segundo Año\Sintaxis y Semantica de los Lenguajes\Sintaxis 2\TPs\DD - FrasesErrores -
 El comando cd sirve para cambiar de directorio
2. notepad - Para abrir el bloc de notas
3. Cree el archivo hello2.c
### Paso 2
1. gcc -E -P hello2.c -o hello2.i - Generó hello2.i, -E muestra el resultado del preprocesamiento y -P eliminó las líneas que empezaban con #.
### Paso 3
1. notepad - Para abrir el bloc de notas
2. Cree el archivo hello3.c
### Paso 4
1. En la primera línea se declara la función printf, del tipo int y puede tener uno o mas argumentos, un puntero a char constante, que no puede variar y opcionalmente otros argumentos.
### Paso 5
1. gcc -E -P hello3.c -o hello3.i - Luego de preprocesar hello3.c, hello3.c y hello3.i son iguales, la única diferencia es el tipo de archivo
### Paso 6
1. gcc -S hello3.i -o hello3.s - hello3.i: In function 'main':
hello3.i:4:2: warning: implicit declaration of function 'prontf' [-Wimplicit-function-declaration]
  prontf("La respuesta es %d\n");
  ^~~~~~
hello3.i:4:2: error: expected declaration or statement at end of input - Hubo un error de compilación, esperaba encontrar un } que cierre el main, también hay un warning diciendo que intento declarar implicitamente la funcion prontf
### Paso 7
1. notepad - Para abrir el bloc de notas
2. Agregué el } para cerrar el main y cree el archivo hello4.c
3. gcc -E -P hello4.c -o hello4.i - Se preprocesó hello4.c y se generó hello4.i
4. gcc -S hello4.i -o hello4.s - hello4.i: In function 'main':
hello4.i:4:2: warning: implicit declaration of function 'prontf' [-Wimplicit-function-declaration]
  prontf("La respuesta es %d\n");
  ^~~~~~ Hubo un warning diciendo que intento declarar implicitamente la funcion prontf y se generó un archivo assembler hello4.s
  ### Paso 9
  1. gcc -c hello4.s -o hello4.o - Se generó un archivo de código maquina hello4.o
  ### Paso 10
  1. gcc hello4.o -o hello4 - hello4.o:hello4.i:(.text+0x1e): undefined reference to 'prontf'
collect2.exe: error: ld returned 1 exit status No se pudo generar el ejecutable porque hubo un error de linkeo, ya que no encontró prontf en la biblioteca estándar
### Paso 11
1. notepad - Para abrir el bloc de notas
2. Cambie prontf por printf y cree el archivo hello5.c
3. gcc hello5.c -o hello5 - Se generó el ejecutable hello5
### Paso 12
1. hello5 - Se ejecutó el programa y devolvió por la salida estandar: "La respuesta es 4200768"
### Paso 13
1. notepad - Para abrir el bloc de notas
2. Agregué un argumento i a printf para que muestre el contenido de la variable i(42) en lugar de 4200768 y cree el archivo hello6.c
3. gcc hello6.c -o hello6 - Se generó el ejecutable hello6
4. hello6 - Se ejecutó el programa y devolvió por la salida estándar: "La respuesta es 42"
### Paso 14
1. notepad - Para abrir el bloc de notas
2. Cree el archivo hello7.c
### Paso 15
1. gcc hello7.c -o hello7 - hello7.c: In function 'main':
hello7.c:3:2: warning: implicit declaration of function 'printf' [-Wimplicit-function-declaration]
  printf("La respuesta es %d\n", i);
  ^~~~~~
hello7.c:3:2: warning: incompatible implicit declaration of built-in function 'printf'
hello7.c:3:2: note: include '<stdio.h>' or provide a declaration of 'printf' me dice que estoy tratando de declarar implicitamente printf y que debería hacer un include de la librería stdio.h o proveer una declaración de printf y se generó hello7
2. hello7 - Se ejecutó el programa y devolvió por la salida estándar: "La respuesta es 42"
### Paso 16
1. Funciona porque C proporciona una declaración implícita automáticamente para una función que no tiene un prototipo en el scope, la declaración implícita sería int printf(); entonces printf es una función que devuelve un int y puede tomar cualquier cantidad de argumentos. Esto significa que el compilador puede hacer lo que quiera con un programa que usa printf sin el prototipo de stdio.h o una definición equivalente.


