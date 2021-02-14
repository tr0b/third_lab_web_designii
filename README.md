### Third Lab - Web Design

This will be the repository for all third lab-related code [Web Design II]

### Tercer laboratorio - Diseno Web

Este va a ser el repositorio para todo el codigo relacionado con el tercer laboratorio [Diseno Web II]

### HOW TO RESTORE BACKUP (COMO RESTAURAR RESPALDO)

The backup is a mongo binary file. It can be restored using `mongorestore`:

~

El respaldo es un archivo binario mongo. Puede ser restaurado usando `mongorestore`:

### Accessing the database `my_theater_studio` (Accediendo a la base de datos `my_theater_studio`)

` use my_theater_studio`

### Ten Queries (Las diez consultas)

#### Finding all movies (Encontrando todas las peliculas)

`db.movies.find()`

#### Finding all theaters (Encontrando todos los teatros)

`db.theaters.find()`

#### Finding all schedules (Encontrando todos los horarios)

`db.schedules.find()`

#### Finding all prices (Encontrando todos los precios)

`db.prices.find()`

#### Finding movies by `genre` (Encontrando peliculas por genero)

`db.movies.find({genre: "fantasy"})`

#### Finding movies by `movie_id` (Encontrando peliculas por su `movie_id`)

`db.movies.find({movie_id: 1})`

#### Finding theater(s) by `name` (Encontrando teatros por su nombre)

`db.theaters.find({name: "My First Theater"})`

#### Finding schedules by `description` (Encontrando horarios por su description)

`db.schedules.find({description: "My First Theater"})`

#### Finding all movies in a theater (Encontrando todas las peliculas en un teatro)

`db.theaters.aggregate({ $lookup:{ from:"movies", localField:"movies", foreignField:"movie_id", as:"movies_available" } }).pretty()`

#### Finding schedule and price of all movies (Encontrando horario y precio de todas las peliculas en cartelera)

`db.movies.aggregate({$lookup:{ from: "schedules", localField: "schedule_id", foreignField: "schedule_id", as: "movie_schedule"}}, {$lookup:{from:"prices",localField:"price_id",foreignField:"price_id", as:"movie_price"}}).pretty()`
