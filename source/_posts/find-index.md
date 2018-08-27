---
title: Método findIndex() Javascript
date: 2018-08-27 11:43:25
tags: Javascript, Front-end 
postKeywords: JS, findindex, ecmascript, dicas de javascript, retornar indice.
postDescription: Método para encontrar índice de um array que não sabemos exatamente a posição que se encontra
author: Victor Jordan
authorImg: victor.png
authorDesc: Desenvolvedor front-end na FITec e formando em Banco de Dados pela Fatec, apaixonado por usabilidade, performance e UX!
authorLinkedin: victorjordan95
authorGithub: victorjordan95
---

## Definição

O método `findIndex()` retorna o índice do primeiro elemento que satisfaz uma determinada condição. Caso não encontre nenhuma, ele retorna -1.

## Aplicação

Podemos utilizar caso seja necessário encontrar o índice de um array mas não sabemos em que posição ele se encontra, como por exemplo, temos o seguinte JSON:

<!-- more --> 

``` javascript
const lista = [
    { role: 'DOUTORADO', name: 'Doutorado' },
    { role: 'MESTRADO', name: 'Mestrado' },
    { role: 'POS_GRADUACAO', name: 'Pós-graduação' },
    { role: 'GRADUACAO', name: 'Graduação' },
    { role: 'ENSINO_MEDIO', name: 'Ensino Médio' },
    { role: 'NONE', name: 'None' }
];
```

Em nossa API, quando fazemos o GET do usuário, ele retorna a apenas a `role` do usuário. Por questões visuais, não podemos deixar exibindo na tela uma informação sem a devida tratativa, correto? Então como faríamos para acessar o `name` da lista através da `role` que temos na mão? Para isso, podemos usar o FindIndex!

Com uma variável auxiliar, encontramos o index da role desejada e acessamos o valor do name através dela! No exemplo, vamos usar 'ENSINO_MEDIO' como um valor vindo da API.

``` javascript
const educationIndex = lista.findIndex(item => item.role === 'ENSINO_MEDIO'); // Busca o Index que tenha a role como 'ENSINO_MEDIO'
const escolaridade = lista[educationIndex].name // Sabendo o índice, fica fácil acessar o name desejado
```

E o resultado:
![Retorno da função: Ensino Médio](/posts/findIndex-exemplo.gif)

Bem fácil e pode ser muito útil quando precisamos acessar um valor que não sabemos o índice diretamente!

