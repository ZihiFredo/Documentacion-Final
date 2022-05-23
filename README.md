# Proyecto Voxmapp

Sistema de flujo de datos que busca faciitar el uso y el analisis de información que recibe una empresa


## Tabla de contenidos

+ [Información General](https://github.com/ZihiFredo/Documentacion-Para-Usuario-Final/blob/main/README.md#información-general)
+ [Tecnología usada](https://github.com/ZihiFredo/Documentacion-Para-Usuario-Final/blob/main/README.md#tecnología-usada)
+ [Características principales](https://github.com/ZihiFredo/Documentacion-Para-Usuario-Final/blob/main/README.md#características-principales)
+ [Set up](https://github.com/ZihiFredo/Documentacion-Para-Usuario-Final/blob/main/README.md#set-up)
+ [Uso](https://github.com/ZihiFredo/Documentacion-Para-Usuario-Final/blob/main/README.md#uso)
+ [Estatus del Proyecto](https://github.com/ZihiFredo/Documentacion-Para-Usuario-Final/blob/main/README.md#estatus-del-proyecto)
+ [Mejoras del Proyecto](https://github.com/ZihiFredo/Documentacion-Para-Usuario-Final/blob/main/README.md#mejoras-en-el-futuro)
+ [Link de la Encuesta](https://github.com/ZihiFredo/Documentacion-Para-Usuario-Final/blob/main/README.md#link-de-la-encuesta)


## Información general

El proyecto crea una via de datos la cual comienza recibiendo la informacion, se translada a una base de datos y una vez en la base de datos se organiza para poder analizarla.

Voxmapp es una empresa que se dedica a apoyar hospitales en países de menores recursos. Al ser paises de bajos recursos no existe la infraestructura para conseguir informacion vital para mantener y mejorar los hospitales. Es por esto que buscamos mejorar su proceso de recepción y manejo de datos. Estos datos se basan en la infraestructura de salud de hospitales se reciben a través de un cuestionario mensual que se llena por el personal de los hospitales. 

El sistema consiste de una encuesta la cual pregunta a los hospitales por informacion relevantl. Las respuestas de el cuestionario son guardada en un google sheets. Mas adelante, estas respuestas son transladadas a una base de datos la cual organiza la informacion. Por ultimo, ya en la base de datos, la informacion puede ser accesda facilmente y asi Voxmapp puede mas facilemente resolver problemas y ayudar a los hospitales.


## Tecnología Usada

Se utilizan principalmente 4 elementos grandes para que el proyecto funcione:

1. __Google forms__: aquí es donde se creó la encuesta y se reciben los datos para que la información pueda seguir su flujo.
2. __Google sheets__: se guarda la información de la encuesta para poder pasara a la base de datos.
3. __PostgresSQL__: PostgreSQL es un sistema de gestión de bases de datos relacional orientado a objetos que utilizamos para poder crear la base de datos.
4. __DBeaver__: DBeaver es una aplicación de software cliente de SQL para la manipulación y mantenimiento de las bases de datos.

## Características principales

### Screenshot

#### Ejemplo de una gráfica

A continuación, se muestra una gráfica creada a partir de la información recaudada de las encuestas almacenadas en la base de datos junto con el código para poder observar los datos graficados.

Tiempo promedio de reservas: Tiempo promedio existente de reservas para cada recurso registrado en cada hospital, así como sus características geográficas.



###### Tablas en la base de datos

![Tabla parte 1](https://github.com/ZihiFredo/Documentacion-Para-Usuario-Final/blob/main/Captura%20de%20Pantalla%202022-03-12%20a%20la(s)%2013.44.59.png?raw=true)
![Tabla parte 2](https://github.com/ZihiFredo/Documentacion-Para-Usuario-Final/blob/main/Captura%20de%20Pantalla%202022-03-12%20a%20la(s)%2013.45.20.png)

###### Gráfica

![Gráfica](https://github.com/ZihiFredo/Documentacion-Para-Usuario-Final/blob/main/Captura%20de%20Pantalla%202022-03-12%20a%20la(s)%2013.46.38.png)

###### Código

```python
--

create view necesidades_hospital as(
	with reservas_num as (
		select
		    case r.oxygen_reserves 
		      when 'Yes, for 30 days' then 30
		      when 'Yes, for 15 days' then 15
		      when 'Yes, for 7 days' then 7
		      when 'Yes, for 3 days' then 3
		      when 'No' then 0
		    end as oxygen_reserves_num,
		    case r.antipyretics_reserves 
		      when 'Yes, for 30 days' then 30
		      when 'Yes, for 15 days' then 15
		      when 'Yes, for 7 days' then 7
		      when 'Yes, for 3 days' then 3
		      when 'No' then 0
		    end as antipyretics_reserves_num,
		    case r.anesthetics_and_muscular_relaxants
		      when 'Yes, for 30 days' then 30
		      when 'Yes, for 15 days' then 15
		      when 'Yes, for 7 days' then 7
		      when 'Yes, for 3 days' then 3
		      when 'No' then 0
		    end as anesthetics_and_muscular_relaxants_num,
		    case r.alcohol_reserves_and_handsoap
		      when 'Yes, for 30 days' then 30
		      when 'Yes, for 15 days' then 15
		      when 'Yes, for 7 days' then 7
		      when 'Yes, for 3 days' then 3
		      when 'No' then 0
		    end as alcohol_reserves_and_handsoap_num,
		    case r.personal_disposable_masks
		      when 'Yes, for 30 days' then 30
		      when 'Yes, for 15 days' then 15
		      when 'Yes, for 7 days' then 7
		      when 'Yes, for 3 days' then 3
		      when 'No' then 0
		    end as personal_disposable_masks_num,
		    case r.personal_vinyl_gloves
		      when 'Yes, for 30 days' then 30
		      when 'Yes, for 15 days' then 15
		      when 'Yes, for 7 days' then 7
		      when 'Yes, for 3 days' then 3
		      when 'No' then 0
		    end as personal_vinyl_gloves_num,
		    case r.personal_disposable_hats
		      when 'Yes, for 30 days' then 30
		      when 'Yes, for 15 days' then 15
		      when 'Yes, for 7 days' then 7
		      when 'Yes, for 3 days' then 3
		      when 'No' then 0
		    end as personal_disposable_hats_num,
		    case r.personal_disposable_aprons
		      when 'Yes, for 30 days' then 30
		      when 'Yes, for 15 days' then 15
		      when 'Yes, for 7 days' then 7
		      when 'Yes, for 3 days' then 3
		      when 'No' then 0
		    end as personal_disposable_aprons_num,
		    case r.personal_visors
		      when 'Yes, for 30 days' then 30
		      when 'Yes, for 15 days' then 15
		      when 'Yes, for 7 days' then 7
		      when 'Yes, for 3 days' then 3
		      when 'No' then 0
		    end as personal_visors_num,
		    case r.personal_disposable_shoe_covers
		      when 'Yes, for 30 days' then 30
		      when 'Yes, for 15 days' then 15
		      when 'Yes, for 7 days' then 7
		      when 'Yes, for 3 days' then 3
		      when 'No' then 0
		    end as personal_disposable_shoe_covers_num,
		    r.num_test_kits,
		    r.respiratory_ventilator_machines,
		    r.reservas_id,
		    r.update_id
			from reservas r join update_ u on(r.reservas_id=u.update_id) join control_ c on(c.update_id=u.update_id)
			where c.update_status like '%completed%' 
	), health_levels as (
		select u.moph_number as hos_id, avg(reservas_num.oxygen_reserves_num) as avg_oxygen, avg(reservas_num.antipyretics_reserves_num) as avg_antipyretics, avg(reservas_num.anesthetics_and_muscular_relaxants_num) as avg_anesthetics, avg(reservas_num.alcohol_reserves_and_handsoap_num) as avg_alcohol, avg(reservas_num.personal_disposable_masks_num) as avg_masks, avg(reservas_num.personal_disposable_aprons_num) as avg_aprons, avg(reservas_num.personal_vinyl_gloves_num) as avg_gloves, avg(reservas_num.personal_disposable_hats_num) as avg_hats, avg(reservas_num.personal_visors_num) as avg_visors, avg(reservas_num.personal_disposable_shoe_covers_num) as avg_shoe_covers, avg(reservas_num.num_test_kits) as avg_test, avg(reservas_num.respiratory_ventilator_machines) as avg_venti
		from update_ u join reservas_num  using (update_id) join control_ c using (update_id)
		where c.update_status like '%completed%' and c.problem like '%none%' and u.update_date <= current_date and u.update_date > (current_date - '1 month'::interval)
		group by u.moph_number
		order by u.moph_number
	)
	select h.moph_number, h.hospital_name, h.district, h.province, health_levels.avg_oxygen, health_levels.avg_antipyretics, health_levels.avg_anesthetics, health_levels.avg_alcohol, health_levels.avg_masks, health_levels.avg_aprons, health_levels.avg_gloves, health_levels.avg_hats, health_levels.avg_visors,health_levels.avg_shoe_covers, health_levels.avg_test,  health_levels.avg_venti
	from hospital h join health_levels  on (health_levels.hos_id = h.moph_number)
	order by h.moph_number
)
```

#### Diagrama-ER

Se presenta el diagrama Entidad-Relación de la base de datos hecho con db.diagram.io
https://dbdiagram.io/embed/6098481db29a09603d141499

y el que se muestra en DBeaver

![ER_voxmapp_dbeaver](https://user-images.githubusercontent.com/77375206/117859721-fdcd0180-b254-11eb-8251-1de45397df5d.PNG)

### Set up

Para usar la aplicación como usuario solo se requiere instalar la aplicación de escritorio.

Para poder tener acceso completo al proyecto y poder utilizar de todas sus, muy útiles, herramientas se requiere instalar un par de cosas. Se debe conectar Google Sheets a Python y Python a la base de datos. A continuación, dejamos el link para acceder al manual de usuario:

https://docs.google.com/document/d/1f8hk7zHd1ZKWIZ-X9rfSQJVDa396f0n6/edit

### Uso

Para el uso del proyecto como usuario, creamos un aplicación de escritorio con Visual Studio. Una vez instalada, al acceder a la aplicación, se debe ingresar lo siguiente: usuario y contraseña. Una vez dentro de ella, los empleados de Voxmapp podrán acceder a las respuestas de las encuestas, y los trabajadores de los hospitales podrán completar la encuesta.

## Estatus del Proyecto

El proyecto actualmente está terminado; sin embargo, siempre estamos arreglando errores y buscando posibles mejoras. En caso de tener cualquier duda o comentario sobre el proyecto no duden en contactarnos. @ZihiFredo @Borghin

## Mejoras en el futuro

La principal mejora para el proyecto es la posibilidad de crear gráficas y vistas que contienen información que es pertinente para el cliente de manera más eficiente. Queremos mostrarlas de la mejor manera posible, por lo que estamos buscando poder conectar la base de datos con Tableau porque nos permite mostrar las gráficas y las vistas fácilmente, sin tener que acceder directamente a la base de datos. 


### Link de la encuesta

Dejamos el link de la encuesta para cualquier posible situación o necesidad que se presente

https://docs.google.com/forms/d/1NnXM4PWHAKxzAtIaQ5KYfcVVXQNEB6snOr99RaMZijE/edit
