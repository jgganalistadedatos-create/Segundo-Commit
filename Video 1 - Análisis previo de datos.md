---
title: "Video 1 — Análisis previo de datos en R"
source: "Transcripción de YouTube proporcionada por el usuario"
chapter: 5
tags:
  - aprendizaje-estadistico
  - R
  - preparacion-de-datos
  - analisis-exploratorio
---

# Video 1 — Análisis previo de datos en R

[Ver el video en YouTube](https://www.youtube.com/watch?v=6Lg54pmR1-4&t=7s)

## Idea central

Antes de aplicar una técnica estadística, hay que preparar los datos y examinarlos para entender qué contienen. Si se ajusta un modelo con datos sin depurar, el cálculo puede ser correcto y aun así describir una muestra equivocada. La revisión inicial ayuda a detectar valores ausentes, problemas de formato y características importantes de las variables.

## Caso de estudio

La práctica utiliza datos ficticios del sector del transporte interestelar. La autoridad reguladora (ARTI) solicita un análisis previo para orientar dos preguntas:

1. ¿Es homogénea la rentabilidad económica entre las empresas? Se estudiará la variable `Reneco`.
2. ¿Cómo se relacionan la rentabilidad, el activo, el margen y el resultado?

La sesión de este video prepara los datos para responderlas; todavía no desarrolla el análisis estadístico de esas preguntas.

## Preparar el proyecto de R

El profesor crea un proyecto de RStudio asociado a una carpeta de trabajo. La carpeta del proyecto sirve como ubicación común para los archivos de entrada y los resultados que se generen.

En esa carpeta coloca tres materiales:

- El Excel `interestelar 100`, con los datos.
- El script `previo RStars`, que utiliza funciones resumidas de un paquete auxiliar.
- El script `previo puro RStars`, que muestra las instrucciones sin esas funciones resumidas.

Ambos scripts deberían producir los mismos resultados. En la práctica del video se usa el primero para reducir código repetitivo.

## Preparar la sesión e importar los datos

1. Se limpia el entorno global de R para evitar que objetos de sesiones anteriores interfieran.
2. Se activan los paquetes necesarios. **Activar** un paquete permite usar sus funciones; **instalarlo** es un paso distinto y normalmente se hace una sola vez.
3. Se importa el Excel desde la carpeta del proyecto y desde la hoja llamada `Datos`.
4. Se especifican las marcas que representan datos ausentes (en la transcripción se reconoce una etiqueta similar a `n.d.`). Si no se indican, R podría leer una columna numérica como texto.

El archivo de Excel tiene tres hojas: `Inicio`, `Variables` —que funciona como diccionario de variables— y `Datos`.

La hoja de datos contiene **104 empresas**. La primera columna contiene sus nombres. Después de importarla, el profesor coloca esos nombres como nombres de fila en vez de conservarlos como una variable adicional. Así, el marco de datos pasa de 29 columnas a 28 variables.

## Inspeccionar las variables

Se realiza un resumen inicial del marco de datos:

- `summary()` ofrece resúmenes básicos según el tipo de variable.
- También se genera una tabla visual de resumen con distribuciones de variables cualitativas, histogramas para variables numéricas, porcentaje de valores ausentes y estadísticos como media, mediana y desviación típica.

Esta inspección permite comprobar cómo vienen los datos antes de comenzar el análisis. En el ejemplo se observa, entre otros detalles, que la variable `Activo` tiene aproximadamente un 1 % de valores ausentes.

## Conservar el original

Antes de depurar `Reneco`, el profesor conserva el marco de datos original y crea una copia llamada `muestra`. El trabajo posterior se hará sobre esa copia.

Este procedimiento permite modificar o filtrar los datos de análisis sin perder la fuente importada, y facilita comparar los datos originales con los preparados.

## Flujo de trabajo del video

`Crear proyecto → reunir archivos → limpiar entorno → activar paquetes → importar Excel → identificar datos ausentes → ordenar identificadores de empresas → resumir variables → crear copia para depuración`

## Conceptos clave

- **Proyecto de RStudio:** carpeta de trabajo que organiza los archivos usados y producidos por el análisis.
- **Entorno global:** espacio en memoria donde R mantiene los objetos de la sesión.
- **Paquete instalado / paquete activado:** instalar incorpora el paquete a la máquina; activarlo carga sus funciones para usarlas en la sesión.
- **Dato ausente:** valor que falta. Puede estar representado por una celda vacía o por una etiqueta que debe declararse como ausente al importar.
- **Exploración inicial:** revisión de tipos, distribuciones, estadísticos y valores ausentes antes de elegir o ajustar modelos.
- **Copia de trabajo:** duplicado del conjunto original sobre el que se realizan cambios de preparación.

## Para recordar

La preparación de datos forma parte del análisis, no es un trámite. Conviene revisar la codificación de los valores ausentes, los tipos de las variables y sus distribuciones antes de estimar modelos. También es buena práctica conservar intacta la importación original y trabajar sobre una copia.

## Alcance de esta primera parte

El video configura el proyecto, importa y explora los datos y crea una copia para trabajar. La depuración concreta de `Reneco` y el análisis de las preguntas quedan para la continuación de la práctica.

## Fuente de la transcripción

Archivo local: `Video 1.txt`. La transcripción automática contiene errores puntuales en algunos nombres de funciones y paquetes; por eso esta nota resume el procedimiento y evita atribuir nombres de código dudosos.

