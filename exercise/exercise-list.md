# Exercício Proposto

Segue uma lista de exercício com os conteúdos ensinado no módulo CSS. Siga o passo a passo de como mandar um exercício para a gente corrigir. Observe as issues. Ali você coloca o link do pull request criado da respectiva questão. Uma tabela será apresentada nas issues de cada exercício dizendo se você fez corretamente ou não. A legenda abaixo mostra o símbolo para casos de acerto perfeito, acerto e erro.

- :heavy_check_mark: (Acerto Perfeito)
- :o: (Acerto)
- :x: (Erro)

## Exercício 1
 Observe o código abaixo e complete a relação de parentesco abaixo:

```html
<html>
	<head>
		<meta charset="utf-8" />	
	</head>

	<body>
		<header>
			<img alt="logo do produto" src="img/logo.png"/>
			<nav>
				<ul>
					<li>Início</li>
					<li>Perfil</li>
					<li>Configurações</li>
				</ul>
			</nav>
		</header>

		<main>
			<h1>Meu produto</h1>
			<p>Algum texto sobre o meu produto</p>
		</main>

		<footer>
		</footer>
	</body>
</html>
```

1. `<meta charset="utf-8" />` é FILHO de `<head></head>`.
2. `<li>Configuração</li>` é DESCENDENTE de `<nav></nav>`.
3. `<li>Perfil</li>` é IRMÃO de `<li>Configuração</li>`.
4. `<li>Perfil</li>` é subsequente de <li>Início</li> .
5. `<main></main>` é filho de <body></body>.
6. `<footer></footer>` é irmão de <header></header>.
7. `<h1>Meu produto</h1>` é precedente de <p>Algum texto sobre o meu produto</p>.
8. `<p>Algum texto sobre o meu produto</p>` é DESCENDENTE de `<html></html>`..
9. `<ul></ul>` é PAI de `<li></li>`.
10. `<head></head>` é IRMÃO de `<body></body>`.

## Exercício 2

Para os seletores abaixo, diga qual o tipo dele.

1. `body { ... }`. SELETOR DE TIPO
2. `li:hover { ... }`. SELETOR DE PSEUDO-CLASSE
3. `p::before { ... }`. SELETOR DE PSEUDO-ELEMENTO
4. `body ul li { ... }`. SELETOR DE ESPECIFICIDADE
5. `.section-item { ... }`. SELETOR DE CLASSE
6. `section[class^="section-item"] { ... }`. SELETOR DE ATRIBUTO

## Exercício 3

Dado os seletores abaixo, forme o número de especificidade.

1. `body ul li { ... }`. 0003
2. `.section-item > p`. 0011
3. `head + body { ... }`. 0002
4. `#section-father ul li::before { ... }`. 0102
5. `section ul li:hover { ... }`. 0012

## Exercício 4

Dado o html abaixo, analise os itens com css e diga qual regra se aplica não levando em consideração a ordem na folha de estilo, ou seja, ignorando o 4 item do cálculo do efeito cascata.

```html
<header>
	<img alt="logo do produto" src="img/logo.png"/>
	<nav id="navbar">
		<ul id="navbar-list">
			<li class="navbar-item">Início</li>
			<li class="navbar-item">Perfil</li>
			<li class="navbar-item">Configurações</li>
		</ul>
	</nav>
</header>
```

1. 
```css
	#navbar ul { ... } --> 0201
	nav ul { ... } --> 0002
	header nav ul { ... } --> 0003
```

2.
```css
	nav ul li { ... } --> 0003
	header nav ul li { ... } --> 0004
	.navbar-item { ... } --> 0010
```

