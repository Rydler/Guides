# UTILIDADES

* **`db`** - Muestra la base de datos a la que me encuentro conectado
* **`show dbs`** - Muestra las bases de datos existentes
* **`use "Nombre_Base_Datos"`** - Cambia a una base de datos existente, si esta no existe la crea temporalmente


# CREATE

* **`db.createUser({user: 'user', pwd:'pwd', roles ['readWrite', 'dbAdmin']})`** - Crea un usuario en la base de datos
* **`db.coleccion.insert(<document>)`** - Inserta un documento en la coleccion
* **`db.coleccion.insert([<document>,<document1>,....])`** - Inserta uno o varios documentos tipo array a una coleccion
* **`db.coleccion.insertOne(<document>)`** - Inserta un documento en la coleccion, si la coleccion no existe la crea
* **`db.coleccion.insertMany([<document>,<document1>,...], {writeConcern: <document>,ordered: <boolean>})`** - Inserta Varios Documentos dentro de una coleccion, el argumento ordered permite definir si el insert se detiene en caso de error (true) o sigue en caso de errores (false)


# READ

* **`db.coleccion.find()`** - Consulta por todos los registros de una coleccion
* **`db.coleccion.find().count()`** - consulta y devuelve el numero total de registros de una coleccion
* **`db.coleccion.find().pretty()`** - Consulta y ordena de mejor manera todos los registros de una coleccion
* **`db.coleccion.find().sort({campo: 1})`** - Consulta y ordena de mayor a menor dado un campo
* **`db.coleccion.find().sort({campo: -1})`** - Consulta y ordena de menor a mayor dado un campo
* **`db.coleccion.findOne()`** - Consulta y devuelve un documento
* **`db.coleccion.find().limit(numero)`** - Consulta por y devuelve la cantidad de registros de una coleccion dado en el limit
* **`db.coleccion.find({campo: 'valor'})`** Consulta por el valor de un campo definido en la coleccion
* **`db.coleccion.find({"campo.subcampo": "valor"})`** Consulta por el valor de un campo de tipo objeto en la coleccion
* **`db.coleccion.find({'campo.N': "valor"})`** Consulta por el valor de un campo de tipo objeto en una posicion relativa, donde N es la posicion relativa del arreglo
* **`db.coleccion.find({campo: objetId("_id")})`** Consulta por el valor del campo _id el cual es un objetId
* **`db.coleccion.find({$or: [{campo: "valor"}, {campo: "valor"},...])`** Consulta por el valor de uno o varios campos usando el operador logico or
* **`db.coleccion.find({campo: {$in: "valor1","valor2",...}})`** Consulta por los valores de un campo dado, si alguno conincide con el criterio devuelve el o los resultados
* **`db.coleccion.find({campo: {$gt: valor_numerico}})`** Consulta por un campo que devuelte todos los registros que sean mayor al valor dado
* **`db.coleccion.find({campo: {$lt: valor_numerico}})`** Consulta por un campo que devuelte todos los registros que sean menor al valor dado
* **`db.coleccion.find({campo: {$regex: 'expresion_regular'}})`** Consulta por un campo que devuelve un registro dado su expresion regular


# UPDATE

* **`db.collection.updateOne(<filtro>, <update>{<document>})`** Consulta mediante un filtro y luego ejecuta la actualizacion de los campos inidicados en un solo documento
* **`db.coleccion.update({campo_busqueda: 'valor_busqueda'}, {campo: valor},....)`** Consulta por un campo y actualiza los restantes
* **`db.coleccion.update({campo_busqueda: 'valor_busqueda'}, {campo: valor},..., {upsert: true})`** Consulta por un campo y actualiza los restantes, si el registro no existe lo crea
* **`db.coleccion.update({campo_busqueda: 'valor_busqueda'}, { $set: {campo: valor},...})`** Consulta por un campo y agrega un nuevo campo y valor
* **`db.coleccion.update({campo_busqueda: 'valor_busqueda'}, { $unset: {campo: 1},...})`** Consulta por un campo y elimina un campo segun su nombre
* **`db.coleccion.update({campo_busqueda: 'valor_busqueda'}, { $inc: {campo: valor},...})`** Consulta por un campo e incrementa otro campo especificado segun el valor
* **`db.coleccion.update({campo_busqueda: 'valor_busqueda'}, { $rename: {"campo": "campo_renombrado"}},....)`** Consulta por un campo y renombra un campo dado por otro campo pasado como segundo parametro

# DELETE

* **`db.coleccion.remove({campo_busqueda: 'valor_busqueda'})`** Consulta por un campo y remueve el o los registros de la coleccion que coincida con la busqueda
* **`db.coleccion.remove({campo_busqueda: 'valor_busqueda'}, {justOne: true})`** Consulta por un campo y remueve solo un registro de la coleccion que coincida con la busqueda

# OPERADORES

* **`$all --> { <field>: { $all: [ <value1> , <value2> ... ] } }`** busca documentos que contengan todos los value especificados para un field
* **`$and --> { $and: [ { <expression1> }, { <expression2> } , ... , { <expressionN> } ] }`** utiliza el operador logico and
* **`$exist --> { field: { $exists: <boolean> } }`** Valida si el campo field existe utilizando un boolean
* **`$gt --> {field: {$gt: value} }`** greater than o mayor que
* **`$gte --> {field: {$gte: value} }`** greater than equal o mayor o igual que
* **`$in --> { field: { $in: [<value1>, <value2>, ... <valueN> ] } }`** Compara varios valores dentro de una matriz
* **`$lt --> {field: {$lt: value} }`** less than o menor que
* **`$lte --> {field: {$lte: value} }`** less than equal o menor o igual que
* **`$elemMatch --> { <field>: { $elemMatch: { <query1>, <query2>, ... } } }`** busca coincidencias con documentos que tienen campos de tipo array donde al menosun elemento coincide con los criterios de las querys
* **`$ne --> {field: {$ne: value} }`** not equal o no igual
* **`$lte --> {field: {$lte: value} }`** less than equal o menor o igual queele
* **`$or --> { $or: [ { <expression1> }, { <expression2> }, ... , { <expressionN> } ] }`** utiliza el operadorlogico or
* **`$size --> { $size: <expression> }`** cuenta y retorna el total de elementos de un arreglo
* **`$type --> { field: { $type: <BSON type> } }`** Valida que el field sea de un tipo de dato determinado BSON type
* **`$type --> { field: { $type: [ <BSON type1> , <BSON type2>, ... ] } }`** valida que el field sea de uno o varios tipos de datos determinadosen el array de BSON type


# Aggregation Framework Pippeline

* **`db.coleccion.aggregate([{ $match: {....} }])`** Funciona como el equivalente a un where en una consula SQL
* **`db.coleccion.aggregate([{ $project: {...} }])`** Funciona como el equivalnte a un select en una consulta SQL
* **`db.coleccion.aggregate([{ $addFields: { <newField>: <expression>, ... } }])`** Funciona similar a un $project, permite adicionar campos
