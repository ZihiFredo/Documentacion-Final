# Proyecto Voxmapp

Sistema de flujo de datos que busca facilitar el uso y el análisis de información que recibe una empresa.


## Tabla de contenidos

+ [Información general](https://github.com/ZihiFredo/Documentacion-Final/blob/main/README.md#información-general)
+ [Tecnología usada](https://github.com/ZihiFredo/Documentacion-Final/blob/main/README.md#tecnología-usada)
+ [Características principales](https://github.com/ZihiFredo/Documentacion-Final/blob/main/README.md#características-principales)
+ [Uso](https://github.com/ZihiFredo/Documentacion-Final/blob/main/README.md#uso)
+ [Enlace de la encuesta](https://github.com/ZihiFredo/Documentacion-Final/blob/main/README.md#link-de-la-encuesta)
+ [Mejoras a futuro](https://github.com/ZihiFredo/Documentacion-Final/blob/main/README.md#mejoras-en-el-futuro)



## Información general

El proyecto crea una vía de datos que comienza recibiendo la información, se translada a una base de datos y una vez en la base de datos se organiza para poder analizarla.

Voxmapp es una empresa que se dedica a apoyar hospitales en países de menores recursos. Al ser países de bajos recursos, no existe la infraestructura para conseguir información vital para mantener y mejorar los hospitales. 

Nuestro proyecto busca mejorar su proceso de recepción y manejo de datos. Los datos de salud de hospitales se reciben a través de un cuestionario mensual que se llena por el personal de los hospitales. 

El sistema consiste de una encuesta que pregunta a los hospitales por información relevante. Las respuestas del cuestionario son guardadas en un _Google Sheets_. Posteriormente, las respuestas son transladadas a la base de datos que organiza la información. Por último, Voxmapp puede resolver problemas y ayudar a los hospitales usando, únicamente, la base de datos.


## Tecnología Usada

El proyecto funciona con cinco elementos:

1. ___Google forms___: mediante una encuesta recibe los datos para que la información pueda seguir su flujo.
2. ___Google sheets___: guarda la información de la encuesta que se pasará a la base de datos.
3. ___PostgresSQL___: gestiona la base de datos relacional orientada a objetos.
4. ___DBeaver___: para la manipulación y mantenimiento de la base de datos.
5. ___Tableu___: visualiza la información de la base de datos.

## Características principales

Primero, se responde el cuestinario en _Google Forms_.

![Google Forms 1](https://github.com/ZihiFredo/Documentacion-Final/blob/main/Captura%20de%20Pantalla%202022-05-22%20a%20la(s)%2022.41.09.png)
![Google Forms 2](https://github.com/ZihiFredo/Documentacion-Final/blob/main/Captura%20de%20Pantalla%202022-05-22%20a%20la(s)%2022.41.42.png)

Una vez contestada, las respuestas de la encuesta se guardan en el _Google Sheets_.

![Google Sheets](https://github.com/ZihiFredo/Documentacion-Final/blob/main/Captura%20de%20Pantalla%202022-05-22%20a%20la(s)%2022.51.14.png)


Después, la información se pasa a la base de datos. La información se almacena conforme al siguiente diagrama Entidad-Relación de la base de datos.

https://dbdiagram.io/embed/6098481db29a09603d141499

![ER_voxmapp_dbeaver](https://user-images.githubusercontent.com/77375206/117859721-fdcd0180-b254-11eb-8251-1de45397df5d.PNG)


De esta manera, se facilita la extracción y la búsqueda de los datos.

La información recaudada de las encuestas almacenadas en la base de datos se presenta de la siguiente forma: 

![Tabla parte 1](https://github.com/ZihiFredo/Documentacion-Para-Usuario-Final/blob/main/Captura%20de%20Pantalla%202022-03-12%20a%20la(s)%2013.44.59.png?raw=true)
![Tabla parte 2](https://github.com/ZihiFredo/Documentacion-Para-Usuario-Final/blob/main/Captura%20de%20Pantalla%202022-03-12%20a%20la(s)%2013.45.20.png)


Ejemplo de cómo la información puede ser analizada una vez en la base de datos, usando _Tableu_.

![Gráfica](https://github.com/ZihiFredo/Documentacion-Para-Usuario-Final/blob/main/Captura%20de%20Pantalla%202022-03-12%20a%20la(s)%2013.46.38.png)


## Uso

Para el uso del proyecto como usuario, creamos un aplicación de escritorio con _Visual Studio_. Una vez instalada, al acceder a la aplicación, se debe ingresar lo siguiente: usuario y contraseña. Una vez dentro de ella, los empleados de Voxmapp podrán acceder a las respuestas de las encuestas, y los trabajadores de los hospitales podrán completar la encuesta.

Para poder tener acceso completo al proyecto y poder utilizar de todas sus, muy útiles, herramientas se requiere instalar un par de cosas. Se debe conectar _Google Sheets_ a _Python_ y _Python_ a la base de datos. En el [manual de usuario](https://docs.google.com/document/d/1f8hk7zHd1ZKWIZ-X9rfSQJVDa396f0n6/edit) se describe cómo conectar _Google Sheets_ a _Python_ y _Python_ a la base de datos.


### Enlace de la encuesta

Dejamos el enlace de la [encuesta](https://docs.google.com/forms/d/1NnXM4PWHAKxzAtIaQ5KYfcVVXQNEB6snOr99RaMZijE/edit) para cualquier posible situación o necesidad que se presente.


### Mejoras a futuro

La principal mejora para el proyecto es la posibilidad de crear gráficas y vistas que contienen información que es pertinente para el cliente de manera más eficiente. Queremos mostrarlas de la mejor manera posible, por lo que estamos buscando poder conectar la base de datos con _Tableau_ porque nos permite mostrar las gráficas y las vistas fácilmente, sin tener que acceder directamente a la base de datos. 

Siempre estamos al pendiente de posibles errores y buscando mejoras. En caso de dudas, puede contactarnos a @ZihiFredo y @Borghin.
