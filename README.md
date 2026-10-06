<div align="center">
  
![DataScience](JP-DATA-tmagArticle.webp)

</div>

# Jeff Hammerbacher y el desarrollo de la infraestructura de datos y del Data Warehouse de Facebook

![Jeff Hammerbacher](https://img.shields.io/badge/L%C3%ADder-Jeff_Hammerbacher-blue)
![Data Warehouse](https://img.shields.io/badge/Infraestructura-Data_Warehouse-1877F2?logo=facebook&logoColor=white)
![Apache Hive](https://img.shields.io/badge/Tecnolog%C3%ADa-Apache_Hive-orange)
![Hadoop](https://img.shields.io/badge/Procesamiento-Apache_Hadoop-66CCFF)

> Jeff Hammerbacher, el cientifico del proyecto que vamos a analizar, estudió Matemáticas en Harvard, habia trabajado antes ya como analista cuantitativo y llegó a Facebook en 2006. Allí fundó y lideró el Data Team, un equipo que combinaba análisis, ingeniería y construcción de infraestructura de datos.

# ***Desarrollo de la infraestructura de Data Science y Data Warehouse de Facebook.***

Cuando Hammerbacher llegó a Facebook, existía una herramienta interna que se llamaba ***Watch Page***. Esta utilizaba las bases de datos MySQL que alimentaban el sitio y ejecutaba consultas para obtener información como el número de usuarios activos y su distribución entre  diferentes redes. Hammerbacher dice que su primera tarea habia sido crear una versión más profesional del sistema, osea un ***data warehouse*** capaz de recopilar un rango mucho más amplio de datos.

> [!WARNING]
> Un Data Warehouse es un sistema diseñado para reunir y organizar grandes cantidades de datos de Facebook en un lugar preparado específicamente para analizarlos.

Además de eso, las preguntas que el equipo quería responder estaban principalmente relacionadas con el crecimiento de Facebook. Como qué redes estaban creciendo, cuáles no y qué factores podían explicar ese crecimiento y/o decrecimiento.

Después, el crecimiento de los datos hizo que la infraestructura original dejara de ser suficiente. Facebook pasó de trabajar con aproximadamente 15 TB de datos en 2007 a ***2 PB***, y algunos procesos diarios que inicialmente tardaban más de un día podían realizarse en pocas horas utilizando Hadoop.

# ***Características del Proyecto.***

- [x] ¿Qué se hizo?
- [ ] ¿Qué información se utilizó?
- [ ] ¿Cómo se recopilaban los datos?
- [ ] ¿Cómo se procesaban los datos?
- [ ] ¿Qué función tenía el Data Warehouse?
- [ ] ¿Qué análisis se realizaba?
- [ ] Herramientas

# *¿QUÉ SE HIZO?*

Basicamente el objetivo principal era desarrollar una infraestructura que permitiera a Facebook aprovechar de la manera más eficiente los datos generados por sus usuarios.

El trabajo incluyó aspectos como:
<div>
  
- Crear y dirigir el equipo inicial de datos de Facebook.
- Desarrollar un Data Warehouse más profesional.
- Organizar la información para facilitar su análisis.
- Separar las tareas de análisis de las bases de datos utilizadas para el funcionamiento normal de Facebook.
- Desarrollar sistemas que fueran capaces de procesar cantidades cada vez mas grandes de información.
- Crear herramientas que permitieran realizar consultas sobre estos grandes conjuntos de datos.
- Usar los datos para entender el comportamiento de los usuarios y el crecimiento o tendencias de la plataforma.
</div>


# *¿QUÉ INFORMACIÓN SE UTILIZÓ?*
El proyecto usó información generada por la misma plataforma de Facebook.
Despliega para conocer algunos ejemplos más específicos de la información que usaron.
<details>
  
<Resumen> Haz click para desplejar mas info </Resumen>
- Actividad de los usuarios
- Usuarios activos
- Interacciones de los usuarios
- Crecimiento de la red
- Uso de productos
- Actividad dentro de la plataforma
- Registros generados por los sistemas

</details>

# *¿CÓMO SE RECOPILABAN LOS DATOS?*
Los datos provenían principalmente de la actividad que ocurría dentro de Facebook, como ya lo mencionamos arriba.

Cada interacción de los usuarios con la plataforma podía generar información útil para entender el comportamiento y el crecimiento de Facebook.

A medida que el tamaño de Facebook aumentó, fue necesario desarrollar sistemas especializados para recopilar y transportar grandes cantidades de registros.

Uno de estos sistemas fue ***Scribe***, desarrollado por Facebook para recopilar y transportar grandes volúmenes de datos provenientes de los registros de los sistemas.

> [!WARNING]
> Scribe funcionaba como un sistema de recopilación y transporte de registros ***(logs)*** dentro de la infraestructura de datos de Facebook. Los diferentes servidores de Facebook generaban de forma continua información sobre las actividades que ocurrían en la plataforma, y Scribe recibía esos registros desde muchos servidores, los organizaba y los enviaba hacia sistemas de almacenamiento para que pudieran ser procesados luego. Podemos decir que Scribe actuaba como un intermediario entre los servidores que generaban los datos y la infraestructura donde esos datos eran almacenados y analizados.

# *¿CÓMO SE PROCESABAN LOS DATOS?*

A medida que aumentaba la cantidad de información, las ***bases de datos tradicionales*** dejaron de ser suficientes para algunas tareas de análisis. Entonces Facebook comenzó a utilizar ***tecnologías de procesamiento distribuido***, que permitían dividir los datos y las tareas entre diferentes computadores. Una de las tecnologías más importantes fue Hadoop.

<img src="03hadoop-logo.jpg" width="200" />

Hadoop permitió procesar grandes cantidades de información utilizando múltiples computadores en lugar de depender de una sola máquina.

<img src="hadoopi.jpg" width="200" />
Hadoop Distributed File System, permitió distribuir grandes cantidades de información entre diferentes máquinas.

<img src="MapReduce-esquema-1024x615.png.webp" width="200" />
MapReduce permitió dividir las tareas de procesamiento en diferentes operaciones que podían ejecutarse de manera distribuida.

<img src="Apache_Hive_logo.svg" width="200" />
Hive permitió realizar consultas sobre grandes cantidades de datos almacenados en Hadoop mediante un sistema de consultas de más alto nivel.


# *¿QUÉ FUNCIÓN TENÍA EL DATA WAREHOUSE?*

El Data Warehouse era bastante importante porque Facebook generaba información desde diferentes partes de su plataforma. Entonces, en lugar de hacer todos los análisis directamente sobre las bases de datos que utilizaba Facebook para funcionar, la información podía organizarse en un sistema diseñado específicamente para el análisis.

Entonces podemos decir que se dividía en: Una base de datos operacional (En donde el usuario inicia sesión, Facebook consulta una base de datos y muestra la informacipon) y por otra parte en Data Warehouse (En donde hay millones de actividades que pasan a través de Data Warehouse, y este realiza las consultas previas al análisis)

# *¿QUÉ ANÁLISIS SE REALIZABA?*
> ¿Cuántos usuarios estaban activos?
> ¿Qué tan rápido estaba creciendo la red?
> ¿Cómo estaban distribuidos los usuarios?
> ¿Cómo interactuaban los usuarios con la plataforma?
> ¿Cómo cambiaba el uso de los productos?
> ¿Qué patrones podían identificarse en la actividad de los usuarios?


# *HERRAMIENTAS*

|Herramienta                 | Función                                |
|----------------------------------------|-------------------------------------------------------------------|
| MySQL    | Base de datos utilizada en los primeros sistemas de Facebook                       | 
|Data Warehouse|Organización y almacenamiento de datos para análisis                |
|Hadoop |Procesamiento distribuido de grandes cantidades de datos|
|HDFS   | Almacenamiento distribuido |
|MapReduce| Procesamiento distribuido|
|Hive| Consultas sobre grandes conjuntos de datos|
|Scribe| Recopilación y transporte de registros |

- [x] ¿Qué se hizo?
- [x] ¿Qué información se utilizó?
- [x] ¿Cómo se recopilaban los datos?
- [x] ¿Cómo se procesaban los datos?
- [x] ¿Qué función tenía el Data Warehouse?
- [x] ¿Qué análisis se realizaba?
- [x] Herramientas

# *¿CUÁL FUE EL IMPACTO DE TODO ESTE PROYECTO?*

El proyecto permitió desarrollar una forma mucho más estructurada de utilizar sus datos. La empresa avanzo hacia una organización más orientada a los datos, en la que la información podía utilizarse para comprender:

- El comportamiento de los usuarios.
- El crecimiento de la plataforma.
- El uso de los productos.
- Los cambios dentro de la red.

Además, este proyecto y sus funciones tuvieron impacto en el campo de Big Data.


