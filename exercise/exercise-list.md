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

1. `<meta charset="utf-8" />` é filho de `<head></head>`.
2. `<li>Configuração</li>` é descendente de `<nav></nav>`.
3. `<li>Perfil</li>` é irmão de `<li>Configuração</li>`.
4. `<li>Perfil</li>` é subsequente de `<li>Início</li>`.
5. `<main></main>` é filho de `<body></body>`.
6. `<footer></footer>` é irmão de `<header></header>` e `<main></main>`.
7. `<h1>Meu produto</h1>` é precedente de `<p>Algum texto sobre o meu produto</p>`.
8. `<p>Algum texto sobre o meu produto</p>` é descendente de `<html></html>`..
9. `<ul></ul>` é pai de `<li></li>`.
10. `<head></head>` é irmão de `<body></body>`.

## Exercício 2

Para os seletores abaixo, diga qual o tipo dele.

1. `body { ... }`	'seletor de tipo'.
2. `li:hover { ... }`	'seletor pseudoclasse'.
3. `p::before { ... }`	'seletor pseudoelemento.
4. `body ul li { ... }`	'seletor de tipo'.
5. `.section-item { ... }`	'seletor classe'.
6. `section[class^="section-item"] { ... }` 'seletor de atributo'.

## Exercício 3

Dado os seletores abaixo, forme o número de especificidade.

1. `body ul li { ... }`	0003.
2. `.section-item > p`	0011.
3. `head + body { ... }`	0002.
4. `#section-father ul li::before { ... }`	0102.
5. `section ul li:hover { ... }`	0012.

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
	#navbar ul { ... }
	nav ul { ... }
	header nav ul { ... }
```
- Aplica-se: #navbar ul { ... }

2.
```css
	nav ul li { ... }
	header nav ul li { ... }
	.navbar-item { ... }
```
- Aplica-se: .navbar-item { ... }

3.
```css
	nav ul .navbar-item { ... }
	.navbar-item { ... }
	nav[id="navbar"] ul li { ... }
```
- Aplica-se: nav[id="navbar"] ul li { ... } (mas não há desempate de prioridade desconsiderando a ordem da folha de estilo)

## Exercício 5

Em alguns sites nós temos um botão redondo com uma seta para cima que ao ser clicado, a tela volta para o início do site. Normalmente ele fica no canto inferior direito da tela. Crie um botão dessa forma e posicione-o nesse mesmo canto. Não é preciso realizar a funcionalidade de voltar para o início da tela. Deixe um espaçamento curto entre o botão e o fim da tela tanto no lado direito como na parte inferior.

Site para ícone: [link](https://www.flaticon.com/)
Regra para arrendodamento de um elemento: `border-radius: 50%`.
```html
<html>
	<head>
		<meta charset="utf-8">
		<title>Exercício 5</title>
		<style type="text/css">
			.content {
				display: flex;
			}
			button {
				border-radius: 50%;
				float: right;
				margin-right: 18px;
				margin-bottom: 22px;
			}
			section > img {
				margin: 15% 15% 0% 15%;
				height: 40%;
				width: 50%;
			}
			button > img {
				max-height: 30px;
				max-width: 30px;
			}
			footer {
				margin: 20px 0 0 5px;
			}
		</style>
	</head>
	<body>
		<section class="content">
			<section>
				<p>paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
				<p>When you have Alzheimer and you forget you already wrote a paragraph</p>
			</section>
			<section>
				<img src="https://i.warosu.org/data/lit/img/0102/37/1510082608785.jpg">
			</section>
		</section>
		<footer>
			Icons made by <a href="https://www.flaticon.com/authors/dave-gandy" title="Dave Gandy">Dave Gandy</a> from <a href="https://www.flaticon.com/" title="Flaticon">www.flaticon.com</a> is licensed by <a href="http://creativecommons.org/licenses/by/3.0/" title="Creative Commons BY 3.0" target="_blank">CC 3.0 BY</a>
			<button>
				<img src="https://image.flaticon.com/icons/svg/25/25366.svg">
			</button>
		</footer>
	</body>
