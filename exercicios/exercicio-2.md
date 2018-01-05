# MongoDB - Aula 02 - Exercício
autor: MatheusPSantos

## Passos do exercício
### 1 - Criar uma database chamada pokemons

### 2 - Listar quais databases você tem no servidor
```
> show dbs
admin     (empty)
meubanco   0.078GB
local     0.078GB
pokemons  0.078GB

```

### 3 - Listar quais coleções você possui nessa database
```
> use pokemons
switched to db pokemons
> show collections
pokemons
system.indexes

```

### 4 - Inserir 5 pokemons utilizando o padrão a seguir
```
{
    'name': ,
    'description': ,
    'attack': ,
    'defense': ,
    height: 
}
```

### 5 - Listar os pokemons existentes na sua coleção
```
> db.pokemons.find()
{ 
    "_id" : ObjectId("5a4edac3e97e092b69f3dd5d"), 
    "name" : "Pikachu", 
    "description" : "Rato elétrico", "type" : "electric", 
    "attack" : 55, 
    "height" : 0.4 
}
{ 
    "_id" : ObjectId("5a4edc6cd1c08bdedd106ecc"), 
    "name" : "Bulbassauro", 
    "description" : "Chicote de trepadeira", "type" : "grama", 
    "attack" : 49, 
    "height" : 0.4 
}
{ 
    "_id" : ObjectId("5a4edc92d1c08bdedd106ecd"), 
    "name" : "Charmander", 
    "description" : "Esse é o cão chupando a manga", "type" : "fogo", 
    "attack" : 52, 
    "height" : 0.6 
}
{ 
    "_id" : ObjectId("5a4edcabd1c08bdedd106ece"), 
    "name" : "Squirtle", 
    "description" : "Ejeta água que passarinho não bebe", "type" : "água", 
    "attack" : 48, 
    "height" : 0.5 
}
{ 
    "_id" : ObjectId("5a4edee557e555da1bcbedef"), 
    "name" : "Cartepie", 
    "description" : "Larva lutadora", "type" : "inseto", 
    "attack" : 30, 
    "height" : 0.3, 
    "defense" : 35 
}
{ 
    "_id" : ObjectId("5a4f72cc323fd547e724e755"), 
    "name" : "Venusaur", 
    "description" : "Depois de um dia de chuva, as flores voltam a ficar fortes", 
    "attack" : 82, 
    "defense" : 83, 
    "height" : 2 
}
{ 
    "_id" : ObjectId("5a4f731e323fd547e724e756"), 
    "name" : "Pidgeot", 
    "description" : "Pássaro topetudo", 
    "attack" : 80, 
    "defense" : 75, 
    "height" : 1.5 
}
{ 
    "_id" : ObjectId("5a4f7378323fd547e724e757"), 
    "name" : "Mewtwo", 
    "description" : "Pokemon criado por recombinação genética", 
    "attack" : 110, 
    "defense" : 90, 
    "height" : 2 
}
{ 
    "_id" : ObjectId("5a4f73c1323fd547e724e758"), 
    "name" : "Sandshrew", 
    "description" : "Um tatu bolado", 
    "attack" : 75, 
    "defense" : 85, 
    "height" : 0.6 
}
{ 
    "_id" : ObjectId("5a4f7418323fd547e724e759"), 
    "name" : "Magneton", 
    "description" : "Um pokemon com fortes ondas magnéticas", 
    "attack" : 60, 
    "defense" : 95, 
    "height" : 1 
}

```

### 6 -Buscar os pokemons a sua escolha pelo nome, e armazena-los em uma variável 'poke'
```
> var query = {name:'Sandshrew'}
> var poke = db.pokemons.findOne(query)
> poke
{
	
    "_id" : ObjectId("5a4f73c1323fd547e724e758"),

	"name" : "Sandshrew",
	"description" : "Um tatu bolado",
	"attack" : 75,
	"defense" : 85,
	"height" : 0.6
}
```

### 7 - Modifique sua 'description' e salve
```
> poke.description = 'Quando está em perigo ele rola o seu corpo na areia e ataca'
Quando está em perigo ele rola o seu corpo na areia e ataca
> db.pokemons.save(poke)
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
```