# Módulo Web Scrap para produtos Submarino

[![npm](https://img.shields.io/npm/v/scrap-submarino.svg)](https://www.npmjs.com/package/scrap-submarino)
[![npm](https://img.shields.io/npm/dm/scrap-submarino.svg)](https://www.npmjs.com/package/scrap-submarino)

O **scrap-submarino** é um módulo para consulta de informações de produtos do Submarino.

O módulo faz a consulta via get no site Submarino pela URL e retorna as informações de: Nome, Preço, Imagem e ProdutoId.

**npm install scrap-submarino --save**

## Exemplo prático product

```js

var sscrap = require('scrap-submarino');
var url = 'http://www.submarino.com.br/produto/116796362/micro-ondas-consul-cm020-20l-cinza-espelhado';

sscrap.product(url).then(function(product) {
	console.log(product);
}, function(err){
	console.log(err);
});
```

### Objeto de Retorno

```js
{
  productId: '116796362',
  title: 'Micro-ondas Consul Cm020 20L Cinza Espelhado',
  price: '379.90',
  image: 'http://isuba1-a.akamaihd.net/produtos/01/00/item/116796/3/116796362_1GG.jpg'
}
```

### Objeto de erro

```js
 { error: 'Cannot get product' }
```

## Exemplo prático listProducts

```js

var sscrap = require('scrap-submarino');
var urls = [
	'http://www.submarino.com.br/produto/116796362/micro-ondas-consul-cm020-20l-cinza-espelhado',
	'http://www.submarino.com.br/produto/326208/frigobar-brastemp-pla-80-litros-brl08'
];

sscrap.listProducts(urls).then(function(list) {
	console.log(list);
}, function(err){
	console.log(err);
});
```

### Objeto de Retorno

```js
{
  productId: '116796362',
  title: 'Micro-ondas Consul Cm020 20L Cinza Espelhado',
  price: '379.90',
  image: 'http://isuba1-a.akamaihd.net/produtos/01/00/item/116796/3/116796362_1GG.jpg'
},
{
  productId: '326208',
  title: 'Frigobar Brastemp Pla 80 litros BRL08',
  price: '1956.99',
  image: 'http://images.submarino.com.br/produtos/01/00/item/326/2/326208_1GG.jpg'
}

```

### Objeto de erro

```js
 { error: 'Cannot get product' }
```
