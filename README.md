# PRACTICA 0 - INTRODUCCION A LINUX Y AL COMPILADOR GCC #

## 1. Objetivos ##
1. Aprender a manipular a un nivel basico la consola de Linux.
2. Introducir la sintaxis básica del leguaje C y desarrollar programas basicos empleando este lenguaje.
3. Interactuar con el compilador GCC.

## 2. Actividades previas al laboratorio ##

**Entregable**: Desarrollar todas las actividades propuestas en el tutorial [Introduction to Shell for Data Science](https://www.datacamp.com/courses/introduction-to-shell-for-data-science) de **datacamp**. Como evidencia se deberá subir en el classroom el diploma que alli se entrega una vez que el curso ha finalizado.

## 3. Temas a tratar ##
1. Repaso breve de la consola (Ver: [Linux básico](https://github.com/repos-SO-UdeA/laboratorios/tree/master/lab0/teoria/parte1)).
2.  Manejo del compilador gcc (Ver: [Manejo básico del GNU Compiler Collection (GCC)](https://github.com/repos-SO-UdeA/laboratorios/tree/master/lab0/teoria/parte2/teoria)).
3.  Introducción al lenguaje C (Ver: [Conceptos introductorios del lenguaje C](https://github.com/repos-SO-UdeA/laboratorios/blob/master/lab1/teoria/parte1/intro_C_basico.ipynb))

## 5. Actividades en el laboratorio ##
1. Analizar y compilar los ejemplos resueltos disponibles en el siguiente [enlace](https://github.com/repos-SO-UdeA/laboratorios/tree/master/lab1/sesiones/1).
2. Desarrollar los puntos propuestos en clase disnibles en el enlace anterior.

## 6. Para la proxima sesion de laboratorio ##

**Actividad 1 - Entregable**: Estudiar todas las lecciones de los modulos 1, 2, 3 y 4 del curso de sololearn [C tutorial](https://www.sololearn.com/Course/C/)

**Actividad 2**: Traer leido el [Interlude: Process API](http://pages.cs.wisc.edu/~remzi/OSTEP/cpu-api.pdf). Compilar todos los codigos de este los cuales se encuentran en el siguiente [enlace](https://github.com/so-udea/ostep-code/tree/master/cpu-api).
 
**Actividad 3 - Entregable**: Con base en lo leido, responder las siguientes pregunas:
1. ¿Que hace la llamada ```fork``` y que devuelve?
2. ¿Que es un PID y como se obtiene?
3. ¿Para que sirve la llamada ```wait```?
4. ¿Que hace la llamada ```exec```, cuantas variaciones de esta existen?
5. Dado el siguiente codigo:

```C
#include <unistd.h>
#include <stdio.h>

int main(int argc, char *argv[]) {
  pid_t pid_h1, pid_h2, pid_h3;
  pid_t pid_n;
  int i = 0;  
  pid_h1 = fork();
  if(pid_h1 == 0) {
    i++;
    pid_n = fork();
    if(pid_n==0) {
      i++;
      printf("NIETO: i = %d\n",i);      
    }else {
      printf("HIJO 1: i = %d\n",i);      
    }   
  }else {
    pid_h2 = fork();
    if(pid_h2 == 0) {
      i++;
      printf("HIJO 2: i = %d\n",i);   
    }else {
      pid_h3 = fork();
      if(pid_h3 == 0) { 
         i++;
         printf("HIJO 3: i = %d\n",i);   
      }else {  
         printf("PAPA: i = %d\n",i);   
      }
    }
  }
  return 0;
}
```
Responda las siguientes preguntas:
  1. ¿Cuantos hijos tiene cada uno de los procesos anteriormente creados?
  2. ¿Cual proceso se acaba primero?
  3. ¿La variable i es la misma para todos los procesos?, ¿Cual es su valor?

