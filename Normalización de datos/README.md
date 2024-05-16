# Normalización
¿Qué es? 
Proceso de simplificación de datos
    Tener amacenado con el menor espacio posible
    Eliminar datos repetidos
    Eliminar errores lógicos
    Datos ordenados


Formas normales 
-Primera forma normal (1FN)
-Segunda forma normal (2FN)
-Tercera forma normal (3FN)
-Forma normal de Boyce_Codd
-Cuarta Forma Normal (4FN)
-Quinta Forma Normal (5FN)

## 1FN

Reglas:

-Una única celda de la tabla no debe de contener más de un solo valor (atomicidad)
-Cada registro debe contener un identificador único(llave primaria)
-No debe existir filas o columnas duplicadas
-Cada columna debe contener un solo valor por cada fila en la tabla

El resultado es una tabla sin grupos de datos repetidos

Por ejemplo:
Tenemos 2 o más tablas tablas para cada valor y no solo 1 que contenga el nombre completo (cumple con la atomicidad)
first_name | last_name | middle_name|

## 2FN

Reglas: 

-Debe cumplir la primera forma normal 
-No deben existir dependencias parciales
    -Cada celda de la fila debe ser completamente dependiente a su llave primaria o identificador único
Forma correcta:
id|nombre|edad|id_direccion 
Forma incorrecta:
id|nombre|edad|calle 

(calle) es un valor unico pero calle bien podría ser valor de otra tabla llamada direccion por ende es mejor que se coloque en la tabla dirección 
y de esta forma evitamos dependencias parciales.

resultado: una tabla sin redundancia

## 3FN

Reglas: 

-La tabla debe estar en su segunda forma normal
-No deben de existir dependencias transitivas

    Una dependencia transtivia es cuando se tiene una columna que funcionalmente depende de otra columna, pero no es una columna primaria

Ejemplo:
Tenemos la tabla empleados 
id| address_id | cp |

como podemos ver la columna id del empleado sería la llave primaria, mientras que la columna address_id es una llave foranea
pero cp depende totalmente de addres_id por lo que es una dependecia transitiva (cuando alguna columna no depende de la llave primaria si no mas bien de una llave foranea)