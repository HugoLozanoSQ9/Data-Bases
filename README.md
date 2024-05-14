# Bases de datos

Nociones básicas de bases de datos 

SQL

01.- Bases de datos y SQL 
-¿Qué es?
-¿Que puede hacer?
-DBMS

02.- ¿Qué es PostgreSQL?
-¿Qué es?
-Particularidades

03.-Instalación de PostrgreSQL
-Instalación de PostgreSQL en Linux, MacOS y de ser necesario en Windows

04 Beekeeper Studio (GUI)
-Instalación de un GUI para bases de datos

## Bases de datos y SQL 

Es un Conjunto de información que tienen relación entre si 

Agenda de contactos 
Lista de compras
Lista de To Do's
5 mejores amigos
Usuarios de FB etc...

Formas de almacenamiento:
En papel 
En la mente
En una computadora
En una presentación 
En una sección de comentarios

Vamos a enfocarnos para utilizar la computadora como una base de datos.

Por ejemplo Amazon.com

-Mantiene el seguimiento de Productos, Reseñas, Ordenes de compra, Tarjetas de crédito, Usuarios, Medios, etc...
-Se requiere almacenar y mantener disponible millones de piezas de información 
-La información es extremadamente valiosa y crítica para el funcionamiento de Amazon.com
-La seguridad es esencial ya que Amazon resguarda información personal
-La información se almacena en una computadora 

A diferencia de una lista de compras:

-Mantiene el seguimiento de productos que se prequieren de comprar
-Se requiere almacenar y mantener fácilmente disponible 10-20 piezas de información 
-La información es sólo por conveniencia y no es necesaria para realizar la compra
-La seguridad no es importante
-La información se puede almacenar en un papel o incluso en la memoria.

Todo esto hace referenca a un DBMS
(Software que ayuda a los usuarios crear y mantener una base de datos)
-El DBMS nos va a permitir tener Gran cantidad de datos
-Seguridad
-Respaldos / clonación 
-Importar / exportar
-Permite interactucar con lenguajes de software

#Principales Operaciones

Create --> Read o Retreve --> Update --> Delete

#Tipos de BD

Relacionales(SQL)
-Organiza los datos en una o más tablas
--Cada tabla tiene columnas y filas
--Una clave única identifica cada fila
--Se tienen que definir las tablas

No Relacionales (noSQL)
-La manera de organizar datos es cualquier otra que no sea una tabla tradicional
--Registros de tipo llave-valor
--Documentos(JSON,XML,etc)
--Grafos
--Tablas flexibles

Ejemplos: SQL 
-Postgresql
-Ms  SQL Server
-My SQL
-Maria DB

Ejemplos: noSQL 
-RethinkDB
-Casandra
-Mongodb
-Dynamodb
-Graphql

## DB relacionales
Tabla de coders
ID     Nombre     Bootcamp
1       Diego       Python1G
2       Maria       JS9G
3       Alfonso     Python2G
4       Noelia      JS2G
se puede adicionar más elementos agregando justamente otra tabla como por ejemplo "Fecha"
Pero es muy importante también tomar en cuenta que el ID deberá ser unico por c/u de los registros (el unico irrepetible es el ID)

Pero por decir ahora si tenemos otra tabla con cierta clave unica que tampoco se debe repetir como por ejemplo el User name  ( de le indica que es de clave unica)
Tabla de usuarios
Username     Passwprd     Email
pakito       1234      pakito1@void
arm          678683    pakito1@void
chapuli      fudh8y    pakito1@void
colorao     h785uirjf  pakito1@void

# sistemas de Administración de BD Relacionales(RDBMS)

-Ayuda a los usuarios a crear y mantener una base de datos relacional
-MySQL, Oracle, PostgreSQL, MariaDB, etc...

Structured Query Lenguage (SQL)
-Lenguaje estandarizado para interactuar con RDBMS
-Utilizado para realizar operaciones CRUD, así como otras tareas administrativas (gestiión de usuarios, seguridad, respaldos, etc...)
-Utilizado para definir tablas y estructuras
-El código SQL utilizado en una RDBMS no siempre es portable a otro sistema sin modificación

Cabe destacar que las consultas deben ser creadas en el lenguaje para que lo que reciba también pueda ser interpretado por el lenguaje

Queries = Consultas
Queries son solicitudes de infromatción específica realizados al sistema de administración de bases de datos
-A medida que la estructura de la base de datos se vuelve cada vez más compolejta, se vuelve más dificil obtener la información específica que queremos.
-Una busqueda un google es un ejemplo de una query

# Conclusiones

-Las bases de datos son cualquier colección o conjunto de información relacionada
-Las computadoras son excelentes para almacenar bases de datos
-Los sistemas de Administración de Bases de Datos (DBMS) facilitan el crear, mantener y asegurar una base de datos
-Existen 2 tipos de bases de datos, Relacionales y No Relacionales.
-Las bases de datos  relacionales utilizan SQL y guardan los datos en tablas con filas y columnas

## ¿Que es PostgreSQL?
-RDBS avanzado
-Clase empresarial
-Código abierto

Características principales:
-Soporta consultas SQL y JSON
-Utilizado como RDBS principal de aplicaciones web, moviles y de analíticas.

-Se puede llegar a considerar una base de datos hibrida pq nos deja almacenar en JSON.

## Casos de uso
1.-Base de datos robusta para un LAPP stack (Linux, Apache o Nginx, Python / PHP. Postgres)
2.-Base de datos para transacciones de propósitos generales
3.-Base de datos geoespacial

# Características destacadas
-Tipos de definidos por el usuario  (se pueden crear nuestros propios tipos de datos)
-Herencia de tablas
-Sofisticado mecanismo de bloqueo
-Integridad referencial de llaves foráneas
-Vistas, reglas, subquery
-Transacciones anidadas
-Control de concurrencia (multi-versión)
-Replicación asíncrona
-Al ser open-source se pueden desarrollar plug-ins específicos

## ¿Dónde se utiliza PostgreSQL?
-Apple
-Fujitsu
-Red Hat
-Cisco
-Juniper Network
-Instagram

Para verificar la instalación del cluster se debe ingresar a /var/lib/postgresql ls -a y aca está todo el entorno de trabajo (todo lo que inicia con Pg son scritps que maneja postgres)


