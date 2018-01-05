# MongoDB - Aula 01 - Exercício
autor: MatheusPSantos

## Importando os restaurantes

```
mongoimport --db meu-banco --collection restaurantes --host=127.0.0.1 --drop --file restaurantes.json

2018-01-04T23:23:21.961-0200 dropping: be-mean.restaurantes
2018-01-04T23:23:24.253-0200 check 9 25359
2018-01-04T23:23:26.459-0200 imported 25359 objects

```

## Contando os restaurantes
```
> use meubanco
switched to db meubanco

> db.restaurantes.find({}).count()
25359
```
