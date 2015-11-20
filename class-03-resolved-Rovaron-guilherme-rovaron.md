# MongoDB - Aula 03 - Exercício
autor: Guilherme Rovaron

## 1 - Listando pokemons com altura menor que 0.5
```
> var query = {height: {$lt: 0.5}}
> db.pokemons.find(query) // Não retornou nada pq meus custom-pokes são todos gigantes naipe godzilla
```

## 2 - Listando pokemons com altura maior ou igual a 0.5
```
> var query = {height: {$gte: 0.5}}
> db.pokemons.find(query)
{ "_id" : ObjectId("5643ca4fe728f5449c816791"), "nome" : "Shiny Scyther", "description" : "Pokemon mais loco da galáxia", "attack" : 333, "defense" : 100, "height" : 30 }
{ "_id" : ObjectId("5643cb34e728f5449c816792"), "nome" : "AecioSnows", "description" : "Tipo voador, nariz com coloração branca", "attack" : 2, "defense" : 8001, "height" : 80 }
{ "_id" : ObjectId("5643cbafe728f5449c816793"), "nome" : "Dilmee", "description" : "Parente do slowking, so fica boiando e repetindo coisas sem sentido", "attack" : 0.13, "defense" : 0, "height" : 88 }
{ "_id" : ObjectId("5643cc2fe728f5449c816794"), "nome" : "Scizor", "description" : "Evolução do scyther nem sei qual é mais bolado", "attack" : 999, "defense" : 999, "height" : 33.33 }
{ "_id" : ObjectId("5643cc9ee728f5449c816795"), "nome" : "Hitmonlee", "description" : "Homenagem ao mestre bruce lee, da vuadora até na sombra", "attack" : 9999999, "defense" : 999999, "height" : 60.33 }
```

## 3 - Listando pokemons com altura menor ou igual a 0.5 e do tipo grama
```
> var query = {$and: [{height: {$lte: 0.5}},{type: "grass"}]}
> db.pokemons.find(query)
```

## 4 - Listando pokemon com o nome 'Pikachu' ou com ataque menor ou igual a 0.5
```
> var query = {$or: [{name: "Pikachu"},{attack: {$lte: 0.5}}]}
> db.pokemons.find(query)
{ "_id" : ObjectId("5643cbafe728f5449c816793"), "nome" : "Dilmee", "description" : "Parente do slowking, so fica boiando e repetindo coisas sem sentido", "attack" : 0.13, "defense" : 0, "height" : 88 }
```

## 5 - Listando pokemons com attack maior ou igual a 48 e com height menor ou igual a 0.5
```
> var query = {$and: [{attack: {$gte: 48}},{height:{$lte: 0.5}}]}
> db.pokemons.find(query) // novamente nao retorna nada devido a pokemons megazord.
```