</html>
```

## Exercício 6

Um modal é um bloco que abre ao você clicar em algum elemento da tela principal. Crie um modal apenas com regras estilo de posicionamento. Não use flexbox ou grid layout. Veja a imagem abaixo para entender melhor o que é um modal.

![modal site do include 2019](../.github/exercise/modal.png)

**Dica**: Para fazer um fundo transparente, utilize a regra `background-color: rgba(0,0,0,0.2)`. Busque saber a lógica por trás da montagem de um modal antes de começar. Por exemplo, o modal deve ficar acima de todo o conteúdo principal no eixo z. Também não fica nem abaixo, nem acima.

```html
<html>
	<head>
		<meta charset="utf-8">
		<title>Exercício 6</title>
		<style type="text/css">
			th {
				background-color: #000000;
				color: white;
			}
			th, td {
				font-size: 48px;
				height: 24%;
			}
			td:hover {
				background-color: gray;
				cursor: pointer;
			}
			#manha {
				position: fixed;
				top: 0;
				left: 0;
				width: 100%;
				height: 100%;
				text-align: center;
				font-size: 32px;
				background-color: rgba(0,0,0,0.2)
			}
			#tarde, #noite {
				display: none;
			}
			.texto {
				margin: 12.5% 0 0 25%;
				width: 50%;
				height: 50%;
				background-color: yellow;
			}
		</style>
	</head>
	<body>
		<h1>Rotina de um <i>Pigervitae lascivus</i></h1>
		<table>
			<tr id="dias">
				<th></th>
				<th>Segunda</th>
				<th>Terça</th>
				<th>Quarta</th>
				<th>Quinta</th>
				<th>Sexta</th>
				<th>Sábado</th>
				<th>Domingo</th>
			</tr>
			<tr>
				<th>Manhã</th>
				<td>Comer</td>
				<td>Comer</td>
				<td>Comer</td>
				<td>Comer</td>
				<td>Comer</td>
				<td>Comer</td>
				<td>Comer</td>
			</tr>
			<tr>
				<th>Tarde</th>
				<td>Reproduzir</td>
				<td>Reproduzir</td>
				<td>Reproduzir</td>
				<td>Reproduzir</td>
				<td>Reproduzir</td>
				<td>Reproduzir</td>
				<td>Reproduzir</td>
			</tr>
			<tr>
				<th>Noite</th>
				<td>Dormir</td>
				<td>Dormir</td>
				<td>Dormir</td>
				<td>Dormir</td>
				<td>Dormir</td>
				<td>Dormir</td>
				<td>Dormir</td>
			</tr>
		</table>
		<section id="manha">
			<section class="texto">
				<p>"ao clicar em 'Comer'":</p>
				<p>Nutrir-se é obter os nutrientes necessários às atividades celulares.</p>
				<p> <i>Pigervitae lascivus</i> obtém-nos ao comer alimentos, ou seja, introduzir aglomerados de nutrientes através de um sistema (conjunto de órgãos) chamado "digestivo" </p>
				<p>O excesso disso é o pecado da gula.</p>
			</section>
		</section>
		<section id="tarde">
			<section class="texto">
				<p>Reproduzir-se é gerar algo semelhante a si.</p>
				<p> <i>Pigervitae lascivus</i> reproduz-se com o auxílio de outro <i>Pigervitae lascivus</i> de sexo oposto, por um método chamado "reprodução sexuada" </p>
				<p>O excesso disso é o pecado da luxúria.</p>
			</section>
		</section>
		<section id="noite">
			<section class="texto">
				<p>Dormir é encerrar boa parte das atividades não-vitais para gerar energia.</p>
				<p> <i>Pigervitae lascivus</i> dorme à noite, mesmo não tendo gasto muita energia (nem à tarde)..." </p>
				<p>O excesso disso é o pecado da preguiça.</p>
			</section>
		</section>
	</body>
