# Trabajo #1 — Fases de la Traducción y Errores
## Autor
 * Ezrá Matías Blanca
 * 155530-3
 * matiasblanca
## Objetivo
 * Identificar las fases de traducción y errores.
 ### Hello2.c
 #### Comandos Ejecutados:
 1. gcc hello2.c
 2. gcc -E -P hello2.c -o hello2.i
 #### Resultados o errores obtenidos: 
 1. hello2.c: In function 'main':
hello2.c:4:2: warning: implicit declaration of function 'prontf' [-Wimplicit-function-declaration]
  prontf("La respuesta es %d\n");
  ^~~~~~
hello2.c:4:2: error: expected declaration or statement at end of input
2. Generó hello2.i, -E muestra el resultado del preprocesamiento y -P eliminó las líneas que empezaban con #.
 ### Hello3.c
 #### Comandos Ejecutados:
 * gcc hello3.c
 * gcc -E -P hello3.c -o hello3.i
 * gcc -S hello3.i -o hello3.s
 #### Resultados o errores obtenidos:
 * hello3.c: In function 'main':
hello3.c:4:2: warning: implicit declaration of function 'prontf' [-Wimplicit-function-declaration]
  prontf("La respuesta es %d\n");
  ^~~~~~
hello3.c:4:2: error: expected declaration or statement at end of input
* Luego de preprocesar hello3.c, hello3.c y hello3.i son iguales, la única diferencia es el tipo de archivo
* hello3.i: In function 'main':
hello3.i:4:2: warning: implicit declaration of function 'prontf' [-Wimplicit-function-declaration]
  prontf("La respuesta es %d\n");
  ^~~~~~
hello3.i:4:2: error: expected declaration or statement at end of input
### Hello4.c
 #### Comandos Ejecutados:
 * gcc hello4.c
 * gcc -E -P hello4.c -o hello4.i
 * gcc -S hello4.i -o hello4.s
 * gcc -c hello4.s -o hello4.o
 * gcc hello4.o -o hello4
 #### Resultados o errores obtenidos:
 * hello4.c: In function 'main':
hello4.c:4:2: warning: implicit declaration of function 'prontf' [-Wimplicit-function-declaration]
  prontf("La respuesta es %d\n");
  ^~~~~~
C:\Users\MATIAS~1\AppData\Local\Temp\ccmsarno.o:hello4.c:(.text+0x1e): undefined reference to 'prontf'
collect2.exe: error: ld returned 1 exit status
* Se preprocesó hello4.c y se creó hello4.i
* hello4.i: In function 'main':
hello4.i:4:2: warning: implicit declaration of function 'prontf' [-Wimplicit-function-declaration]
  prontf("La respuesta es %d\n");
  ^~~~~~ y se generó un archivo assembler hello4.s
  * Se generó un archivo de código maquina hello4.o
  * hello4.o:hello4.i:(.text+0x1e): undefined reference to 'prontf'
collect2.exe: error: ld returned 1 exit status

### Hello5.c
 #### Comandos Ejecutados:
 * 
 #### Resultados o errores obtenidos:



