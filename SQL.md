# Para iniciar el servicio de postgres es:

sudo  service postgresql start

## Para poder inicializar al ambiente de postgres se procede con:

psql postgres -U postgres
 
### En mac  no crea algunas veces  el user postgres

Escribiendo:  createuser postgres ahora si te debe dejar iniciar
cereatedb hace lo mismo pero con una base de datos 

# SQL
01 Base de datos demo
Carga de base de datos muestra

02 SQL Queries
Construcción básica de consultas a la base de datos

03 Relaciones entre datos
Teoría acerca de las relaciones entre distintas tablas

04 Bases de datos relacionales

## Crear usuario para facilitar acceso

<!-- Crear usuario de PostgreSQL -->
postgres=$ CREATE ROLE name WITH  (la palabra clave aquí es WITH)
SUPERUSER  (Es para darle permisos elevados sobre una BD)
CREATEDB (Permisos para crear DB)
CREATEROLE (Permiso para crear más usuarios)
INHERIT (Permisos para que ese rol pueda ser heredado (crear otro rol como ese mismo))
LOGIN   (Permisos para que se loguee)
REPLICATION   (Permisos para copiar bases de datos (replicar una bd a otro lugar))
BYPASSRLS   (Permisos para un bypass para tablas en bases de datos)

En SQL el ; (punto y coma) no va a finalizar el comando hasta que se le ponga el ;

# SQL Queries

SELECT STATEMENT

Características:
-Es la instrucción más compún 
-Nos permite consultar datos de las tablas
-Puede ser muy complejo, devido a la cantidad de cláusulas para hacer una consulta más flexible

## Las clausulas son:

Operador DISTINCT, selecciona filas distintas 
Clausula ORDER BY, permite ordenar las filas
Clausula WHERE,  filtra filas de la consulta
Clausulas LIMIT y FETCH, selecciona un subconjunto de filas de una tabla
Cláusula GROUP BY, agrupa filas 
Clausula HAVING, Filtra grupos
Clausulas INNER JOIN, LEFT JOIN, RIGTH JOIN, FULL OUTER FOIN, CROSS JOIN, JOIN Unen varias tablas
UNION, INTERSECT y EXCEPT, permiten realizar operaciones de conjuntos

## sintaxis

SELECT  lista_de_deleccion (que datos quiero que me traiga  o que columna quiero consultar) FROM nombre_de_la_tabla (especificamos la tabla);
## COLUMN ALIAS

Definición 
Un alias de columna permite asignar un nombre temporal a una columna o expresión en la lista de selección de una instrucción SELECT. El alias de columna existe temporalmente durante la ejecución de la consulta.

sintaxis

SELECT columna AS alias FROM tabla;

SELECT columna alias FROM tabla;

SELECT expresion AS alias FROM tabla;

Se pueden concatenar ls datos con un ' ' y el alias lo puedo nombrar con espacios si lo deseo con comillas dobles
select  CONCAT(first_name, ' ' , last_name) as full_name FROM customer;
por ejemplo
select  CONCAT(first_name, ' ' , last_name) as "Full Name" FROM customer;

Por lo general no se ocupan alias, sino más bien se nombran las consultas como las variables en el código 

Conclusión 
-Es posible asignar un alias a una columna o una expresión con las siguiente sintaxis:
    -Nombre_columna AS nombre_alias
    -Expresión AS nombre_alias
-La palabra reservada AS es opcional 
Para definir alias que contengan espacios, es necesario definirlo entre comillas ("")

## Order By

Explicación 
Cuando se realiza una consulta a una tabla, la declaración SELECT regresa las filas en un orden no especificado. La clausula ORDER BY permite especificar un orden al conjunto de datos devueltos. Este orden puede ser ascendente o descendente basado en una expresión de ordenamiento.

"se va a ocupar después de la clausula FROM
en esta secuencia: 

SELECT customer_id, first_name, last_name, email
FROM customer
ORDER BY first_name DEC, last_name ASC, customer_id;
la jerarquía sería: 

From --> Select --> Order by

Conclusiones 
-Para ordenar las filas de una declaración SELECT se utiliza la cláusula ORDER BY
-Para controlar la forma en la que se ordenan los datos se utilizan las opciones ASC y DESC 
-Si el conjunto de datos contiene datos nulos o vacíos podemos utilizar las opciones NULLS FIRS y NULLS LAST para especificar explícitamente el orden junto con valores no-nulos 


## Select Distinct (Es exclusiva de postgreSQL)

Sirve para identificar lasfilas duplicadas, se coloca después del select y si se acompaña con más de una coolumna entonces va a intentar evaluar a las 2 para que esto no suceda se le coloca un "()" para colocar la columna que queremos evaluar con distinct (como si fuera su argumento).
 
Select
    distinct ON (columnax) columnax, columnay 
from 
    tabla
order by
    columnax,columay;

## Where
devuelve todas las filas de una o más columnas en una tabla. Para seleccionar las filas que complan una condición específica, se utiliza la cláusula WHERE

Sintaxis:

SELEC lista_de_seleccion
FROM tabla
Where condicion AND | OR
ORDER BY expresion_de_ordenamiento

Practicamente el where es una condicional.

dicho esto : 
primero se evalúa el FROM --> Where -> Select --> Order By

OPERADORES en WHERE

= (igual a)
> Mayor que
< Menor que
>= Mayor o igual que 
<= Menor o igual que 
<>,!= Diferente de (son 2 simobolos que sirven para lo mismo)

AND --Where usando or | and
SELECT first_name, customer_id, last_name
FROM customer
WHERE first_name = 'Willie' or last_name = 'Jhones'
ORDER BY first_name desc;
OR

IN                      Regresa verdadero si un valor coincide con cualquier valor de una lista
BETWEEN                 Regresa verdadero si un valor se encuentra entre un rango de valores
LIKE                    Regresa verdadero si un valor coinide con un patrón
IS NULL                 Regresa verdadero si un valor es nulo o vacío 
NOT                     Niega el resultado de otros operadores

LIMIT me permite limitar una cantidad de resultados
Limit sería el ultimo en evaluarse

FROM => Where => Select => Order By => Limit