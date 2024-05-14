# Manejo de tablas

Create Tabe statement

Conceptos 
    Una base de datos consiste en múltiples tablas relacionadas
    Una tabla consiste en filas y columnas
    Las tablas permiten almacenar datos estructurados como clientes, productos, empleados etc...
    Todas las entidades debén estár definidas en una tabla específica (esto debe estar pre-definida)

Sintaxis:
    Para crear una nueva tabla, se utiliza la declaración 
    CREATE TABLE seguido del nombre de la tabla --> indicar cada una de las columnas que va a tener esta tabla y su tipo de dato: 

    CREATE TABLE products(
        id INT restricción,
        name varchar(50) restricción 
    );
    
 CREATE TABLE products(
        id INT restricción(si es que la hay),
        name varchar(50) restricción (si es que la hay)
        restricción de la tabla si es que la hay 
    );

Si al crear la tabla se ingresa la condición IF NOT EXISTS solamente creará la tabla si es que la tabla no existe, en caso de que ya exista nos va a decir que la tabla ya existe pero no la va a crear.

las reestriciones de columnas puede ser por ejemplo: NOT NULL 
(ante esto la misma bd no va a permitir que tenga algún valor vacío en ningún momento)

Unique nos v aa obligar a que cada registro dentro de la tabla sea unico (es decir que no se repita o que no halla duplicados)
Se uele usar con el ID. 

PRIMARY KEY sirve como reestricción indicando de que esta columna va a ser mi llave primaria (el id será mi llave primaria)

CREATE TABLE IF NOT EXISTS products(
    id INT NOT NULL UNIQUE PRIMARY KEY, --> constraints (reestricciones)
    short_description VARCHAR (255) NOT NULL, 
    long_descriprion TEXT 
);

SELECT id, short_description, long_description
FROM products


Para borrar tablas se puede hacer con la sentencia:
DROP TABLE --> nombre de la tabla

DROP TABLE products

## Ejemplo:


CREATE TABLE IF NOT EXISTS products(
    sku VARCHAR(10) NOT NULL UNIQUE PRIMARY KEY, 
    short_description VARCHAR (255) NOT NULL, 
    long_descriprion TEXT,
    brand VARCHAR(20) NOT NULL 
);

Si se desea guardar estos 2 productos

prod-01:nike
prod-01:adidas 

No nos lo permite por que el sku trae la propiedad unique en el sku en el caso de que yo requiera si o si realizar ese guardado de información, entonces:
tendría que eliminar el unique y de paso el primary key para que el sku y la marcasean mi llave primaria

CREATE TABLE IF NOT EXISTS products(
    sku VARCHAR(10) NOT NULL, 
    short_description VARCHAR (255) NOT NULL, 
    long_descriprion TEXT,
    brand VARCHAR(20) NOT NULL ,

    PRIMARY KEY (sku, brand) // Esta es una restricción a nivel tabla NO a nivel columna :D!
);

## Relaciones y características de tablas

Estamos creando la tabla products pero queremos que la marca sea una tabla diferente 

primero corroboramos que exista la tabla brands (si no existe la crea)

hecho esto creamos la tabla que va a llevar esa llave foranea --> products

y en las restricciones de tablas se proceden a realizar estas sentencias :

    CONSTRAINT  fk_brand
        FOREIGN KEY(brand_id)
            REFERENCES brands(id)
-------------------------------------------

CREATE TABLE IF NOT EXISTS brands(
    id SERIAL PRIMARY KEY,
    name VARCHAR(20)
)
 

CREATE TABLE IF NOT EXISTS products(
    id SERIAL(10), PRIMARY KEY,
    short_description VARCHAR (255) NOT NULL, 
    long_descriprion TEXT,
    brand_id INT, 

    CONSTRAINT  fk_brand
        FOREIGN KEY(brand_id)
            REFERENCES brands(id)
    
);


## Conjuntos

Tenemos un conjunto A y un conjunto B 
 
 A |          B X
___________________________
| A    A X  AB   |B     B X
|  A  A  X    AB |  B   B X
|_A__A___X_ A _B |__B__B__X
 
Si queremos seleccionar TODO lo de A (qque incluye A y B) entonces se hace un 
Left Join 
si queremos A solita entonces --> Left outer Join

si queremos TODO lo de B (incluyendo A y B ) entonces se hace un 
Right Join pero 
Pero si queremos B solita entonces --> Right outer Join

Cuando queremos todos los datos tanto de A como de B  se ocupa 
Full Join
En cambio si queremos los datos de ambas tablas pero sin que coincidan (ocease A y B pero NO AB)
Entonces se ocupa Full Outer Join

SELECT a, friut_a, b, friut_b --> acá estamos diciendo que queremos estas 4 columnas
FROM basket_a --> estas 4 columnas las voy a sacar de la canasta "a"
    Full Join basket_b --> Juntando los datos de "a" con la canasta "b" 
        ON fuit_a = fruit_b --> vamos a identificar los registros de esas 2 columnas que contengan registros iguales (por eso está que a = b)

(esto nos muestra lo de las 2 columnas, tanto A como B y en principio nos muestran las que coinciden)

En cambio si solo queremos saber las que coniciden y los datos que no coinciden pues no queremos traerlos se hace con:

INNER en lugar de FULL

Ahora que si queremos solo los datos del conjunto A y a su vez los datos que son coincidentes, entonces: 
sería LEFT JOIN (Me trae todo lo de A pero como tenemos que fruit a = fruit b entonces mostrará todo A y las coincidencias de B)

ahora que si necesitamos los datos donde B es null (ocease los datos que no empatan con B )
se mantiene el LEFT JOIN pero se agrega la sentencia
WHERE b IS NULL (ocease los datos de A que no empatan con b)





 