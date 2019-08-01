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

1. `<meta charset="utf-8" />` é Filho de `<head></head>`.
2. `<li>Configuração</li>` é descendente de `<nav></nav>`.
3. `<li>Perfil</li>` é Irmão de `<li>Configuração</li>`.
4. `<li>Perfil</li>` é subsequente de <li>Início</li>.
5. `<main></main>` é filho de <body></body>.
6. `<footer></footer>` é irmão de <header></header>.
7. `<h1>Meu produto</h1>` é precedente de <p>Algum texto sobre o meu produto</p>.
8. `<p>Algum texto sobre o meu produto</p>` é Descendente de `<html></html>`..
9. `<ul></ul>` é Pai de `<li></li>`.
10. `<head></head>` é irmão de `<body></body>`.

## Exercício 2

Para os seletores abaixo, diga qual o tipo dele.

1. `body { ... }`. Selotor de tipo
2. `li:hover { ... }`. Seletor de pseudoclasse
3. `p::before { ... }`. Seletor de pseudoelemento
4. `body ul li { ... }`. Seletor de especificidade/descendente
5. `.section-item { ... }`. Seletor de Classe
6. `section[class^="section-item"] { ... }`. Seletor de atributo 

## Exercício 3

Dado os seletores abaixo, forme o número de especificidade.

1. `body ul li { ... }`. a=0; b=0; c=0; d=3; abcd=0003
2. `.section-item > p`. a=0; b=0; c=1; d=1; abcd=0011
3. `head + body { ... }`. a=0; b=0; c=0; d=2; abcd=0002
4. `#section-father ul li::before { ... }`.a=0; b=1; c=0; d=2; abcd=0102
5. `section ul li:hover { ... }`. a=0; b=0; c=1; d=2; abcd=0012

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
	#navbar ul { ... } . especificidade -  0101 - essa regra se aplica
	nav ul { ... } . especificidade - 0004
	header nav ul { ... } especificidade - 0003
```

2.
```css
	nav ul li { ... } especificidade - 0003
	header nav ul li { ... } especificidade - 0004
	.navbar-item { ... } especificidade - 0010 - essa regra se aplica
```

3.
```css
	nav ul .navbar-item { ... } especificidade - 0012
	.navbar-item { ... } especificidade - 0010
	nav[id="navbar"] ul li { ... } especificidade - 0012 - esta regra se aplica
```

## Exercício 5

Em alguns sites nós temos um botão redondo com uma seta para cima que ao ser clicado, a tela volta para o início do site. Normalmente ele fica no canto inferior direito da tela. Crie um botão dessa forma e posicione-o nesse mesmo canto. Não é preciso realizar a funcionalidade de voltar para o início da tela. Deixe um espaçamento curto entre o botão e o fim da tela tanto no lado direito como na parte inferior.

Site para ícone: [link](https://www.flaticon.com/)
Regra para arrendodamento de um elemento: `border-radius: 50%`.

## Exercício 6

Um modal é um bloco que abre ao você clicar em algum elemento da tela principal. Crie um modal apenas com regras estilo de posicionamento. Não use flexbox ou grid layout. Veja a imagem abaixo para entender melhor o que é um modal.

![modal site do include 2019](../.github/exercise/modal.png)

**Dica**: Para fazer um fundo transparente, utilize a regra `background-color: rgba(0,0,0,0.2)`. Busque saber a lógica por trás da montagem de um modal antes de começar. Por exemplo, o modal deve ficar acima de todo o conteúdo principal no eixo z. Também não fica nem abaixo, nem acima.


## Exercício 7

Repita o exercício anterior, mas agora centralize o "modal-content" com flexbox layout.

## Exercício 8

Com a propriedade `float: left`, crie uma barra de navegação lateral. Olha a imagem abaixo de uma barra lateral. Não use flexbox ou grid layout para resolução desse exercício. Antes de começar, defina quais os itens de sua navbar, a cor e se ela vai ter um elemento de busca e uma logo como a mostrada na imagem abaixo.

![Exemplo de barra de navegação](../.github/exercise/navbar.png)

## Exercício 9

Faça o mesmo do exercício anterior, mas agora use flexbox layout para criar uma barra de navegação lateral.

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

## Exercício 12

Crie um header com flexboy layout. Siga as seguintes especificações:

- O header deve ter a logo da ceos horizontal e uma barra de navegação. Você pode definir os itens da barra de navegação.
- Quando a tela diminuir para 1024px, a barra de navegação se tornar um elemento com ícone de três barrinhas.
- As três barrinhas do ícone devem ser feitas apenas com CSS. Sem imagem.
- Não é preciso fazer a funcionalidade de ao clicar nas três barrinhas, faça aparecer o menu.

**Dica**: para fazer as três barrinhas, utilize os pseudoelementos `::before` e `::after`. Talvez definir tamanho e `display: block` possa ajudar. É de seu critério testar se isso resolve o seu problema ou não.

## Exercício 13

Crie um conteúdo principal com a imagem da CEOS que se encontra no google maps. Adicione um pequeno texto dizendo o que é a CEOS para você. Estilize da forma que você achar melhor.

## Exercício 14

Crie um conteúdo lateral com os links das redes sociais da CEOS.

## Exercício 15

Pegue o html e css feito nos exercícios 11, 12, 13, 14 e utilizando grid layout posicione-os de forma que fique como a imagem abaixo no mesmo documento.

![Template](../.github/part-four/template.png)

Quando a tela for menor ou igual a 1024px, faça desaparecer o conteúdo lateral.

## Exercício 16

[Dogs](https://dog.ceo/dog-api/) é uma API que retorna imagens de cachorros. Construa um pequeno instagram consumindo essa API. Para estilização, use `flexbox layout`. Para fazer uma requisição, utilize [fetch API](https://developer.mozilla.org/pt-BR/docs/Web/API/Fetch_API/Using_Fetch). Siga a lista abaixo para cumprir o exercício.

- Crie o mockup da página e salve em formato pdf.
- Crie um repositório no github e comece o projeto.
- Adicione os mockups em uma pasta do repositório chamada `mockups`.
- Ao terminar, coloque o link do repositório em um comentário na issue 16.