</html>
```

## Exercício 7

Repita o exercício anterior, mas agora centralize o "modal-content" com flexbox layout.

```html
<html>
	<head>
		<meta charset="utf-8">
		<title>Exercício 7</title>
		<style type="text/css">
			th {
				background-color: #000000;
				color: white;
			}
			th, td {
				font-size: 48px;
				height: 24%;
			}
			td:hover {
				background-color: gray;
				cursor: pointer;
			}
			#manha {
				display: flex;
				position: fixed;
				top: 0;
				left: 0;
				width: 100%;
				height: 100%;
				text-align: center;
				font-size: 32px;
				background-color: rgba(0,0,0,0.2)
			}
			#tarde, #noite {
				display: none;
			}
			.texto {
				margin: auto;
				width: 50%;
				height: 50%;
				background-color: yellow;
			}
		</style>
	</head>
	<body>
		<h1>Rotina de um <i>Pigervitae lascivus</i></h1>
		<table>
			<tr id="dias">
				<th></th>
				<th>Segunda</th>
				<th>Terça</th>
				<th>Quarta</th>
				<th>Quinta</th>
				<th>Sexta</th>
				<th>Sábado</th>
				<th>Domingo</th>
			</tr>
			<tr>
				<th>Manhã</th>
				<td>Comer</td>
				<td>Comer</td>
				<td>Comer</td>
				<td>Comer</td>
				<td>Comer</td>
				<td>Comer</td>
				<td>Comer</td>
			</tr>
			<tr>
				<th>Tarde</th>
				<td>Reproduzir</td>
				<td>Reproduzir</td>
				<td>Reproduzir</td>
				<td>Reproduzir</td>
				<td>Reproduzir</td>
				<td>Reproduzir</td>
				<td>Reproduzir</td>
			</tr>
			<tr>
				<th>Noite</th>
				<td>Dormir</td>
				<td>Dormir</td>
				<td>Dormir</td>
				<td>Dormir</td>
				<td>Dormir</td>
				<td>Dormir</td>
				<td>Dormir</td>
			</tr>
		</table>
		<section id="manha">
			<section class="texto">
				<p>"ao clicar em 'Comer'":</p>
				<p>Nutrir-se é obter os nutrientes necessários às atividades celulares.</p>
				<p> <i>Pigervitae lascivus</i> obtém-nos ao comer alimentos, ou seja, introduzir aglomerados de nutrientes através de um sistema (conjunto de órgãos) chamado "digestivo" </p>
				<p>O excesso disso é o pecado da gula.</p>
			</section>
		</section>
		<section id="tarde">
			<section class="texto">
				<p>Reproduzir-se é gerar algo semelhante a si.</p>
				<p> <i>Pigervitae lascivus</i> reproduz-se com o auxílio de outro <i>Pigervitae lascivus</i> de sexo oposto, por um método chamado "reprodução sexuada" </p>
				<p>O excesso disso é o pecado da luxúria.</p>
			</section>
		</section>
		<section id="noite">
			<section class="texto">
				<p>Dormir é encerrar boa parte das atividades não-vitais para gerar energia.</p>
				<p> <i>Pigervitae lascivus</i> dorme à noite, mesmo não tendo gasto muita energia (nem à tarde)..." </p>
				<p>O excesso disso é o pecado da preguiça.</p>
			</section>
		</section>
	</body>
</html>
```

## Exercício 8

Com a propriedade `float: left`, crie uma barra de navegação lateral. Olha a imagem abaixo de uma barra lateral. Não use flexbox ou grid layout para resolução desse exercício. Antes de começar, defina quais os itens de sua navbar, a cor e se ela vai ter um elemento de busca e uma logo como a mostrada na imagem abaixo.

![Exemplo de barra de navegação](../.github/exercise/navbar.png)

```html
<html>
	<head>
		<meta charset="utf-8">
		<title>Exercício 8</title>
		<!--Barra de navegação lateral não-funcional (exceto no ícone) com cor de fundo azul, que contém, da esquerda para a direita:
			ícone da home; botões de link a "Sobre", "Serviços" e "Contatos", respectivamente; mas sem área de pesquisa-->
		<style type="text/css">
			nav {
				border-width: 1px;
				border-color: lightblue;
				background-color: lightblue;
				height: 10vh;
			}
			button {
				border: none;
				background-color: inherit;
				color: darkblue;
				width: 15vw;
			}
			button:hover {
				background-color: rgba(0, 0, 0, 0.1);
				cursor: pointer;
				color: darkblue;
			}
			#icn, #sbr, #srv, #cnt {
				float: left;
				height: 6vh;
				padding: 10px;
			}
			#sbr, #srv, #cnt {
				position: relative;
				margin: 2vh 5vh;
				font-size: 24px;
			}
			img {
				height: 6vh;
				width: 6vh;
				margin: 1vh 1vh;
			}
		</style>
	</head>
	<body>
		<nav id="navbar">
			<a href="exerciceos-8.html" id="icn"> <img src="https://web.telegram.org/favicon.ico"> </a>
			<button id="sbr"> Sobre </button>
			<button id="srv"> Serviços </button>
			<button id="cnt"> Contatos </button>
		</nav>
	</body>
</html>
```

## Exercício 9

Faça o mesmo do exercício anterior, mas agora use flexbox layout para criar uma barra de navegação lateral.

```html
<html>
	<head>
		<meta charset="utf-8">
		<title>Exercício 9</title>
		<!--Barra de navegação lateral não-funcional (exceto no ícone) com cor de fundo azul, que contém, da esquerda para a direita:
			ícone da home; botões de link a "Sobre", "Serviços" e "Contatos", respectivamente; mas sem área de pesquisa-->
		<style type="text/css">
			nav {
				display: flex;
				border-width: 1px;
				border-color: lightblue;
				background-color: lightblue;
				height: 10vh;
			}
			button {
				border: none;
				background-color: inherit;
				color: darkblue;
				width: 15vw;
			}
			button:hover {
				background-color: rgba(0, 0, 0, 0.1);
				cursor: pointer;
				color: darkblue;
			}
			#icn, #sbr, #srv, #cnt {
				height: 6vh;
				padding: 10px;
			}
			#sbr, #srv, #cnt {
				position: relative;
				margin: 2vh 5vh;
				font-size: 24px;
			}
			img {
				height: 6vh;
				width: 6vh;
				margin: 1vh 1vh;
			}
		</style>
	</head>
	<body>
		<nav id="navbar">
			<a href="exerciceos-8.html" id="icn"> <img src="https://web.telegram.org/favicon.ico"> </a>
			<button id="sbr"> Sobre </button>
			<button id="srv"> Serviços </button>
			<button id="cnt"> Contatos </button>
		</nav>
	</body>
</html>
```

## Exercício 10

Com grid layout e flexbox, desenhe a bandeira do uruguai. Olhe a imagem abaixo:

![Bandeira do uruguai](../.github/exercise/uruguai.png)

A imagem do sol está na pasta `exercise10`. Busque não perder a resolução dessa imagem ao dimensionar as linhas e colunas.

```html
<html>
	<head>
		<meta charset="utf-8">
		<title>Exercício 10</title>
		<style type="text/css">
			body, #bandeira, #sol, #linhas_0, #linhas_1, #linhas_2, .wht, .blu {
				margin: 0 0;
				padding: 0 0;
			}
			#linhas_acima, #linhas_abaixo {
				display: flex;
				flex-direction: column;
			}
			#bandeira {
				display: grid;
				grid-template-columns: repeat(3, 1fr);
				grid-template-rows: repeat(8, 1fr);
				grid-gap: 0 0;
			}
			img {
				position: relative;
				margin: auto;
				padding: 5vh;
				height: 80%;
				width: 80%;
			}
			#sol {
				grid-column: 1 / 2;
				grid-row: 1 / 6;
				max-height: 62.5vh;
			}
			#linhas_acima {
				grid-column: 2 / 4;
				grid-row: 1 / 6;
				max-height: 62.5vh;
			}
			#linhas_abaixo {
				grid-column: 1 / 4;
				grid-row: 6 / 9;
				max-height: 37.5vh;
			}
			.wht {
				background-color: white;
				height: 12.5vh;
			}
			.blu {
				background-color: rgb(0, 56, 168);
				height: 12.5vh;
			}
		</style>
	</head>
	<body>
		<section id="bandeira">
			<section id="sol">
				<img src="https://github.com/ceos-jr/Capacitacao-CEOS-1-CSS/blob/master/exercise/exercise10/uruguai-sun.png?raw=true">
			</section>
			<section id="linhas_acima">
				<section class="wht"></section>
				<section class="blu"></section>
				<section class="wht"></section>
				<section class="blu"></section>
				<section class="wht"></section>
			</section>
			<section id="linhas_abaixo">
				<section class="blu"></section>
				<section class="wht"></section>
				<section class="blu"></section>
			</section>
		</section>
	</body>
