# VivaReal Code Challenge :)

<!-- If you prefer, you can read our [english version](README-en.md). -->

## Pré-requisito

Conheça a [lenda de Spottipos](historia.md)

## Propósito deste desafio

Este desafio tem o intuito de entender a forma como você pensa para resolver os problemas, como você organiza seu código e quais tecnologias você se sente mais confortável.

## Sobre o desafio

Dependendo da sua experiência e/ou das ferramentas escolhidas, você pode precisar de mais ou menos tempo para realizar o desafio. Em geral 2 horas são suficientes.

Para isso, vamos fornecer para você alguns dados. Neste [json](database.json) você encontra uma série de imóveis listados com a seguinte estrutura:

```javascript
{
  "totalProperties": 1, // total number of properties on this json
  "properties": [ // array of properties
    {
      "id": 1, // id :P
      "x": 870, // x (spottipos geographic coordinate)
      "y": 867, // y (spotippos geographic coordinate)
      "beds": 5, // number of beds
      "baths": 4, // number of baths
      "provinces" : ["Scavy"], // spotippos provinces
      "squareMeters": 134
    }
  ]
}
```

## Desafio

Em Spottipos temos as seguintes regras:

Um imóvel em Spottipos tem as seguintes características:
  - No máximo 5 quartos (beds), e no mínimo 1
  - No máximo 4 banheiros (baths), e no mínimo 1
  - No máximo 240 metros quadrados, e no mínimo 20


Usando as informações anteriores, crie uma API REST que execute as seguintes funções:

### 1. Busque os imóveis em Spottipos :P

Do mesmo modo que as áreas das províncias de Spotippos são delimitadas, queremos saber os imóveis de uma certa região dado os pontos A e B, onde A é o ponto superior esquerdo e B é o ponto inferior direito. Cada ponto é representado pelas cordenadas x e y. Sendo assim, a estrutura da url a ser seguida deve ser: 

Request:
```
  GET /properties?ax={integer}&ay={integer}&bx={integer}&by={integer}
```

Response:

```json
{
  "foundProperties": 3,
  "properties": [
    {
      "id": 34,
      "x": 999,
      "y": 333,
      "beds": 4,
      "baths": 3,
      "provinces" : [ "Gode", "Ruja"],
      "squareMeters": 237
    },
    {...},
    {...}
  ]
}
```

### 2. Crie imóveis em Spottipos :D

A partir da estrutura abaixo em `Request` e `Body` permita a criação de um imóvel. Todos os campos são obrigatórios e devem respeitar as regras enunciadas neste desafio e nos limites geográficos de Spottipos.

Request:
```
POST /properties
```

Body:
```json
{
  "x": 222,
  "y": 444,
  "beds": 4,
  "baths": 3,
  "squareMeters": 210
}
```

Response:

Você define, faz parte da avaliação.

### 3. Mostre um imóvel específico em Spottipos =]

Busque um imóvel específico a partir de seu `id`.

Request:
```
  GET /properties/{id}
```

Response:

```json
{
  "id": 665,
  "x": 667,
  "y": 556,
  "beds": 1,
  "baths": 1,
  "provinces" : ["Ruja"],
  "squareMeters": 42
}
```

### 4. Uau! Agora temos que fazer deploy! :@

Crie uma documentação de como fazer para rodar o seu projeto. Quanto mais simples, melhor! ;)


## Modo de avaliação

Nós sempre avaliamos o seu código, e para isso nós envolvemos sempre no mínimo 3 engenheiros aqui do Viva e amigavelmente informamos que iremos nos basear pelos seguintes critérios:

* **Manutenibilidade:** É um código legível, de fácil manutenção.
* **Desenho:** Como você separou as reponsabilidades. Quais técnicas utilizou.
* **Qualidade:** Tem testes? Quão difícil é recriar os testes caso seja necessário alterar o comportamento da aplicação?
* **Desempenho:** Escreveu um código com performance adequada? Não precisa ser perfeito, mas entende como seria a solução perfeita?

Fique a vontade para incrementar e deixar a sua API de Spottipos ainda melhor !

Boa sorte, agora vá programar ;)
