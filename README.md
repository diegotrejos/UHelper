# U Helper
![](https://i.imgur.com/oVTolaU.png)

**Aplicación U Helper**

**Documento de conceptualización**

**Versión 4.0 de la aplicación**

**Versión 4.0 del documento**

[TOC]

## Introducción

El propósito de este documento es explicar detalladamente el proceso de desarrollo que se llevó a cabo para la creación de la aplicación U Helper. De manera específica, busca mencionar la metodología que siguió el proyecto, las tecnologías y artefactos utilizados y los objetivos de la aplicación. Este documento está estructurado de manera que primero se mostrará una breve introducción del proyecto junto a los desarrolladores de la aplicación. Posteriormente, en la descripción general, se abarcará el propósito y las funcionalidades de la aplicación (también mediante prototipos). Finalmente se mostrarán los aspectos técnicos y más "internos" al desarrollo del proyecto, que son los artefactos de la base de datos y las decisiones técnicas realizadas.  

El objetivo principal de la aplicación U Helper es facilitar, mediante distintas funcionalidades específicas, la experiencia universitaria de los estudiantes de la Universidad de Costa Rica. De una manera más concreta, esta aplicación busca facilitar los procesos de: comunicación con distintas instituciones de la Universidad de Costa Rica (mediante un acceso rápido a los contactos), manejar un horario de los cursos matriculados en el semestre y encontrar la ubicación de la clase de cada curso matriculado.   

## Listado de equipos y miembros de los equipos

### Sprint 1

* Look and feel
* Scrum Master
* Database master
* Documentación

| Name | Carné | Rol |
| ------ | ------ | ----- |
| Daniel Salazar Mora | B87214 |Documentación|
| Ricardo Franco Rodriguez| B83050 |Database master|
| Josué Araya Murillo| B30478 |Look and feel|
| Diego Trejos Echeverria | B57233 |Scrum Master|
| Denis Solano Padilla | B59304 |Look and feel|

---

### Sprint 2

| Name                     | Carné  | Rol             |
| ------------------------ | ------ | --------------- |
| Daniel Salazar Mora      | B87214 | Documentación   |
| Ricardo Franco Rodriguez | B83050 | Database master |
| Josué Araya Murillo      | B30478 | Look and feel   |
| Diego Trejos Echeverria  | B57233 | Scrum Master    |
| Denis Solano Padilla     | B59304 | Look and feel   |

---

### Sprint 3

| Name                     | Carné  | Rol             |
| ------------------------ | ------ | --------------- |
| Daniel Salazar Mora      | B87214 | Documentación   |
| Ricardo Franco Rodriguez | B83050 | Database master |
| Josué Araya Murillo      | B30478 | Look and feel   |
| Diego Trejos Echeverria  | B57233 | Scrum Master    |
| Denis Solano Padilla     | B59304 | Look and feel   |

---

### Sprint 4

| Name                     | Carné  | Rol             |
| ------------------------ | ------ | --------------- |
| Daniel Salazar Mora      | B87214 | Documentación   |
| Ricardo Franco Rodriguez | B83050 | Database master |
| Josué Araya Murillo      | B30478 | Look and feel   |
| Diego Trejos Echeverria  | B57233 | Scrum Master    |
| Denis Solano Padilla     | B59304 | Look and feel   |



## Descripción general

### Descripción

Antes de describir la aplicación en sí, es mejor contextualizar la razón de la existencia de UHelper. No conocer a fondo la Universidad de Costa Rica, puede resultar muy estresante para los estudiantes y más para los de primer ingreso. El tener que preocuparse porque no se sabe dónde se va a recibir la clase debería ser el menor de los problemas. Por lo tanto, se nos ocurrió la solución que presenta la aplicación UHelper. En el app, se selecciona el aula del curso respectivo, y se obtiene la dirección del edificio en Google Maps y además, una breve descripción de la ubicación del aula dentro de dicho edificio. Esta funcionalidad se relaciona directamente con el epic "Localización de aulas" presentado en el backlog.

Aunque esa es la funcionalidad principal, este app también busca facilitar otras funcionalidades, como la de tener el horario y tener una agenda con los contactos a las instituciones dentro de la Universidad de Costa Rica. Estas funcionalidades se relacionan con los epics de "Administración del horario de usuario" e "Información de contactos de ayuda-asistencia" respectivamente. Para poder tener todas estas funcionalidades dentro del mismo app, se recurre al epic de "Navegación" que propone la creación del drawer que contendrá las opciones para que el usuario pueda seleccionarlas fácilmente.

Finalmente, hay que almacenar todos estos datos del usuario y justamente es lo que propone el epic "Administración de perfiles" ya que crea usuarios, con sus respectivos correos electrónicos y contraseñas como autorización, que pueden tener toda la información mencionada anteriormente relacionada directamente a su perfil.

### Requerimientos funcionales

* **R1:** Que el usuario pueda crear una nueva cuenta con su información personal para que pueda utilizar la aplicación. Este requerimiento se relaciona directamente con la historia de usuario MV2021A3-6.
* **R2:** El usuario requiere poder iniciar sesión al utilizar sus credenciales de manera correcta para poder utilizar las funcionalidades que provee la aplicación. Este requerimiento se relaciona directamente con la historia de usuario MV2021A3-7. 
* **R3:** El usuario requiere de un menú (drawer) en todas las pantallas para poder tener una experiencia agradable de navegación dentro del app a la hora de buscar funcionalidades. Este requerimiento se relaciona directamente con la historia de usuario MV2021A3-65.
* **R4:** El usuario requiere de tener a disposición una agenda con contactos oficiales de instituciones dentro de la Universidad de Costa Rica para facilitar su posibilidad de comunicarse adecuadamente con ellas (y de una manera rápida). Este requerimiento se relaciona directamente con la historia de usuario MV2021A3-18.
* **R5:** El usuario requiere poder editar la información de su perfil para poder actualizar sus datos personales cuando sea necesario. Este requerimiento se relaciona directamente con la historia de usuario MV2021A3-10.
* **R6:** El usuario requiere poder cambiar su contraseña cuando la haya olvidado o por gusto propio por motivos de seguridad. Este requerimiento se relaciona directamente con la historia de usuario MV2021A3-9.
* **R7:** El usuario requiere poder observar su horario para saber cuáles cursos tiene un determinado día. Este requerimiento se relaciona directamente con la historia de usuario MV2021A3-12.
* **R8:** El usuario requiere poder editar su horario para agregar nuevos cursos en su horario. Este requerimiento se relaciona directamente con la historia de usuario MV2021A3-13.
* **R9:** El usuario requiere poder editar su horario para borrar cursos de su horario. Este requerimiento se relaciona directamente con la historia de usuario MV2021A3-14.
* **R10:** El usuario requiere poder ver la ubicación de un aula, mediante Google Maps y una descripción, para que pueda encontrarla de una manera más sencilla. Este requerimiento se relaciona directamente con las historias de usuario MV2021A3-70, MV2021A3-71 y MV2021A3-78.
* **R11:**  El usuario requiere que después de iniciar sesión, el sistema recuerde su cuenta y no le solicite credenciales la próxima vez que abra el app para así ahorrarse el tiempo de escribir datos que ya ha puesto. Este requerimiento se relaciona directamente con la historia de usuario MV2021A3-67.
* **R12:** El usuario requiere poder cerrar sesión para asegurar la privacidad de su cuenta por si iniciara sesión en otros dispositivos o en situaciones similares. Este requerimiento se relaciona directamente con la historia de usuario MV2021A3-66.
* **R13:** El usuario requiere de poder ver recordatorios institucionales para organizar su tiempo y tener la información al día con la universidad. Este requerimiento se relaciona directamente con la historia de usuario MV2021A3-133 y MV2021A3-189.
* **R14:** El usuario requiere de poder ver sus recordatorios personalizados para organizar su tiempo y tener su información al día. Este requerimiento se relaciona directamente con la historia de usuario MV2021A3-198.
* **R15:** El usuario requiere de poder agregar recordatorios personalizados para organizar su tiempo y tener su información al día. Este requerimiento se relaciona directamente con la historia de usuario MV2021A3-134.
* **R16:** El usuario requiere de poder eliminar recordatorios personalizados para corregirlo o simplemente para tener su información al día. Este requerimiento se relaciona directamente con la historia de usuario MV2021A3-135.
* **R17:** El usuario requiere de poder recuperar su contraseña en caso de que la haya olvidado. Este requerimiento se relaciona directamente con la historia de usuario MV2021A3-8.

### Requerimientos no funcionales

* **R1:** Realizar llamados a la base de datos de manera asincrónica para asegurar que el thread principal se encargue de la interfaz con la que interactúa el usuario.
* **R2:** El usuario puede acceder a las funcionalidades principales del app de la manera más simple posible desde el menú.
* **R3:** La aplicación no aceptará contraseñas menores a 4 caracteres por cuestiones de seguridad.
* **R4:** La aplicación no aceptará registrar más de una cuenta relacionada a un mismo correo por cuestiones de identificación y seguridad.
* **R5:** La aplicación no aceptará un carné que no esté conformado por una letra y cinco números o por seis números.
* **R6:** La aplicación no aceptará correos que no sea de la Universidad de Costa Rica (formato: @ucr.ac.cr).
* **R7:** El usuario requiere poder tener la información más actualizada de la aplicación para que pueda tener toda la información al día y es correcta. Este requerimiento se relaciona directamente con las historias de usuario MV2021A3-126 y MV2021A3-124.
* **R8:** El usuario requiere que sus cambios realizados en la aplicación se actualicen en la nube para asegurar que su información está bien almacenada y puede acceder a ella desde otros dispositivos. Este requerimiento se relaciona directamente con las historias de usuario MV2021A3-127 y MV2021A3-124.
* **R9:** La aplicación no aceptará un nombre de curso más largo que 40 caracteres.
* **R10:** La aplicación no permitirá que un mismo curso esté más de una vez en el mismo día.
* **R11:** La aplicación no permitirá agregar cursos en horas antes de las 7 am ni después de las 10 pm.
* **R12:** La aplicación no permitirá agregar más de 10 cursos en un mismo día.
* **R13:** La aplicación generará códigos diferentes para mandar por correo electrónico y verificar la identidad del usuario.
* **R14:** La aplicación no permitirá más de 3 intentos de escribir el código único para recuperar la contraseña

## Prototipos de la aplicación

A continuación se muestran algunos prototipos de manera muy general. Para ver la totalidad de los prototipos, se presenta el siguiente enlace: https://www.figma.com/file/WofkkGz5UD7ZUjpHCeICRK/U-helper?node-id=0%3A1

### Página de inicio
![](https://i.imgur.com/TBFJCiU.png)

### Actividad de iniciar sesión

![](https://i.imgur.com/JyTq5fB.png)

---

![](https://i.imgur.com/reyXf6Z.png)


### Actividad de registro
![](https://i.imgur.com/9EYceMa.png)

---

![](https://i.imgur.com/3Zb1XIN.png)


### Actividad de ver contactos
![](https://i.imgur.com/0Ssvb02.png)

---

![](https://i.imgur.com/CKMJ5uy.png)

### Drawer
![](https://i.imgur.com/y1lpehb.png)

### Actividad de editar perfil
![](https://i.imgur.com/h5nQgWG.png)

---
![](https://i.imgur.com/DbqvDbT.png)

---
![](https://i.imgur.com/ZZYGKmd.png)

### Actividad de buscar aula

![](https://i.imgur.com/ChVYObI.png)





### Actividad de ver horario

![](https://i.imgur.com/yUnSe7E.png)

### Actividad de eliminar curso de un horario

![](https://i.imgur.com/6zPB1Ej.png)



### Actividad de agregar curso a un horario

![](https://i.imgur.com/HkbnZEh.png)



### Actividad de recordatorios institucionales

![image-20210704212024106](C:\Users\Daniel Salazar\AppData\Roaming\Typora\typora-user-images\image-20210704212024106.png)

---



![image-20210704212103119](C:\Users\Daniel Salazar\AppData\Roaming\Typora\typora-user-images\image-20210704212103119.png)

### Actividad de "Mis Recordatorios"

![image-20210725194919679](C:\Users\Daniel Salazar\AppData\Roaming\Typora\typora-user-images\image-20210725194919679.png)

---

![image-20210725194936733](C:\Users\Daniel Salazar\AppData\Roaming\Typora\typora-user-images\image-20210725194936733.png)



### Actividad de Recuperar contraseña

![](https://i.imgur.com/T1LLjFR.png)





![](https://i.imgur.com/RTRNzHd.png)

## Casos de prueba

Se realizaron 3 de casos de prueba en la aplicación. A continuación se muestran, sin embargo, si desea observarlos a detalle, se encuentran en el siguiente enlace: https://docs.google.com/document/d/1pvT1CizOcl9_G0us4j03WSNhWokWrkVddAaxYrvDITI/edit?usp=sharing

### Caso de prueba 1: Agregar dos cursos a la misma hora



![](https://i.imgur.com/kKhUGUH.png)

---



![image-20210705210516538](C:\Users\Daniel Salazar\AppData\Roaming\Typora\typora-user-images\image-20210705210516538.png)



### Caso de prueba 2: Agregar el mismo curso dos veces en un día

![](https://i.imgur.com/UouYyEh.png)

---

![](https://i.imgur.com/udyxi8p.png)



### Caso de prueba 3: Agregar un curso en un día donde no está agregado

![image-20210705211701265](C:\Users\Daniel Salazar\AppData\Roaming\Typora\typora-user-images\image-20210705211701265.png)

---

![](https://i.imgur.com/PMgDtgW.png)



## Artefactos de la base de datos

### Esquema conceptual base de datos local

Se realizó un esquema conceptual EER de la base de datos, utilizando la herramienta de Lucidchart. A continuación se presenta una imagen de dicho esquema y el link donde se encuentra para poder verlo a mayor detalle. 
Enlace: https://lucid.app/lucidchart/invitations/accept/inv_7565cbfd-a123-4af1-b2b4-d05283d3847c

![](https://i.imgur.com/MlN5eW7.png)



### Estructura de base de datos en la nube

Se utiliza una base de datos a tiempo real dada por Firebase como la base de datos en la nube. Cabe destacar que es una base de datos NoSQL. pero se le estructuró de una manera que facilita el manejo de datos y su procesamiento. La siguiente estructura se puede visualizar de la siguiente manera:

![](https://i.imgur.com/Yvgy5pj.png)

## Decisiones técnicas

### Metodología

En este proyecto se aplicó una metodología ágil scrum, por lo que a los miembros del equipo se le asignaron roles específicos para dividirse distintas responsabilidades. Se aplicaron las respectivas acciones que caracterizan a las metodologías ágiles, como las reuniones de control de avances de funcionalidades y las reuniones de validación con el PO y/o interesados en el proyecto. Sin embargo, debido al contexto de pandemia se recurrió a la virtualidad en la comunicación entre miembros y con el PO o interesados en el proyecto, mediante las plataformas de Discord y Zoom.

### Artefactos utilizados

* Documento con protipos (realizado en Figma)
* Documento de conceptualización
* Documento del esquema conceptual de la base de datos (realizado en Lucidchart)
* Código (realizado con Java en Android Studio)
* Backlog para organización de tareas (realizado en Jira)
* Documento de texto con los casos de prueba

### Tecnología

Se utilizó Java como lenguaje de programación, en el ambiente de Android Studio. En la aplicación se utiliza la versión de Android 5.0, nivel del API 21 (como mínimo) y además, la base de datos es la de SQLite con la biblioteca de Room para facilitar el manejo de los datos. También se utiliza otra base de datos de manera remota (en la nube), la cual equivale a la base de datos a tiempo real de Firebase verisón 23.0.1. El manejo de la distribución de tareas fue realizado con Jira. Se utiliza la librería externa de gantonius/MaterialDayPicker para el manejo de seleccionar días en un curso y el api de Java Mail para enviar correos electrónicos (usando la cuenta de la aplicación: info.uhelper@gmail.com) para que el usuario pueda recuperar su contraseña si se le olvida.

### Formatos de los commits

Cada commit, si es de funcionalidad, deberá mencionar: breve descripción de cambios, desarrolladores que trabajaron, id historia de usuario y subtarea técnica respectiva (si la tiene) y como opcional WIP (work in progress).

Si el commit es un arreglo, se deberá mencionar el tipo y brevemente qué se arreglo. 

### Repositorio de código y estrategia de branches

El código se encuentra en el siguiente repositorio de Bitbucket: https://bitbucket.org/lyonv/ecci_ci0161_i2021_g01_t03

Con respecto a la estrategia de branches, nuestro enfoque es el de trabajar por funcionalidades. De esta manera, los branches serán nombrados acorde a a la funcionalidad y facilitará el pair-programming entre miembros del equipo. Además, al tener el nombre de la funcionalidad será más sencillo de identificarlo en caso de que se requiera. También es importante mencionar que se utilizó la técnica de integración continua y que se utilizaron pull requests para realizar commits en máster (requeriendo un mínimo de dos vistos buenos). 

### Definición de listo

Para subir un commit a master, se debe realizar la técnica de jalar master dentro de la rama a mezclar y posteriormente asegurarse que: 

- No rompa la arquitectura.

- Debe completar una tarea técnica.

- Seguir principios de *clean code* básico.

- Master continúe funcional.

- La historia de usuario relacionada a la funiconalidad debe estar ya validada por el PO.