</html>
```

## Exercício 11

Crie um footer com flexbox layout. Siga as seguintes especificações:

- O footer deve ter a logo da CEOS no primeiro flex item, o endereço da CEOS no segundo flex item e a logo da ufc no terceiro flex item.
- Quando a tela é menor ou igual a 1024px, a logo da ufc deve desaparecer.
- Quando a tela tiver 400px ou menos, a logo da ufc deve reaparecer e os elementos devem estar um abaixo do outro.

**Dica**: para fazer um elemento desaparecer no CSS, basta usar `display: none`.

As imagens da logo da CEOS e da UFC vão estar na pasta `exercise11`.

```html
<html>
	<head>
		<meta charset="utf-8">
		<title>Exercício 11</title>
		<style type="text/css">
			body {
				margin: 0;
				padding: 0;
			}
			footer {
				display: flex;
				flex-direction: row;
				flex-wrap: wrap;
				background-color: lightblue;
				height: 20vh;
				border-top: 1px solid black;
			}
			#ceos, #ufc {
				height: 15vh;
				width: 15vw;
				margin: 2.5vh 8vw;
			}
			#ende {
				height: 10vh;
				width: 10vw;
				margin: 2.5vh 8vw;
				font-size: 2vmin;
			}
			#ende > p {
				margin: 1vh 0;
			}
			@media screen and (max-width: 1024px) {
				#ufc {
					display: none;
				}
				#ceos, #ende {
					width: 25vw;
					font-size: 1.9vmax;
				}
				#ende {
					margin-top: 1vh;
				}
			}
			@media screen and (max-width: 400px) {
				footer {
					display: flex;
					flex-direction: column;
					width: 100vw;
					height: 55vh;
				}
				#ufc {
					display: inline-block;
					position: relative;
				}
				#ceos, #ufc {
					width: 30vw;
					height: 15vh;
					margin: 1vh 35vw;
				}
				#ende {
					align-items: center;
					width: 50vw;
					height: 10vh;
					margin: 2vh 25vw;
					font-size: 10px;
				}
			}
		</style>
	</head>
	<body>
		<footer>
			<a href="http://www.ceos.ufc.br/"> <img src="https://github.com/ceos-jr/Capacitacao-CEOS-1-CSS/blob/master/exercise/exercise11/ceos-logo-vertical.png?raw=true" id="ceos"> </a>
			<section id="ende">
				<p>Campus do Pici - Bloco 902 - Centro de Ciências</p>
				<p>Fortaleza - Ceará</p>
			</section>
			<a href="http://ufc.br/"> <img src="https://github.com/ceos-jr/Capacitacao-CEOS-1-CSS/blob/master/exercise/exercise11/ufc-logo-vertical-01.png?raw=true" id="ufc"> </a>
		</footer>
	</body>
