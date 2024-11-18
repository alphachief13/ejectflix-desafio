# Função para Renderizar Divs

A função **renderizar divs** deixa o HTML mais limpo, evitando a repetição de código. Ela irá renderizar divs que possuem o mesmo HTML de forma dinâmica.

---

## Como a função sabe qual é a div que eu quero renderizar?

No arquivo `utils/template.js`, você precisa criar um **template** (esqueleto HTML) da div. Onde os dados da div mudam, você os insere entre chaves `{}`.

### Exemplo:

```javascript
const cardArtigo = `
    <div>
        <img class="card-artigo" src={imagem}>
        <p class="card-descricao">{descricao}</p>
    </div>
`;
```


## Como a função vai saber quantas divs eu quero renderizar e quais são os dados de cada uma?

Você precisa ir no arquivo `utils/data.js` e criar um array de objetos. Cada objeto terá as propriedades que irão ser dinâmicas na div.

Ex.:

```javascript
const cardArtigoData = [
    {
        imagem: "../img/home/artigos-e-materiais-home/artigo-1.png",
        descricao: "Lorem ipsum dolor sit amet, consectetur",
    },
    {
        imagem: "../img/home/artigos-e-materiais-home/artigo-2.png",
        descricao: "Lorem ipsum dolor sit amet, consectetur",
    },
    {
        imagem: "../img/home/artigos-e-materiais-home/artigo-3.png",
        descricao: "Lorem ipsum dolor sit amet, consectetur",
    },
];
```

## E como finalmente renderizar o template com os dados corretos? 

Depois de ter feito o data e o template correto para sua div, basta você ir no HTML e criar a div com um id para o .js identificar. Depois, crie um .js para esse html e utilize a função renderizarDivs, passando os parametros corretos

Ex.:

```html
<div id="artigos">
</div>
```

```javascript
// id, data, template
renderizarDivs("artigos", cardArtigoData, cardArtigo)
```