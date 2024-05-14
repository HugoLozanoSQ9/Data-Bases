# Insert 

Sirve para crear datos (insertar datos dentro de una tabla)

Sintaxis.

INSERT INTO customer (store_id, first_name, last_name, email, activebool, active,address_id)
VALUES( 1,'Pedro','Perez','pedro.perez@example.com',true,1,1)
RETURNING customer_id;

Cuando se escribe la sentencia returning me va a regresar los datos creados a esa nueva insersión.
De hecho esto es de utilidad para saber que ID se le dio a un usuario al darse de alta etc...
se puede hacer con el * para corroborar que todos los datos son correctos.

Values puede recibir una lista de parentesis, donde cada uno de los parentesis sería una nueva fila agregada a la tabla

# Update

Sirve para actualizar datos

UPDATE customer 

SET first_name = 'Javier',
    last_name = 'Ramos'
WHERE customer_id = 600
RETURNING *;

# Delete

Sirve para eliminar datos

  
Datos automáticos son los last_update, create_date y los que traen id

# Proceso para crear un usuario nuevo 

--insert into city(city,country_id)
--values ('Ciudad de México',60)
--returning *; //Tiene el id 604

--update city 
--set city = 'Estado de México'
--where city_id = 603
--returning*
--select * from city order by city_id desc;

--insert into address(address,address2,district,city_id,postal_code,phone)
--Values ('some direction','alguna otra dirección','Some district',604,05343,54893589347)
--returning *;

--select address_id, city.city_id, city, city.country_id, country
--from address
--inner join city
--on address.city_id = city.city_id
--inner join country 
--on city.country_id = country.country_id
--where address_id = 606;
--select * from address where address_id = 606;
--insert into customer(store_id, first_name, last_name, email, address_id, activebool,active)
--Values(1,'Hugo','Lozano','someemail.com',606,true,1)
--returning*;