</html>
```

## Exercício 12

Crie um header com flexboy layout. Siga as seguintes especificações:

- O header deve ter a logo da ceos horizontal e uma barra de navegação. Você pode definir os itens da barra de navegação.
- Quando a tela diminuir para 1024px, a barra de navegação se tornar um elemento com ícone de três barrinhas.
- As três barrinhas do ícone devem ser feitas apenas com CSS. Sem imagem.
- Não é preciso fazer a funcionalidade de ao clicar nas três barrinhas, faça aparecer o menu.

**Dica**: para fazer as três barrinhas, utilize os pseudoelementos `::before` e `::after`. Talvez definir tamanho e `display: block` possa ajudar. É de seu critério testar se isso resolve o seu problema ou não.

```html
<html>
	<head>
		<meta charset="utf-8">
		<title>Exercício 12</title>
		<style type="text/css">
			body {
				margin: 0;
				padding: 0;
			}
			header {
				display: flex;
				flex-direction: row;
				background-color: lightblue;
				height: 20vh;
				border-bottom: 1px solid black;
			}
			#barrinhas {
				display: none;
			}
			#logo {
				max-height: 15vh;
				max-width: 15vh;
				height: auto;
				width: auto;
				margin: 2.5vh 3vw;
			}
			button {
				border: none;
				background-color: inherit;
				color: darkblue;
				width: 20vw;
				height: 10vh;
				margin: 5vh 3vw;
				font-size: 1.8vmax;
			}
			button:hover {
				background-color: rgba(0, 0, 0, 0.2);
				color: white;
				cursor: pointer;
			}
			@media screen and (max-width: 1024px) {
				#logo, button {
					display: none;
				}
				#barrinhas {
					display: inline-block;
					position: relative;
					width: 10vmax;
					height: 15vh;
					margin: 2.5vh 0 0 2vw;
					padding: 0;
				}
				#barrinhas:hover {
					background-color: rgba(0, 0, 0, 0.2);
					cursor: pointer;
				}
				p {
					background-color: rgba(0, 0, 0, 0.4);
					border-radius: 50px;
					width: 10vmax;
					height: 3.5vh;
					margin: 1vh 0;
				}
			}
		</style>
	</head>
	<body>
		<header>
			<section id="barrinhas">
				<p></p> <p></p> <p></p>
			</section>
			<img src="https://github.com/ceos-jr/Capacitacao-CEOS-1-CSS/blob/master/exercise/exercise11/ceos-logo-vertical.png?raw=true" id="logo">
			<button id="sobre"> A CEOS </button>
			<button id="servicos"> Nossos Serviços </button>
			<button id="contato"> Contato </button>
		</header>
	</body>
</html>
```

## Exercício 13

Crie um conteúdo principal com a imagem da CEOS que se encontra no google maps. Adicione um pequeno texto dizendo o que é a CEOS para você. Estilize da forma que você achar melhor.

```html
<html>
	<head>
		<meta charset="utf-8">
		<title>Exercício 13</title>
		<style type="text/css">
			body {
				margin: 0;
				padding: 0;
			}
			#main {
				display: flex;
				background-color: lightblue;
				height: 60vh;
				width: 60vw;
			}
			#main > img {
				position: relative;
				max-height: 50vh;
				max-width: 20vw;
				height: auto;
				width: auto;
				margin: 5vh 5vw;
			}
			#descricao {
				margin: 5vmin;
				padding: 10vmin;
				font-size: 2.5vmin;
			}
			@media screen and (max-width: 1024px) {
				#main {
					display: flex;
					flex-direction: column;
					width: 100vw;
					height: 160vh;
				}
			}
		</style>
	</head>
	<body>
		<section id="main">
			<img src="https://lh5.googleusercontent.com/p/AF1QipOCvEGXa8GGE8daRvWdcIZyj6ePpCkG1iXo9LRp=w408-h544-k-no" id="frente">
			<p id="descricao">
				A Ceos é uma Empresa Júnior do curso de Ciência da Computação da Universidade Federal do Ceará (campus Fortaleza). Só tem gente (e gata) top lá. No further additions.
			</p>
		</section>
	</body>