3.
```css
	nav ul .navbar-item { ... } --> 0012
	.navbar-item { ... } --> 0010
	nav[id="navbar"] ul li { ... } --> 0012
```
O ITEM "3" É O ÚNICO QUE TEM 2 SELETORES COM NÚMERO IGUAL DE PRIORIDADE, FAZENDO-SE NECESSÁRIO, PORTANTO, O USO DO ITEM 4 DO CÁLCULO DE EFEITO CASCATA. DESSE MODO, OS ITENS QUE IGNORAM-NO SÃO OS ITENS "1" E "2".

## Exercício 5

Em alguns sites nós temos um botão redondo com uma seta para cima que ao ser clicado, a tela volta para o início do site. Normalmente ele fica no canto inferior direito da tela. Crie um botão dessa forma e posicione-o nesse mesmo canto. Não é preciso realizar a funcionalidade de voltar para o início da tela. Deixe um espaçamento curto entre o botão e o fim da tela tanto no lado direito como na parte inferior.

Site para ícone: [link](https://www.flaticon.com/)
Regra para arrendodamento de um elemento: `border-radius: 50%`.

RESPOSTA:
```html
<!DOCTYPE html>
<html lang="pt-br">
    <head>
        <meta charset="utf-8">
        <link rel="stylesheet" href="ex5.css" type="text/css">
        <title>Exercício 5</title>
    </head>
    <body id="grid-container">
        <header>
            <h1 id="inicio">Início</h1>
        </header>
        <footer id="flex-container">
            <a href="#inicio"><img src="https://image.flaticon.com/icons/svg/17/17507.svg" alt="seta para cima"></a>
        </footer>
    </body>
</html>
```
```css
#grid-container {
    display: grid;
    grid-template-rows: 1fr 1fr;
    grid-row-gap: 1000px;
}

#flex-container {
    display: flex;
    justify-content: flex-end;
}

img {
    height: 50px;
    width: auto;
}

footer {
    align-self: end;
}
```

## Exercício 6

Um modal é um bloco que abre ao você clicar em algum elemento da tela principal. Crie um modal apenas com regras estilo de posicionamento. Não use flexbox ou grid layout. Veja a imagem abaixo para entender melhor o que é um modal.

![modal site do include 2019](../.github/exercise/modal.png)

**Dica**: Para fazer um fundo transparente, utilize a regra `background-color: rgba(0,0,0,0.2)`. Busque saber a lógica por trás da montagem de um modal antes de começar. Por exemplo, o modal deve ficar acima de todo o conteúdo principal no eixo z. Também não fica nem abaixo, nem acima.
RESPOSTA:
```html
<!DOCTYPE html>
<html lang="pt-br">
    <head>
        <meta charset="utf-8">
        <title>Exercício 6</title>
        <link rel="stylesheet" href="ex6.css" type="text/css">
    </head>
    <body>
        <section id="modal"></section>
    </body>
</html>
```
```css
body {
    background-color: rgba(0,0,0,0.2)
}

#modal {
    position: absolute;
    float: left;
    top: 180px;
    left: 410px;
    height: 300px;
    width: 400px;
    background-color: blue;
}
```

## Exercício 7

Repita o exercício anterior, mas agora centralize o "modal-content" com flexbox layout.
RESPOSTA:
```html
<!DOCTYPE html>
<html lang="pt-br">
    <head>
        <meta charset="utf-8">
        <title>Exercício 7</title>
        <link rel="stylesheet" href="ex7.css" type="text/css">
    </head>
    <body id="flex-container">
        <section id="modal"></section>
    </body>
</html>
```
```css
body {
    background-color: rgba(0,0,0,0.2);
    height: 600px;
}

#flex-container {
    display: flex;
    justify-content: center;
    align-items: center;
}

#modal {
    height: 300px;
    width: 400px;
    background-color: blue;
}
```

## Exercício 8

Com a propriedade `float: left`, crie uma barra de navegação lateral. Olha a imagem abaixo de uma barra lateral. Não use flexbox ou grid layout para resolução desse exercício. Antes de começar, defina quais os itens de sua navbar, a cor e se ela vai ter um elemento de busca e uma logo como a mostrada na imagem abaixo.

![Exemplo de barra de navegação](../.github/exercise/navbar.png)
RESPOSTA:
```html
<!DOCTYPE html>
<html lang="pt-br">
    <head>
        <meta charset="utf-8">
        <title>Exercício 8</title>
        <link rel="stylesheet" href="ex8.css" type="text/css">
        <link href="https://fonts.googleapis.com/css?family=Montserrat&display=swap" rel="stylesheet"> 
    </head>
    <body>
        <header>
        <nav>
            <img src="https://image.flaticon.com/icons/svg/1279/1279495.svg" alt="logo de um planeta estilizado">
            <form action="pesquisa.html" method="POST">
                <input type="text" name="busca" id="busca" placeholder="Pesquise aqui!">
                <input type="submit" value="Buscar">
            </form>
            <p>Sobre</p>
            <p>Membros</p>
            <p>Serviços</p>
            <p>Postagens</p>
            <p>Contato</p>                          
        </nav>
        </header>
    </body>
</html>
```
```css
body {
    height: 1000px;
    margin: 0;
    font-family: 'Montserrat', sans-serif;
}

nav {
    position: fixed;
    width: 100%;
    background-color: aqua;
}

img {
    margin-top: 5px;
    margin-left: 10px;
    margin-right: 10px;
    height: 40px;
    width: auto;
    float: left;
}

p {
    float: left;
    margin-left: 10px;
    margin-right: 10px;
    color: #3C4144;
}

form {
    margin-top: 10px;
    margin-left: 10px;
    margin-right: 10px;
    float: left;
}

nav p {
    font-weight: bold;
}
```
## Exercício 9

Faça o mesmo do exercício anterior, mas agora use flexbox layout para criar uma barra de navegação lateral.
RESPOSTA:
```html
<!DOCTYPE html>
<html lang="pt-br">
    <head>
        <meta charset="utf-8">
        <title>Exercício 9</title>
        <link rel="stylesheet" href="ex9.css" type="text/css">
        <link href="https://fonts.googleapis.com/css?family=Montserrat&display=swap" rel="stylesheet"> 
    </head>
    <body>
        <header>
        <nav>
            <img src="https://image.flaticon.com/icons/svg/1279/1279495.svg" alt="logo de um planeta estilizado">
            <form action="pesquisa.html" method="POST">
                <input type="text" name="busca" id="busca" placeholder="Pesquise aqui!">
                <input type="submit" value="Buscar">
            </form>
            <p>Sobre</p>
            <p>Membros</p>
            <p>Serviços</p>
            <p>Postagens</p>
            <p>Contato</p>                          
        </nav>
        </header>
    </body>
</html>
```

```css
body {
    height: 1000px;
    margin: 0;
    font-family: 'Montserrat', sans-serif;
}

nav {
    display: flex;
    flex-wrap: wrap;
    position: fixed;
    width: 100%;
    background-color: aqua;
}

img {
    margin-top: 5px;
    margin-left: 10px;
    margin-right: 10px;
    height: 40px;
    width: auto;
}

p {
    margin-left: 10px;
    margin-right: 10px;
    color: #3C4144;
}

form {
    margin-top: 10px;
    margin-left: 10px;
    margin-right: 10px;
}

nav p {
    font-weight: bold;
}
```

## Exercício 10

Com grid layout e flexbox, desenhe a bandeira do uruguai. Olhe a imagem abaixo:

![Bandeira do uruguai](../.github/exercise/uruguai.png)

A imagem do sol está na pasta `exercise10`. Busque não perder a resolução dessa imagem ao dimensionar as linhas e colunas.

## Exercício 11

Crie um footer com flexbox layout. Siga as seguintes especificações:

- O footer deve ter a logo da CEOS no primeiro flex item, o endereço da CEOS no segundo flex item e a logo da ufc no terceiro flex item.
- Quando a tela é menor ou igual a 1024px, a logo da ufc deve desaparecer.
- Quando a tela tiver 400px ou menos, a logo da ufc deve reaparecer e os elementos devem estar um abaixo do outro.

**Dica**: para fazer um elemento desaparecer no CSS, basta usar `display: none`.

As imagens da logo da CEOS e da UFC vão estar na pasta `exercise11`.
```html
<!DOCTYPE html>
<html lang="pt-br">
    <head>
        <meta charset="utf-8">
        <link rel="stylesheet" href="ex11.css" type="text/css">
        <title>Exercício 11</title>
    </head>
    <body>
        <header></header>
        <main></main>
        <footer id="flex-container">
            <img class="flex-item" src="https://raw.githubusercontent.com/arthus05/Capacitacao-CEOS-1-CSS/master/exercise/exercise11/ceos-logo-vertical.png" alt="logo da CEOS">
            <p class="flex-item">UFC Campus do Pici, Bloco 902 sala - 60020-181</p>
            <img class="flex-item" src="https://raw.githubusercontent.com/arthus05/Capacitacao-CEOS-1-CSS/master/exercise/exercise11/ufc-logo-vertical-01.png" alt="logo da UFC">
        </footer>
    </body>
</html>
```

```css
header {
    height: 200px;
}

main {
    height: 450px;
}

#flex-container {
    display: flex;
    align-items: flex-end;
    background-color: rgb(233, 182, 107);
}

img[alt="logo da UFC"] {
    height: 60px;
    width: auto;
}

img[alt="logo da CEOS"] {
    height: 60px;
    width: auto;
}

@media (max-width: 1024px) {
    img[alt="logo da UFC"] {
        display: none;
    }
}

@media (max-width: 400px) {
    #flex-container {
        display: flex;
        flex-wrap: wrap;
    }

    img[alt="logo da UFC"] {
        display: initial;
    }
}
```

## Exercício 12

Crie um header com flexboy layout. Siga as seguintes especificações:

- O header deve ter a logo da ceos horizontal e uma barra de navegação. Você pode definir os itens da barra de navegação.
- Quando a tela diminuir para 1024px, a barra de navegação se tornar um elemento com ícone de três barrinhas.
- As três barrinhas do ícone devem ser feitas apenas com CSS. Sem imagem.
- Não é preciso fazer a funcionalidade de ao clicar nas três barrinhas, faça aparecer o menu.

**Dica**: para fazer as três barrinhas, utilize os pseudoelementos `::before` e `::after`. Talvez definir tamanho e `display: block` possa ajudar. É de seu critério testar se isso resolve o seu problema ou não.
RESPOSTA:
```html
body {
    margin: 0px;
}

#flex-container {
    width: 100%;
    display: flex;
    position: fixed;
    background-color: #009bc3;
    background-image: linear-gradient(#009bc3, white)
}

.flex-item {
    margin-right: 10px;
    margin-left: 10px;
    font-family: 'Montserrat', sans-serif;
    color: #3C4144;
}

.traço {
    display: none;
    width: 25px;
    height: 4px;
    background-color: #1a4776;
    margin: 5px;
}

header {
    height: 500px;
    width: 100%;
    background-image: url(https://raw.githubusercontent.com/arthus05/Capacitacao-CEOS-1-CSS/master/exercise/exercise12/ceos-logo-horizontal.png); 
    background-repeat: no-repeat;
    background-position-y: 40px;
}

@media (max-width: 1024px) {
    .traço {
        display: block;
    }

    #flex-container {
        display: initial;
    }

    .flex-item {
        display: none;
    }
}
```

```css
<!DOCTYPE html>
<html lang="pt-br">
    <head>
        <meta charset="utf-8">
        <title>Exercício 12</title>
        <link rel="stylesheet" href="ex12.css" type="text/css">
        <link href="https://fonts.googleapis.com/css?family=Montserrat&display=swap" rel="stylesheet"> 
    </head>
    <body>
        <header>
            <nav id="flex-container">
                <section class="traço"></section>
                <section class="traço"></section>
                <section class="traço"></section>
                <p class="flex-item">Sobre</p>
                <p class="flex-item">Quem Somos</p>
                <p class="flex-item">Serviços</p>
                <p class="flex-item">Contato</p>
            </nav>
        </header>
    </body>
</html>
```

## Exercício 13

Crie um conteúdo principal com a imagem da CEOS que se encontra no google maps. Adicione um pequeno texto dizendo o que é a CEOS para você. Estilize da forma que você achar melhor.
RESPOSTA:
```html
<!DOCTYPE html>
<html lang="pt-br">
    <head>
        <meta charset="utf-8">
        <title>Exercício 13</title>
        <link rel="stylesheet" href="ex13.css" type="text/css">
        <link href="https://fonts.googleapis.com/css?family=Montserrat&display=swap" rel="stylesheet"> 
    </head>
    <body>
        <main>
            <img src="https://lh5.googleusercontent.com/p/AF1QipOCvEGXa8GGE8daRvWdcIZyj6ePpCkG1iXo9LRp=w408-h544-k-no" alt="porta da CEOS">
            <p>A CEOS é a empresa júnior de computação da UFC - Fortaleza. Marcada por resiliência, companheirismo, e pelo uso
                de tecnologias de qualidade, acredito que seja uma EJ com um grande potencial de crescimento. Vejo que a empresa
                tem capacidade de produzir projetos de altíssima qualidade, de forma a destacar-se no mercado e, com isso, junto a
                atual reorganização administrativa geral que ela está passando, alcançar tal crescimento latente.
            </p>
        </main>
    </body>
</html>
```
```css
body {
    margin: 0px;
    font-family: 'Montserrat', sans-serif;
    color: #3C4144;
}

main {
    float: left;
}

main img {
    float: left;
    border-radius: 5%;
    margin: 10px;
}

main p {
    float: left;
    width: 300px;
    margin: 10px;
}
```
## Exercício 14

Crie um conteúdo lateral com os links das redes sociais da CEOS.
```html
<!DOCTYPE html>
<html lang="pt-br">
    <head>
        <meta charset="utf-8">
        <title>Exercício 14</title>
        <link rel="stylesheet" href="ex14.css" type="text/css">
        <link href="https://fonts.googleapis.com/css?family=Montserrat&display=swap" rel="stylesheet"> 
    </head>
    <body>
        <aside id="grid-container">
            <a href="https://www.instagram.com/ceosjr/" target="blank"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a5/Instagram_icon.png/599px-Instagram_icon.png" alt="ícone instagram"></a>
            <a href="https://www.facebook.com/ceos.jr/" target="blank"><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAOEAAADhCAMAAAAJbSJIAAAAaVBMVEU6VZ////81Up0yT5xgc61+jbsvTZyXo8hFXaOirM0nSJmlrs7O1OUkRpkfQ5c1UZ1oerKHlcDp6/M9WKHHzeHV2ulxgravt9Td4Ozl6PGDkb7ByN5YbatQZ6j29/q3v9h2hrhMY6aQnMSsAnKHAAAC70lEQVR4nO3caXLiMBRFYdoihhhsQ5jDlPT+F9mdqv7bRrYQ7z7XOQug9BUWHiQzmRARERERERERERERERERqVe0IZQPCtaDHFwo62Yz/VrP3jtbrH0Sy7rYH46/YtpV1oPtX6jCbBel+2npThjq/Taa51AYmrdTH583YdHsP/r5nAnLTa/j05+w+ezv8yRsq/MQoB9hmPeegb6E5eU2DOhFWK4G+rwIw3CgD2G4Dge6ELaboXPQi7CJu4nwK6zvKUAHwvCVBHQgrFMmoQdh4jGqL2wviUB5YRP/uMKnsJ2mAtWF9XLkwjblcs2FsDqMXZh6LpQXhn06UFtYpZ7t5YX1wEczboTF/AlAaWFYP0OovPZU9pmGt9194W79sIq/Jt2uqqrytwbcxJ4NT9e6tR7soEIk8N749E2K7zjgubEe6dAi75yOboGxwrnTQ/RvRZTwIHy6e1SccF5Yj3N4UcJjbT3MhKKEh9J6mAlFCZWvyR4WJXxDqBxChPohRKgfQoT6IUSoH0KE+iFEqB9ChPqNQ1h0vKJcxWwt/aofvelsDFzNOlpECO9dH/DT+8ZUWMYgErNdfXuB8Ga7RPwCofHy2wuE59EfpQvbH9MXCNejF65st2q8QPhtu5Mhv/BmfE2TX/hhvGMqv3BpvBslv/BuvGUqv3A2+nloff+YX3gx3rmYX2j9CCC78Ga9NzO78GS9dTG7cDv679B8c2Z24e/R/9LsRy+8Wm/kzy60nobZhdb3TvmF9u8e5hYaP0p8gfB99PPQ/l2F3MKp+StDuYXWvuxC60eJ+YXm907ZhQJ/NlA+4d9ZOrrbH6WTzbyjmL+D/Oz6BNsl/H8V/y9E7TYpOz7BGveoceyn6QohQv0QItQPIUL9ECLUDyFC/RAi1A8hQv0QItQPIUL9ECLUDyFC/RAi1A8hQv0QItQPIUL9ECLUDyFC/RAi1A8hQv0QItQPIUL9ECLUDyFC/RAi1A8hQv0QItQPIUL9ECLs0R8aFUYEFLSeAgAAAABJRU5ErkJggg==" alt="ícone facebook"></a>
            <a href="https://twitter.com/ceos_jr" target="blank"><img src="http://www.sibi.usp.br/wp-content/uploads/2017/01/twitter-icon-77.png" alt="ícone twitter"></a>
            <a href="https://pt.linkedin.com/company/ceos-jr-empresa-junior-da-computa%C3%A7%C3%A3o-ufc" target="blank"><img src="data:image/png;base64,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" alt="ícone linkedin"></a>
        </aside>
    </body>
</html>
```
```css
body {
    margin: 0px;
    font-family: 'Montserrat', sans-serif;
    color: #3C4144;
}

#grid-container {
    display: grid;
    grid-template-rows: 1fr 1fr 1fr 1fr;
    justify-content: right;
}

aside img {
    height: 40px;
    width: auto;
    margin-top: 10px;
}

img[alt="ícone instagram"] {
    grid-row: 1/2;
}

img[alt="ícone facebook"] {
    grid-row: 2/3;
}

img[alt="ícone twitter"] {
    grid-row: 3/4;
}

img[alt="ícone linkedin"] {
    grid-row: 4/5;
}
```
## Exercício 15

Pegue o html e css feito nos exercícios 11, 12, 13, 14 e utilizando grid layout posicione-os de forma que fique como a imagem abaixo no mesmo documento.

![Template](../.github/part-four/template.png)

Quando a tela for menor ou igual a 1024px, faça desaparecer o conteúdo lateral.
RESPOSTA:
```html
<!DOCTYPE html>
<html lang="pt-br">
    <head>
        <meta charset="utf-8">
        <title>Exercício 15</title>
        <link rel="stylesheet" href="ex15.css" type="text/css">
        <link href="https://fonts.googleapis.com/css?family=Montserrat&display=swap" rel="stylesheet"> 
    </head>
    <body id="grid-container">
        <header>
                <nav id="flex-container-header">
                    <section class="traço"></section>
                    <section class="traço"></section>
                    <section class="traço"></section>
                    <p class="flex-item-header">Sobre</p>
                    <p class="flex-item-header">Quem Somos</p>
                    <p class="flex-item-header">Serviços</p>
                    <p class="flex-item-header">Contato</p>
                </nav>
        </header>
        <main>
                <img src="https://lh5.googleusercontent.com/p/AF1QipOCvEGXa8GGE8daRvWdcIZyj6ePpCkG1iXo9LRp=w408-h544-k-no" alt="porta da CEOS">
                <p>A CEOS é a empresa júnior de computação da UFC - Fortaleza. Marcada por resiliência, companheirismo, e pelo uso
                    de tecnologias de qualidade, acredito que seja uma EJ com um grande potencial de crescimento. Vejo que a empresa
                    tem capacidade de produzir projetos de altíssima qualidade, de forma a destacar-se no mercado e, com isso, junto a
                    atual reorganização administrativa geral que ela está passando, alcançar tal crescimento latente.
                </p>
        </main>
        <aside id="grid-container-aside">
            <a class="grid-item" href="https://www.instagram.com/ceosjr/" target="blank"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a5/Instagram_icon.png/599px-Instagram_icon.png" alt="ícone instagram"></a>
            <a class="grid-item" href="https://www.facebook.com/ceos.jr/" target="blank"><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAOEAAADhCAMAAAAJbSJIAAAAaVBMVEU6VZ////81Up0yT5xgc61+jbsvTZyXo8hFXaOirM0nSJmlrs7O1OUkRpkfQ5c1UZ1oerKHlcDp6/M9WKHHzeHV2ulxgravt9Td4Ozl6PGDkb7ByN5YbatQZ6j29/q3v9h2hrhMY6aQnMSsAnKHAAAC70lEQVR4nO3caXLiMBRFYdoihhhsQ5jDlPT+F9mdqv7bRrYQ7z7XOQug9BUWHiQzmRARERERERERERERERERqVe0IZQPCtaDHFwo62Yz/VrP3jtbrH0Sy7rYH46/YtpV1oPtX6jCbBel+2npThjq/Taa51AYmrdTH583YdHsP/r5nAnLTa/j05+w+ezv8yRsq/MQoB9hmPeegb6E5eU2DOhFWK4G+rwIw3CgD2G4Dge6ELaboXPQi7CJu4nwK6zvKUAHwvCVBHQgrFMmoQdh4jGqL2wviUB5YRP/uMKnsJ2mAtWF9XLkwjblcs2FsDqMXZh6LpQXhn06UFtYpZ7t5YX1wEczboTF/AlAaWFYP0OovPZU9pmGt9194W79sIq/Jt2uqqrytwbcxJ4NT9e6tR7soEIk8N749E2K7zjgubEe6dAi75yOboGxwrnTQ/RvRZTwIHy6e1SccF5Yj3N4UcJjbT3MhKKEh9J6mAlFCZWvyR4WJXxDqBxChPohRKgfQoT6IUSoH0KE+iFEqB9ChPqNQ1h0vKJcxWwt/aofvelsDFzNOlpECO9dH/DT+8ZUWMYgErNdfXuB8Ga7RPwCofHy2wuE59EfpQvbH9MXCNejF65st2q8QPhtu5Mhv/BmfE2TX/hhvGMqv3BpvBslv/BuvGUqv3A2+nloff+YX3gx3rmYX2j9CCC78Ga9NzO78GS9dTG7cDv679B8c2Z24e/R/9LsRy+8Wm/kzy60nobZhdb3TvmF9u8e5hYaP0p8gfB99PPQ/l2F3MKp+StDuYXWvuxC60eJ+YXm907ZhQJ/NlA+4d9ZOrrbH6WTzbyjmL+D/Oz6BNsl/H8V/y9E7TYpOz7BGveoceyn6QohQv0QItQPIUL9ECLUDyFC/RAi1A8hQv0QItQPIUL9ECLUDyFC/RAi1A8hQv0QItQPIUL9ECLUDyFC/RAi1A8hQv0QItQPIUL9ECLUDyFC/RAi1A8hQv0QItQPIUL9ECLs0R8aFUYEFLSeAgAAAABJRU5ErkJggg==" alt="ícone facebook"></a>
            <a class="grid-item" href="https://twitter.com/ceos_jr" target="blank"><img src="http://www.sibi.usp.br/wp-content/uploads/2017/01/twitter-icon-77.png" alt="ícone twitter"></a>
            <a class="grid-item" href="https://pt.linkedin.com/company/ceos-jr-empresa-junior-da-computa%C3%A7%C3%A3o-ufc" target="blank"><img src="data:image/png;base64,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" alt="ícone linkedin"></a>
        </aside>
        <footer id="flex-container-footer">
                <img src="https://raw.githubusercontent.com/arthus05/Capacitacao-CEOS-1-CSS/master/exercise/exercise11/ceos-logo-vertical.png" alt="logo da CEOS">
                <p>UFC Campus do Pici, Bloco 902 sala - 60020-181</p>
                <img src="https://raw.githubusercontent.com/arthus05/Capacitacao-CEOS-1-CSS/master/exercise/exercise11/ufc-logo-vertical-01.png" alt="logo da UFC">
        </footer>
    </body>
</html>
```css
/*BODY*/
body {
    margin: 0px;
    font-family: 'Montserrat', sans-serif;
    color: #3C4144;
}

#grid-container {
    height: 100%;
    display: grid;
    grid-template-areas: 
	"hd hd hd"
	"mn mn as"
	"mn mn as"
	"ft ft ft";
}

