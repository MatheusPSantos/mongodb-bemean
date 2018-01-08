# MongoDB - Aula 03 - Exercício
autor: MatheusPSantos

## Passos do exercício

### 1 - Listar os Pokemons com a altura menor que 0.5
```
matheus-NI-1406(mongod-2.6.10) test> use pokemons
switched to db pokemons
matheus-NI-1406(mongod-2.6.10) pokemons> var query = {height: {$lt: 0.5}}
matheus-NI-1406(mongod-2.6.10) pokemons> db.pokemons.find(query)
{
  "_id": ObjectId("5a4edac3e97e092b69f3dd5d"),
  "name": "Pikachu",
  "description": "Rato elétrico",
  "type": "electric",
  "attack": 55,
  "height": 0.4
}
{
  "_id": ObjectId("5a4edc6cd1c08bdedd106ecc"),
  "name": "Bulbassauro",
  "description": "Chicote de trepadeira",
  "type": "grama",
  "attack": 49,
  "height": 0.4
}
{
  "_id": ObjectId("5a4edee557e555da1bcbedef"),
  "name": "Cartepie",
  "description": "Larva lutadora",
  "type": "inseto",
  "attack": 30,
  "height": 0.3,
  "defense": 35
}
Fetched 3 record(s) in 56ms
```

### 2 - Listar os Pokemons com a altura maior ou igual que 0.5
```
matheus-NI-1406(mongod-2.6.10) pokemons> var query = {height: {$gte: 0.5}}
matheus-NI-1406(mongod-2.6.10) pokemons> db.pokemons.find(query)
{
  "_id": ObjectId("5a4edc92d1c08bdedd106ecd"),
  "name": "Charmander",
  "description": "Esse é o cão chupando a manga",
  "type": "fogo",
  "attack": 52,
  "height": 0.6
}
{
  "_id": ObjectId("5a4edcabd1c08bdedd106ece"),
  "name": "Squirtle",
  "description": "Ejeta água que passarinho não bebe",
  "type": "água",
  "attack": 48,
  "height": 0.5
}
{
  "_id": ObjectId("5a4f72cc323fd547e724e755"),
  "name": "Venusaur",
  "description": "Depois de um dia de chuva, as flores voltam a ficar fortes",
  "attack": 82,
  "defense": 83,
  "height": 2
}
{
  "_id": ObjectId("5a4f731e323fd547e724e756"),
  "name": "Pidgeot",
  "description": "Pássaro topetudo",
  "attack": 80,
  "defense": 75,
  "height": 1.5
}
{
  "_id": ObjectId("5a4f7378323fd547e724e757"),
  "name": "Mewtwo",
  "description": "Pokemon criado por recombinação genética",
  "attack": 110,
  "defense": 90,
  "height": 2
}
{
  "_id": ObjectId("5a4f73c1323fd547e724e758"),
  "name": "Sandshrew",
  "description": "Quando está em perigo ele rola o seu corpo na areia e ataca",
  "attack": 75,
  "defense": 85,
  "height": 0.6
}
{
  "_id": ObjectId("5a4f7418323fd547e724e759"),
  "name": "Magneton",
  "description": "Um pokemon com fortes ondas magnéticas",
  "attack": 60,
  "defense": 95,
  "height": 1
}
Fetched 7 record(s) in 53ms

```
### 3 - Listar os Pokemons com a altura menor ou igual que 0.5 do tipo grama
```
matheus-NI-1406(mongod-2.6.10) pokemons> var query = {$and: [{height: {$lte: 0.5}}, {type: 'grama'}]}
matheus-NI-1406(mongod-2.6.10) pokemons> db.pokemons.find(query)
{
  "_id": ObjectId("5a4edc6cd1c08bdedd106ecc"),
  "name": "Bulbassauro",
  "description": "Chicote de trepadeira",
  "type": "grama",
  "attack": 49,
  "height": 0.4
}

```  
### 4 - Liste os Pokemons com o attack maior ou igual que 48 e com height menor ou igual que 0.5
```
matheus-NI-1406(mongod-2.6.10) pokemons> var query = {$or: [{attack: {$gte: 48}}, {height: {$lte: 0.5}}]}
matheus-NI-1406(mongod-2.6.10) pokemons> db.pokemons.find(query)
{
  "_id": ObjectId("5a4edac3e97e092b69f3dd5d"),
  "name": "Pikachu",
  "description": "Rato elétrico",
  "type": "electric",
  "attack": 55,
  "height": 0.4
}
{
  "_id": ObjectId("5a4edc6cd1c08bdedd106ecc"),
  "name": "Bulbassauro",
  "description": "Chicote de trepadeira",
  "type": "grama",
  "attack": 49,
  "height": 0.4
}
{
  "_id": ObjectId("5a4edc92d1c08bdedd106ecd"),
  "name": "Charmander",
  "description": "Esse é o cão chupando a manga",
  "type": "fogo",
  "attack": 52,
  "height": 0.6
}
{
  "_id": ObjectId("5a4edcabd1c08bdedd106ece"),
  "name": "Squirtle",
  "description": "Ejeta água que passarinho não bebe",
  "type": "água",
  "attack": 48,
  "height": 0.5
}
{
  "_id": ObjectId("5a4edee557e555da1bcbedef"),
  "name": "Cartepie",
  "description": "Larva lutadora",
  "type": "inseto",
  "attack": 30,
  "height": 0.3,
  "defense": 35
}
{
  "_id": ObjectId("5a4f72cc323fd547e724e755"),
  "name": "Venusaur",
  "description": "Depois de um dia de chuva, as flores voltam a ficar fortes",
  "attack": 82,
  "defense": 83,
  "height": 2
}
{
  "_id": ObjectId("5a4f731e323fd547e724e756"),
  "name": "Pidgeot",
  "description": "Pássaro topetudo",
  "attack": 80,
  "defense": 75,
  "height": 1.5
}
{
  "_id": ObjectId("5a4f7378323fd547e724e757"),
  "name": "Mewtwo",
  "description": "Pokemon criado por recombinação genética",
  "attack": 110,
  "defense": 90,
  "height": 2
}
{
  "_id": ObjectId("5a4f73c1323fd547e724e758"),
  "name": "Sandshrew",
  "description": "Quando está em perigo ele rola o seu corpo na areia e ataca",
  "attack": 75,
  "defense": 85,
  "height": 0.6
}
{
  "_id": ObjectId("5a4f7418323fd547e724e759"),
  "name": "Magneton",
  "description": "Um pokemon com fortes ondas magnéticas",
  "attack": 60,
  "defense": 95,
  "height": 1
}

```