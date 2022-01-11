# MongoDB

## Como crear una Base de datos en una carpeta:
```sh
mongod --db path="directorio"
```
## Como cerrar el servicio en consola de BD:
```sh
^c
```
## Como empezar a trabajar en un cliente
```sh
mongo
```
## Como ver dbs:
```sh
show dbs
```
## Como como crear o posicionarte en una BD:
```sh
use "nombre de la bd"
```
## Como saber en que bd estoy:
```sh
db
```
# Como crear una coleccion:
### simple
```sh
db.createCollection("productos")
```
### creando items con la coleccion
```
db.usuarios.insert({nombre: 'Juan', edad:23})
```
# Como ver los datos de la coleccion:
### Como ver las coleccion:
```sh
show collections
```
### Como ver la cantidad de items en una coleccion:
```sh
db.productos.count()
```

### Como ver la informacion:
```sh
db.productos.find()
```
### Como ver la informacion mas espaciada:
```sh
db.productos.find({}).pretty()
```
### Como ver la informacion con filtro:
```sh
db.usuarios.find({nombre:'Juan'})
```
### Como ver la informacion con filtro y sin key sensitive:
```sh
db.usuarios.find({nombre:/diego/i})
```
### Como ver la informacion con 2 o mas filtro:
```sh
> db.usuarios.find({nombre:'Diego',edad:30})
```
### Como ver la informacion con filtro AND:
```sh
> db.usuarios.find({ $and: [{nombre:'Diego'},{edad:30}]})
```
### Como ver la informacion con filtro OR:
```sh
db.usuarios.find({ $or: [{nombre:'Juan'},{edad:34}]})
```
### Como ver la informacion con filtro OR y dentro de uno de sus datos un AND:
```sh
db.usuarios.find({ $or: [{nombre:'Juan'},{edad:34},{nombre:'Diego',edad:37}]})
```
### Como ver la informacion con filtro MAYOR QUE:
```sh
db.usuarios.find({edad:{$gt:30}})
```
### Como ver la informacion con filtro MAYOR O IGUAL QUE:
```sh
db.usuarios.find({edad:{$gte:30}})
```
### Como ver la informacion con filtro MENOR QUE:
```sh
db.usuarios.find({edad:{$lt:30}})
```
### Como ver la informacion con filtro MENOR O IGUAL QUE:
```sh
db.usuarios.find({edad:{$lte:30}})
```
### Como ver la informacion con filtro DISTINTO QUE:
```sh
db.usuarios.find({edad:{$ne:30}})
```
### Como ver la informacion con filtro IGUAL QUE:
```sh
db.usuarios.find({edad:{$eq:30}})
```
### Como ver la informacion con filtro MAYOR QUE e MENOR QUE:
```sh
db.usuarios.find({edad:{$gte:24,$lte:34}})
```
### Como ver la informacion con filtro EN ORDEN(si se quiere de mas grande a mas chico poner -1)(tambien sirve alfabeticamente):
```sh
 db.usuarios.find({}).sort({edad:1})
```
### Como ver la informacion con filtro PONER LOS ULTIMO N
```sh
db.usuarios.find({}).limit(3)
```
### Como ver la informacion con filtro PONER LOS ULTIMO N Y SALTAR N
```sh
db.usuarios.find({}).skip(1).limit(3)
```
# Agregar datos en una coleccion
### simple:
```sh
db."productos".insert({variable:'celular',precio:12345})
```
### doble o mas:
```sh
db.productos.insert([{nombre:'tv',precio:23456},{nombre:'equipo de musica',precio:76543}])
```
# Como eliminar una coleccion:
```sh
db.productos.drop()
```
