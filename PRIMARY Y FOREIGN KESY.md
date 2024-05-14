primary key:Me permite identificar los registros de la misma tabla (cada uno de los registros de la misma tabla)
Identificador unico de registro 

foreign key: La llave foranea va a jalar las propiedades de otras llaves primarias
Identificador de registro en una tabla

Por ejemplo de la tabla costumer yo tengo las siguientes propiedades: 

costumer =>{
    costumer_id
    first_name 
    last_name 
    store_id
    address_id
}

llave primaria: costumer_id 

llave fornaea: store_id y address_id


tipos: 
one - one   1   1
one - many  1   1+
many - many 1+  1+