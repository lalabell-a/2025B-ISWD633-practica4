# Mi aprendizaje.

## Antes de la práctica. 
Con 3 practicas en donde me ayudaron a desenvolverme en el entorno Docker (crear y ejecutar contenedores, a comprender la diferencia entre imagen, contenedor, red y volumen, y a manipular variables de entorno, redes bridge, host y none, entre muchas otros procedimientos realizados). No tenía ninguna noción de lo que podía venir en esta práctica. 

## Después de la práctica. 
Para ponerlo en palabras simples, entendemos que Docker Hub nos ayuda a descargar imagene (como un gran repositorio), pero estas mismas pueden editarse, practicas anteriores establecieron un paso a paso del cómo los contenedores pueden comunicarse, adicional aquí se llevo a cabo el mapeo de puertos e inspección para la configuración. 

¿Por qué es importante la limitación en el uso de recursos? Pues, es un recurso limitado de nuestro equipo y es perjudicial que se consuma más de lo que realmente se necesita, por ello, existe la distribución de los recursos (uso del memory, memory-swap).

Por ello, es primordial señalar la teoría que señala el cálculo y entendimiento de los recursos necesarios para evitar problematicas referentes al consumo de la memoria. 

Calculo aprendido: 

Memoria swap máxima = *memory-swap − memory

Además, el parámetro --memory-swap siempre se utiliza en conjunto con --memory para definir un límite total de memoria que incluye tanto la memoria RAM como la memoria swap. Ya que al no entregar ambos, puede ocasionar un error en Docker. 

En la parte tres se explica más referente a los núcleos del CPU, estos tal como la memoria, se pueden controlar e incluso usar uno especifico. 

Vease la linea a la restricción:

```
docker run -d --name server-nginx --cpuset-cpus="0-2" nginx:alpine
```

O escoger los cores utilizados: 

```
docker run -d --name server-nginx --cpuset-cpus="1,3" nginx:alpine
```

Ayuda bastante a la distribución de carga del sistema y como el usuario lo quiere manejar. 

El tema Healthcheck, basicamente nos sirve para la verificación de un contenedor y si se encuentra activo, monitoricear los estados de los servicios dentro de este contenedor o el estado del contenedor como tal. Este es un comando que se ejecuta periódicamente dentro del contenedor. Si el comando devuelve un estado de éxito (código de salida 0) significa que está saludable, cualquier otro resultado indica que este no está en buen estado. 

Dockerfile, este dio una visualización referente a las instrucciones (que se puede ver como una cebolla), ya que estas mismas son reutilizadas en el caso de no ser cambiadas, agregando eficiencia en el tiempo. Además, se vio el concepto de imágenes huerfanas, que no tienen un funcionamiento como tal y deben ser eliminadas para liberaar espacio. En esta parte de la practica me encontré con un error curioso. El error de los repositorios de CentOS 7 al ejecutar yum update, que se corrigió reemplazando CentOS por RockyLinux. 

Docker maneja automáticamente los reinicios de contenedores según el tipo de política configurada. 