# Trabajo #1 — Fases de la Traducción y Errores
## Autor
 * Ezrá Matías Blanca
 * 155530-3
 * matiasblanca
## Objetivo
 * Identificar las fases de traducción y errores.
 ### Hello2.c
 #### Comandos Ejecutados:
 * gcc hello2.c
 * gcc -E -P hello2.c -o hello2.i
 #### Resultados o errores obtenidos: 
 * hello2.c: In function 'main':
hello2.c:4:2: warning: implicit declaration of function 'prontf' [-Wimplicit-function-declaration]
  prontf("La respuesta es %d\n");
  ^~~~~~
hello2.c:4:2: error: expected declaration or statement at end of input
* Generó hello2.i, -E ,uestra el resultado del preprocesamiento y -P eliminó las líneas que empezaban con #.