</html>
```

## Exercício 14

Crie um conteúdo lateral com os links das redes sociais da CEOS.

```html
<html>
	<head>
		<meta charset="utf-8">
		<title>Exercício 14</title>
		<style type="text/css">
			body, aside {
				margin: 0;
				padding: 0;
			}
			aside {
				background-color: lightblue;
				max-height: 60vh;
				max-width: 40vw;
				float: right;
				border-left: 1px solid black;
			}
			h1 {
				margin: 5vmin;
				font-size: 3vmin;
			}
			.social {
				margin: 8vmin;
				font-size: 2.5vmin;
			}
			#facebook{
				background-color: darkblue;
				color: white;
			}
			#twitter{
				background-color: lightblue;
				color: darkblue;
			}
		</style>
	</head>
	<body>
		<aside>
			<h1>Visite nossas redes sociais!</h1>
			<ul>
				<li class="social"> Facebook: <a id="facebook" href="https://pt-br.facebook.com/ceos.jr/"> @ceos.jr </a> </li>
				<li class="social"> Twitter: <a id="twitter" href="https://twitter.com/ceos_jr?lang=pt"> @ceos_jr </a> </li>
			</ul>
		</aside>
	</body>
</html>
```

## Exercício 15

Pegue o html e css feito nos exercícios 11, 12, 13, 14 e utilizando grid layout posicione-os de forma que fique como a imagem abaixo no mesmo documento.

![Template](../.github/part-four/template.png)

Quando a tela for menor ou igual a 1024px, faça desaparecer o conteúdo lateral.

```html
<html>
	<head>
		<meta charset="utf-8">
		<title>Exercício 15</title>
		<style type="text/css">
			body {
				display: grid;
				grid-template-rows: repeat(5, 1fr);
				grid-template-columns: repeat(5, 1fr);
				margin: 0;
				padding: 0;
				background-color: lightblue;
				overflow: hidden;
			}
			
			header {
				grid-row: 1 / 2;
				grid-column: 1 / 6;
				display: flex;
				flex-direction: row;
				background-color: inherit;
				border-bottom: 1px solid black;
			}
			#barrinhas {
				display: none;
			}
			#logo {
				max-height: 15vh;
				max-width: 15vh;
				height: auto;
				width: auto;
				margin: 2.5vh 3vw;
			}
			button {
				border: none;
				background-color: transparent;
				color: darkblue;
				width: 20vw;
				height: 10vh;
				margin: 5vh 3vw;
				font-size: 1.8vmax;
			}
			button:hover {
				background-color: rgba(0, 0, 0, 0.2);
				color: white;
				cursor: pointer;
			}

			#main {
				grid-row: 2 / 5;
				grid-column: 1 / 4;
				display: flex;
				background-color: inherit;
			}
			#main > img {
				position: relative;
				max-height: 50vh;
				max-width: 20vw;
				height: auto;
				width: auto;
				margin: 5vh 5vw;
			}
			#descricao {
				margin: 5vmin;
				padding: 10vmin;
				font-size: 2.5vmin;
			}

			aside {
				grid-row: 2 / 5;
				grid-column: 4 / 6;
				background-color: inherit;
				border-left: 1px solid black;
			}
			h1 {
				margin: 5vmin;
				font-size: 3vmin;
			}
			.social {
				margin: 8vmin;
				font-size: 2.5vmin;
			}
			#facebook{
				background-color: darkblue;
				color: white;
			}
			#twitter{
				background-color: lightblue;
				color: darkblue;
			}

			footer {
				grid-row: 5 / 6;
				grid-column: 1 / 6;
				display: flex;
				flex-direction: row;
				flex-wrap: wrap;
				background-color: inherit;
				border-top: 1px solid black;
			}
			#ceos, #ufc {
				height: 15vh;
				width: 15vw;
				margin: 2.5vh 8vw;
			}
			#ende {
				height: 10vh;
				width: 10vw;
				margin: 2.5vh 8vw;
				font-size: 2vmin;
			}
			#ende > p {
				margin: 1vh 0;
			}

			@media screen and (max-width: 1024px) {
				body {
					display: flex;
					flex-direction: column;
				}
				#logo, header > button {
					display: none;
				}
				#barrinhas {
					display: inline-block;
					position: relative;
					width: 10vmax;
					height: 15vh;
					margin: 2.5vh 0 0 2vw;
					padding: 0;
				}
				#barrinhas:hover {
					background-color: rgba(0, 0, 0, 0.2);
					cursor: pointer;
				}
				#barrinhas > p {
					background-color: rgba(0, 0, 0, 0.4);
					border-radius: 50px;
					width: 10vmax;
					height: 3.5vh;
					margin: 1vh 0;
				}
				#main {
					display: flex;
					flex-direction: column;
					width: 100vw;
					height: 80vh;
				}
				#main > img {
					max-height: 30vh;
					max-width: 60vw;
					height: auto;
					width: auto;
					margin: 10vh 20vw 0 20vw;
				}
				#descricao {
					margin: 1vh 20vw;
				}
				aside {
					display: none;
				}
				#ufc {
					display: none;
				}
				#ceos, #ende {
					width: 25vw;
					font-size: 1.9vmax;
				}
				#ende {
					margin-top: 5vh;
				}
			}
			@media screen and (max-width: 400px) {
				#descricao {
					font-size: 2.5vmax;
				}
				footer {
					display: flex;
					flex-direction: column;
					width: 100vw;
					height: 55vh;
				}
				#ufc {
					display: inline-block;
					position: relative;
				}
				#ceos, #ufc {
					width: 30vw;
					height: 15vh;
					margin: 1vh 35vw;
				}
				#ende {
					align-items: center;
					width: 50vw;
					height: 10vh;
					margin: 2vh 25vw;
					font-size: 2.5vmax;
				}
			}
		</style>
	</head>
	<body>
		<header>
			<section id="barrinhas">
				<p></p> <p></p> <p></p>
			</section>
			<img src="https://github.com/ceos-jr/Capacitacao-CEOS-1-CSS/blob/master/exercise/exercise11/ceos-logo-vertical.png?raw=true" id="logo">
			<button id="sobre"> A CEOS </button>
			<button id="servicos"> Nossos Serviços </button>
			<button id="contato"> Contato </button>
		</header>
		<section id="main">
			<img src="https://lh5.googleusercontent.com/p/AF1QipOCvEGXa8GGE8daRvWdcIZyj6ePpCkG1iXo9LRp=w408-h544-k-no" id="frente">
			<p id="descricao">
				A Ceos é uma Empresa Júnior do curso de Ciência da Computação da Universidade Federal do Ceará (campus Fortaleza). Só tem gente (e gata) top lá. No further additions.
			</p>
		</section>
		<aside>
			<h1>Visite nossas redes sociais!</h1>
			<ul>
				<li class="social"> Facebook: <a id="facebook" href="https://pt-br.facebook.com/ceos.jr/"> @ceos.jr </a> </li>
				<li class="social"> Twitter: <a id="twitter" href="https://twitter.com/ceos_jr?lang=pt"> @ceos_jr </a> </li>
			</ul>
		</aside>
		<footer>
			<a href="http://www.ceos.ufc.br/"> <img src="https://github.com/ceos-jr/Capacitacao-CEOS-1-CSS/blob/master/exercise/exercise11/ceos-logo-vertical.png?raw=true" id="ceos"> </a>
			<section id="ende">
				<p>Campus do Pici - Bloco 902 - Centro de Ciências</p>
				<p>Fortaleza - Ceará</p>
			</section>
			<a href="http://ufc.br/"> <img src="https://github.com/ceos-jr/Capacitacao-CEOS-1-CSS/blob/master/exercise/exercise11/ufc-logo-vertical-01.png?raw=true" id="ufc"> </a>
		</footer>
	</body>
</html>
```