# tipos de datos

Booleano
Caracteres 
    Char
    Varchar
    Text
Numéricos
    Integer
    Floating-point
Temporales
    Date
    Time
    Timestamp
    Interval

# Tipos específicos

UUID
    Identificadores Universalmente Unicos
Array
    Para almacenar arreglos de strings, números, etc...
JSON
    Almacena datos JSON
hstore
    Almacena pares de datos llave -valor
Tipos especiales
    Direcciones de red
    Datos geométricos    
    Datos geoespaciales

# Tipos de datos generales

## Boolean

Un dato que puede almacenar 3 valores:

True
False
Null

Cuando se insertan datos en una columna booleana, PostreSQL lo transforma a un valor booleano

1,yes,y,t,true --> true
0,no,false,f --> false

## Character

PostreSQL ofrece tres tipos de datos de caracter
    char(n) 
        Es la cadena de caracteres de longitud fija con espacios de relleno 
        Si se inserta una cadena de caracteres con longitud menor que el de la columna, PostgreSQL lo rellena con espacios
        Si se inserta una cadena de caracteres con una longitud mayor que el de la columna, postgreSQL devuelve un error

    varchar (n)
    Es la cadena de caracteres de longitud variable
    Con varchar(n) se puede almacenar hasta n caracteres. PostgreSQL no rellenará con espacios cuando la cadena cuente con la longitud menor que la longitud de la columna

    Text 
    Es la cadena de caracteres de longitud variable
    Teóricamente, los datos de este tipo es una cadena con longitud ilimitada

# Tipos de datos numericos

Tenemos 2 tipos distintos de números

Integer
    Entero pequeño SMALLINT es un entero de 2 bytes 
    Entero INT es un entero de 4 bytes 
    Gran entero BIGINT es un entero de 8 bytes 
    Serial es un entero excepto que PostgreSQL lo genera automáticamente y completará los valores en la columna SERIAL, Existen variantes SMALLSERIAL y BIGSERIAL

Floating-point:
    Float(n) es un número de punto flotante, el cual tiene una precision, de al menos n hasta un número máximo de 8 bytes
    REAL es un número foltante de 4 bytes, 6 dígitos de precisión decimal
    NUMERIC o NUMERTIC(p,s) es un número real con p digitos y s números después del punto decimal. El número 23.5141 tiene una precisión p de 6 y una   escala s de 4
    Ejemplo: 
            NUMERIC(6,4)
            6 números en total máximos de los cuales 4 serán decimales
            23.3564 en esta situación tenemos un límite: 99.9999

# Tatos Temporales

Los datos temporales de PostrgreSQL permiten almacenar fechas y/o horas. os datos principales de este tipo son: 
    DATE: Almacena fechas solamente
    TIME: Almacena valores que representan la hora del día
    TIMESTAMP: Almacena ambos valores, fecha y hora
    TIMESTAMPTZ:Es un tipo de dato de marca de tiempo (timestamp) que reonoce la zona horaria
        Es la abreviatura para timestamp con la zona horaria
        Es la extensión de PostgreSQL al estándar SQL para los tipos de datos temporales
    INTERVAL: Almacena preiodos de tiempo

# Tipos de datos especiales

Arrays 
Se puede almacenar un array de cadenas de texto, un array de enteros, etc. en columnas de tipo array. El aray es útil en algunas situaciones, como puede ser el guardar dias de la semana, meses del año etc...

JSON 
Ofrece 2 tipos de datos JSON 
    El tipo de dato JSON almacena información simple en formato JSON que requiere se analizado (o parseado) para cada procedimiento
    El tipo de dato JSONB almacena información en formato JSON en un formato binario que es más rápido de procesar pero más lento de insertar .JSONB admite indexación

UUID
El tipo de datos UUID permite almacenar identificadores únicos universales defindos por el estandart RFC 4122. Los valores UUID garantizan una mejor singularidad que SERIAL y se pueden utilizar para ocultar datos sensibles expuestos al público como valores de id en 

# Tipos de datos especiales ++

box: una caja rectangular
line: un conjunto de puntos
point: un punto geométrico  
lseg: un segmento de línea 
poligon: una forma geométrica cerrada
inet: una dirección 1Pv4
macaddr: una dirección MAC


