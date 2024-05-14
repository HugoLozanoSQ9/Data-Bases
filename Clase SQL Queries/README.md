# Select
Es la más usada en base de datos es la más compleja por la cantidad de clausulas que tiene 
## Alias
Se puede mainuplar una tabla con cierto alias que deseemos
## Order By 
Sirve para odrdenar los datos con cierto orden 
## Where 
Sirve para filtrar ñps datos
LOS ALIAS NO SE VAN A PODER OCUPAR EN EL WHERE
Se puede ocupar el comodín seguido de like => first_name like 'Ja%' 
Esto sirve para indicar que vamos a buscar todo lo que empiece con Ja y lo demás lo buscará en la base de datos
like es muy pesada y es mejor usar el = 
El operador in se puede ocupar como en python (por ejemlo en el for)

Where first_name IN ('algo','otra_cosa','otra_cosa_mas')
In es más optimo que poner varios OR cuando se necesita que en una condicional se tengan varias condiciones

select first_name, last_name
FROM customer 
where first_name IN ('Ann','Anne','Annie') AND last_name IN ('Evans','Powell');

Una relacion es algo que tienen en comun diferentes tablas :D!

# Relaciones entre datos

Conexiones de datos entre tablas
Existen 3 tipos de relaciones entre datos 
    -Uno a uno (one-to-one)
    -Uno a muchos (one to many)
    -Muchos a muchos (mayo-to-many)

Los identificadores son las llaves primarias  (primary key)
Puede ser una propiedad o un conjunto de propiedades  de una entidad
Esto es un identificador o es algo que me permite identificar un registro de manera unica

many-to-many (es cuando podemos tener varios registros entre varias tablas )
one-to-one (es cuando podemos tener un solo registro entre A y B)
one-to-many (es cuando podemos tener un solo registro en varias tablas (ocease un  solo elemento en varias tablas)) (A puede tener varios registros de B)


En las many-to-many siempre se va a ocupar una tabla intermediaría la cual va a tener ambos conjuntos de datos
por ejemplo en este caso de las películas:

peliculas --> flim_actor --> actor 
peliculas va a tener como llave primaria film_id
actor va a tener como llave primaria actor_id

flim_actor va a tener como llaves foraneas  actor_id y film_id (se pueden agregar más datos pero son datos extras como por ejemplo last_update)


select actor_id,film_id
from film_actor --Se hace la busqueda en la tabla intermediaria
where film_id = 1 --Estamos indicando que queremos filtrar por el actor 1
limit 10;




