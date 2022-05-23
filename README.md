# Proyecto Voxmapp

Sistema de flujo de datos que busca faciitar el uso y el analisis de información que recibe una empresa


## Tabla de contenidos

+ [Información General](https://github.com/ZihiFredo/Documentacion-Final/blob/main/README.md#información-general)
+ [Tecnología usada](https://github.com/ZihiFredo/Documentacion-Final/blob/main/README.md#tecnología-usada)
+ [Características principales](https://github.com/ZihiFredo/Documentacion-Final/blob/main/README.md#características-principales)
+ [Uso](https://github.com/ZihiFredo/Documentacion-Final/blob/main/README.md#uso)
+ [Estatus del Proyecto](https://github.com/ZihiFredo/Documentacion-Final/blob/main/README.md#estatus-del-proyecto)
+ [Mejoras del Proyecto](https://github.com/ZihiFredo/Documentacion-Final/blob/main/README.md#mejoras-en-el-futuro)
+ [Link de la Encuesta](https://github.com/ZihiFredo/Documentacion-Final/blob/main/README.md#link-de-la-encuesta)


## Información general

El proyecto crea una via de datos la cual comienza recibiendo la informacion, se translada a una base de datos y una vez en la base de datos se organiza para poder analizarla.

Voxmapp es una empresa que se dedica a apoyar hospitales en países de menores recursos. Al ser paises de bajos recursos no existe la infraestructura para conseguir informacion vital para mantener y mejorar los hospitales. Es por esto que buscamos mejorar su proceso de recepción y manejo de datos. Estos datos se basan en la infraestructura de salud de hospitales se reciben a través de un cuestionario mensual que se llena por el personal de los hospitales. 

El sistema consiste de una encuesta la cual pregunta a los hospitales por informacion relevantl. Las respuestas de el cuestionario son guardada en un google sheets. Mas adelante, estas respuestas son transladadas a una base de datos la cual organiza la informacion. Por ultimo, ya en la base de datos, la informacion puede ser accesda facilmente y asi Voxmapp puede mas facilemente resolver problemas y ayudar a los hospitales.


## Tecnología Usada

El proyecto funciona con cuatro elementos:

1. __Google forms__: mediante una encuesta recibe los datos para que la información pueda seguir su flujo.
2. __Google sheets__: guarda la información de la encuesta que se pasará a la base de datos.
3. __PostgresSQL__: gestiona la base de datos relacional orientada a objetos.
4. __DBeaver__: para la manipulación y mantenimiento de la base de datos.

## Características principales

Primero, se responde a el cuestinario en el google sheets:

PONER SCREENSHOT DEL GOOGLE FORMS


Una vez contestada, las respuestas de la encuesta se guardan en el google sheets:

PONER SCREENSHOT DEL GOOGLE SHEET


Despues, la informacion se pasan a la base de datos. La informacion se almacena conforme al siguiente diagrama Entidad-Relación de la base de datos: 

https://dbdiagram.io/embed/6098481db29a09603d141499

![ER_voxmapp_dbeaver](https://user-images.githubusercontent.com/77375206/117859721-fdcd0180-b254-11eb-8251-1de45397df5d.PNG)


De esta manera se facilita la extraccion y la busqueda de los datos 

La información recaudada de las encuestas almacenadas en la base de datos se presenta de la siguiente forma: 

![Tabla parte 1](https://github.com/ZihiFredo/Documentacion-Para-Usuario-Final/blob/main/Captura%20de%20Pantalla%202022-03-12%20a%20la(s)%2013.44.59.png?raw=true)
![Tabla parte 2](https://github.com/ZihiFredo/Documentacion-Para-Usuario-Final/blob/main/Captura%20de%20Pantalla%202022-03-12%20a%20la(s)%2013.45.20.png)


Ejemplo de como la informacion puede ser analizada una vez en la base de datos, se utiliza tableu en este caso:

![Gráfica](https://github.com/ZihiFredo/Documentacion-Para-Usuario-Final/blob/main/Captura%20de%20Pantalla%202022-03-12%20a%20la(s)%2013.46.38.png)


## Uso

Para el uso del proyecto como usuario, creamos un aplicación de escritorio con Visual Studio. Una vez instalada, al acceder a la aplicación, se debe ingresar lo siguiente: usuario y contraseña. Una vez dentro de ella, los empleados de Voxmapp podrán acceder a las respuestas de las encuestas, y los trabajadores de los hospitales podrán completar la encuesta.


Para poder tener acceso completo al proyecto y poder utilizar de todas sus, muy útiles, herramientas se requiere instalar un par de cosas. Se debe conectar Google Sheets a Python y Python a la base de datos. En el [manual de usuario](https://docs.google.com/document/d/1f8hk7zHd1ZKWIZ-X9rfSQJVDa396f0n6/edit) se decribe como conectar google sheets a pyhton y pyhton a la base de datos


### Link de la encuesta

Dejamos el link de la [encuesta](https://docs.google.com/forms/d/1NnXM4PWHAKxzAtIaQ5KYfcVVXQNEB6snOr99RaMZijE/edit) para cualquier posible situación o necesidad que se presente


### Mejoras a futuro

La principal mejora para el proyecto es la posibilidad de crear gráficas y vistas que contienen información que es pertinente para el cliente de manera más eficiente. Queremos mostrarlas de la mejor manera posible, por lo que estamos buscando poder conectar la base de datos con Tableau porque nos permite mostrar las gráficas y las vistas fácilmente, sin tener que acceder directamente a la base de datos. 


## Estatus del Proyecto

El proyecto actualmente está terminado; sin embargo, siempre estamos arreglando errores y buscando posibles mejoras. @ZihiFredo @Borghin