header {
	grid-area: hd;
}

main {
	grid-area: mn;
}

aside {
	grid-area: as;
}

footer {
	grid-area: ft;
}

/*HEADER*/

#flex-container-header {
    width: 100%;
    display: flex;
    position: fixed;
    background-color: #009bc3;
    background-image: linear-gradient(#009bc3, white)
}

.flex-item {
    margin-right: 10px;
    margin-left: 10px;
    font-family: 'Montserrat', sans-serif;
    color: #3C4144;
}

.traço {
    display: none;
    width: 25px;
    height: 4px;
    background-color: #1a4776;
    margin: 5px;
}

header {
    height: 500px;
    width: 100%;
    background-image: url(https://raw.githubusercontent.com/arthus05/Capacitacao-CEOS-1-CSS/master/exercise/exercise12/ceos-logo-horizontal.png); 
    background-repeat: no-repeat;
    background-position-y: 40px;
}

/*MAIN*/
main {
    float: left;
}

main img {
    float: left;
    border-radius: 5%;
    margin: 10px;
}

main p {
    float: left;
    width: 300px;
    margin: 10px;
}


#grid-container-aside {
    display: grid;
    grid-template-rows: 1fr 1fr 1fr 1fr;
    justify-content: right;
}

/*ASIDE*/
aside img {
    height: 40px;
    width: auto;
    margin-top: 10px;
}

img[alt="ícone instagram"] {
    grid-row: 1/2;
}

img[alt="ícone facebook"] {
    grid-row: 2/3;
}

img[alt="ícone twitter"] {
    grid-row: 3/4;
}

img[alt="ícone linkedin"] {
    grid-row: 4/5;
}

/*FOOTER*/
#flex-container-footer {
    display: flex;
    align-items: flex-end;
    background-color: #009bc3;
    background-image: linear-gradient(white, #009bc3)
}

img[alt="logo da UFC"] {
    height: 60px;
    width: auto;
}

img[alt="logo da CEOS"] {
    height: 60px;
    width: auto;
}

/*MEDIA QUERIES*/

@media (max-width: 1024px) {
    aside {
        display: none;
    }

    .traço {
        display: block;
    }

    #flex-container-header {
        display: initial;
    }

    .flex-item-header {
        display: none;
    }
    .grid-item {
        display: none;
    }
}
```
