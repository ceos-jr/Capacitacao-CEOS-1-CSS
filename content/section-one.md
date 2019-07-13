# Seletores, Cascata, Especificidade e Herança

Antes de começarmos a falar dos temas desse módulo, precisamos explicar alguns conceitos para então facilitar a compreensão do conteúdo. Observe o html abaixo.

```html
<!DOCTYPE html>
<html lang="pt-br">
	<head>
		<meta charset="utf-8" />
	</head>

	<body>
		<h1>Meu HTML</h1>
		<p>Lorem ipsum dolor!</p>
	</body>
</html>
```

Quando o navegador recebe esse arquivo, ele realiza a análise de cima para baixo. Ou seja, ele começa analisando a linha que possui ```<!DOCTYPE html>```, depois ```<html>``` e assim sucessivamente. A partir disso, ele constrói uma estrutura hierárquica que chamamos de **árvore do documento**. Graficamente, podemos representar o HTML mostrado acima da seguinte forma:

<p align="center">
	<img alt="Árvore do Documento" src="https://github.com/ceos-jr/Capacitacao-CEOS-1-CSS/raw/master/.github/part-one/doc-tree.png">
</p>

Algumas palavras são utilizadas para definir a relação de parentesco dos elementos. Elas são:

**Elemento descendente**: um elemento A é descendente de B, se A está contido em B em qualquer nível de aninhamento;

**Elemento ancestral**: um elemento A é ancestral de B, se B está contido em A em qualquer nível de aninhamento;

**Elemento pai**: um elemento A é pai de B, se B está imediatamente contido em A;

**Elemento filho**: um elemento A é filho de B, se ele está imediatamente contido em B;

**Elemento irmão**: um elemento A é irmão de B, se eles estão contidos no mesmo elemento pai;

**Elemento precedente**: um elemento A é precedente de B, se A é ancestral de B. O elemento A também é precedente, caso ele seja um irmão de B e declarado anterior a B;

**Elemento subsequente**: um elemento A é subsequente de B, se ele é descendente de A ou vem após B na marcação HTML;

Logo, todo HTML escrito por nós terá uma representação como mostrado na imagem acima. Mas porque isso é útil para o nosso aprendizado em CSS? É agora que entra outro conceito muito importante.

Como devemos saber, o CSS é uma folha de estilo em cascata. Ele possui várias regras de estilo para fazer nossas páginas mais [alegres e bonitas](https://www.facebook.com/MachuPicchuWeeb/videos/188176511794188/). Tudo bem, mas o que é uma regra de estilo? Por definição, é a menor unidade de código de um CSS. Veja abaixo uma regra de estilo CSS:

```css
h1 {
	text-align: center;
}
```

Observe que uma regra de estilo é composta por um **seletor** e um ou mais **par propriedade/valor**. Certo, sabemos agora o básico. Isso é um grande passo, mas será que ficou claro o que é um seletor e um par propriedade/valor? Então vamos entender o que são esses termos de uma vez por todas.

**Seletor**: é um padrão que casa com um elemento da árvore do documento;

**Par propriedade/valor**: é a definição de uma determinada característica com algum valor CSS válido. Também podemos chamá-lo de propriedade;

Assim, seletores são úteis a pegar um elemento da árvore do documento e aplicar ou alterar características deles. Então, você pode pegar um texto e colocar o tamanho da fonte bem grande ou mudar a cor de fundo de um elemento como mostra o código CSS abaixo:

```css
p {
	font-size: 100px;
}

section {
	background-color: blue;
	/* Caso você queira ver no seu navegador, defina esses dois par propriedade/valor */
	width: 100px;
	height: 100px;
}
```

Nesse código, selecionamos um elemento pelo seu tipo. Ou seja, pegamos os elementos do tipo `p`, enquanto no código seguinte pegamos os elementos do tipo `section`. Mas o CSS3 prevê mais de 42 seletores para selecionar o seu elemento na árvore do documento. Assim não precisamos pegar um elemento apenas pelo seu tipo, mas também pelos seus atributos, classes, id's e pseudoclasses.

**Observação**: classes e id's são também atributos, mas existe uma forma específica de seletor para eles. Por isso que no texto acima, foram abordados como se fossem diferentes de atributos.

## Seletores

"Mais de 42 seletores? Isso é muitoo!" pode ser a primeira coisa que vem em sua cabeça. De fato, é muita coisa, mas não precisamos aprender todos. O objetivo aqui é saber alguns tipos de seletores para você decidir qual melhor atende a resolução de seu problema. Então vamos lá:

**Seletor universal**: aquele que representa a seleção de todos os elementos renderizados do arquivo;

```css
* {
	margin: 0;
	padding: 0;
}
```

**Seletores de tipo**: aqueles que selecionam pelo tipo na representação do documento. No código abaixo, será estilizado todo elemento do tipo `body`;

```css
body {
	margin: 0;
	padding: 0;
}
```

**Seletores de atributo**: aqueles que selecionam baseado em um atributo especificado no elemento;

```css
input[required] {
	border: 1px solid black;
}

input[type="text"] {
	text-align: center;
}

p[class="my-paragraph"] {
	font-size: 18px;
}
```

A tabela abaixo tem os seletores de atributo. Busque testar cada um e tirar suas próprias conclusões de como funcionam.

| Seletor | descrição |
| ------- | --------- |
| A[att]  | Seleciona o elemento A, que tem o atributo att | 
| A[att\|="val"] | Seleciona o elemento A, que tem um atributo att, cujo valor é val ou começa com val. |
| A[att~="val"] | Seleciona o elemento A, no qual foi definido o valor val ao atributo att. |
| A[att^="val"] | Seleciona o elemento A, cujo atributo att comece com o valor val. |
| A[att$="val"] | Seleciona o elemento A, cujo atributo att termine com o valor val. |

**Seletor id**: aquele que seleciona baseado no valor do atributo `id` definido ao elemento;

```css
#my-title {
	color: red;
}
```

**Seletor class**: aquele que seleciona baseado no valor do atributo class definido ao elemento;

```css
.my-paragraph {
	font-size: 18px;
}
```

**Seletor pseudoclasse**: seleciona elementos baseados em informações que não constam na árvore do documento;

```css
.btn:hover {
	background-color: green;
}
```

O código acima diz que a cor do elemento de classe `.btn` vai ter cor verde quando for passado o mouse por cima dele.

A tabela abaixo mostra alguns do seletores pseudoclasses. Busque testar cada um e tirar suas próprias conclusões.

| Seletor  | Descrição |
| -------  | --------- |
| :link    | Seleciona um elemento `a` não clicado. |
| :visited | Seleciona um elemento `a` clicado. |
| A:hover  | Aplica uma estilização no elemento A, quando o ponteiro está sobre ele. |
| A:active | Aplica uma estilização enquanto o elemento estiver ativado. Ou seja, quando o elemento estiver sendo pressionado pelo botão do mouse. |
| A:focus  | Seleciona um elemento A, que tenha sido colocado em foco. |
| :root    | Seleciona o elemento raiz do documento. |
| A:empty  | Seleciona o elemento A, que esteja vazio(sem texto ou nó filho). |
| A:target | Seleciona o elemento A, desde que ele seja o destino de um link interno da página. |
| A:checked | Seleciona o elemento A, que esteja selecionado. É usado, normalmente, para controle de formulários em elementos `radio` e `checkbox`. |

Além desses demonstrados na tabela, existem os seletores pseudoclasses de seleção por posição. Eles podem ser úteis quando você quer manter o número de classes e id's ao mínimo possível a evitar conflito de nomes. Alguns desses seletores recebem um parâmetro a identificar que elemento deve ser selecionado. Observe o código abaixo:

```css
section p:nth-child(even) {
	background-color: red;
	/* Definido o tamanho para pordemos visualizar caso busquemos testar */
	width: 200px;
	height: 200px;
}
```

Veja que entre os parênteses, nós passamos o valor `even`. Isso significa que essa regra CSS vai selecionar todos os `p` filhos de section que estão em ordem par no documento. Veja o html abaixo:

```html
<section>
	<p></p>
	<p></p> <!-- Esse elemento vai ter cor de fundo vermelha -->
	<p></p>
	<p></p> <!-- Esse elemento vai ter cor de fundo vermelha -->
</section>

```

Existem 3 tipos de valores que podemos passar aos seletores do tipo `nth-*`.

1. Um número inteiro positivo.
2. O valor odd(ímpar) ou even(par).
3. A função an + b, cujos valores a e b podem ser um número inteiro positivo ou negativo.

Segue abaixo a tabela de seletores do tipo `nth-*`.

| Seletor | Descrição |
| ------- | --------- |
| A B:nth-child(pos) | Seleciona todos os irmãos de B, que são filhos de A, que seguem o valor passado em `pos` na ordem de declaração do início ao fim. |
| A B:nth-last-child(pos) | Seleciona todos os irmãos de B, que são filhos de A, os quais seguem o valor passado em `pos`, em ordem, do fim ao início. |
| A B:nth-of-type(pos) | Seleciona todos os irmãos de B do mesmo tipo na árvore do documento que são filhos de A, seguindo o valor de `pos`. |
| A B:nth-last-of-type(pos) | Seleciona todos os irmão de B do mesmo tipo na árvore do documento que são filhos de A, seguindo o valor de `pos`, em ordem, do fim da declaração ao início. |

**Observação**: passando uma função do tipo `an+b` para os seletores pseudoclasse do tipo `nth-*`, podemos ter valores de retorno no conjunto dos números inteiros negativos. Eles serão ignorados, já que não existe um elemento n que esteja em uma posição negativa na sequência de elementos. Por exemplo:

```css
section p:nth-child(2n-4) {
	background-color: black;
	/* Definido o tamanho para pordemos visualizar caso busquemos testar */
	width: 200px;
	height: 200px;
}
```

Agora, calculando os valores de `2n-4`, cujo n pertence ao conjunto dos números inteiros de 0 a 7, temos:

```markdown

para n = 0:
2x0 - 4 = -4

para n = 1:
2x1 - 4 = -2

para n = 2:
2x2 - 4 = 0

para n = 3:
2x3 - 4 = 2

para n = 4:
2x4 - 4 = 4

para n = 5:
2x5 - 4 = 6

para n = 6:
2x6 - 4 = 8

para n = 7:
2x7 - 4 = 10

```

Observe que para n igual a 0 e 1, temos valores negativos. Esses valores serão ignorados. Logo, selecionamos os elementos irmãos de `p`, filhos de `section` na posição 2, 4, 6, 8 e 10, cujo n é 3, 4, 5, 6 e 7, respectivamente.

```html
<section>
	<p></p>
	<p></p> <!-- Esse elemento vai ter cor de fundo preta -->
	<p></p>
	<p></p> <!-- Esse elemento vai ter cor de fundo preta -->
	<p></p>
	<p></p> <!-- Esse elemento vai ter cor de fundo preta -->
	<p></p>
	<p></p> <!-- Esse elemento vai ter cor de fundo preta -->
	<p></p>
	<p></p> <!-- Esse elemento vai ter cor de fundo preta -->
</section>
```

Existem também seletores pseudoclasse do tipo `nth-*` que não precisam receber um argumento. Eles são:

| Seletor | Descrição |
| ------- | --------- |
| A B:first-child | Seleciona B, primeiro filho de A. |
| A B:last-child  | Selciona B, último filho de A. |
| A B:first-of-type | Seleciona B, primeiro filho de A, que seja do tipo B. |
| A B:last-of-type | Seleciona B, último filho de A, que seja do tipo B. |
| A B:only-child | Seleciona B, desde que seja filho único de A |
| A B:only-of-type | Seleciona B, desde que seja o único filho de A, do tipo B |

**Seletores pseudoelemento**: são seletores que pegam partes do documento, que não constam na árvore do documento. Bem semelhante à pseudoclasse, a diferença desses seletores está no fato de criar abstrações não definidas na linguagem de marcação e na sua sintaxe de `::`. Segue abaixo uma tabela com alguns seletores pseudoelemento.

| Seletor | Descrição |
| ------- | --------- |
| A::first-letter | Seleciona o primeiro caractere da primeira linha do elemento A. Caso exista qualquer outro conteúdo antes do texto, não será selecionado nada. |
| A::first-line | Seleciona a primeira linha do elemento A. A linha varia de acordo com o tamanho do navegador e do tamanho de A. |

Além desses dois, existem os seletores pseudoelemento `::before` e `::after`, que são usados para definir conteúdo antes e depois, respectivamente, do elemento. Nesses seletores podemos definir o conteúdo com a propriedade `content`. **Esse conteúdo não faz parte da árvore do documento**.

```html
<p>É muito</p>
```

```css
p::before {
	content: "Arnaldo";
}

p::after {
	content: "Inteligente!";
}
```


Valor renderizado:
```Arnaldo é muito Inteligente!```

Foram dados exemplos durante todo esse módulo apenas da seleção de um elemento, mas podemos, perfeitamente, aplicar uma mesma característica a elementos em uma única regra de estilo. Observe abaixo:

```css
header, footer {
	backgroud-color: blue;
}
```

Nesse código, estamos definindo a cor de fundo do `header` e do `footer` de azul. Podemos também utilizar os caracteres de combinação para selecionarmos elementos na árvore do documento. Os caracteres de combinação são:

| Caractere | Descrição |
| --------- | --------- |
| A B   | Elemento B, descendente de A |
| A > B | Elemento B, filho de A |
| A + B | Elemento B, imediatamente após A(A e B devem ser irmãos) |
| A ~ B | Elemento B, após A(A e B devem ser irmãos) |

**Observação**: Foi utilizado muito a expressão *seletor pseudoclasse do tipo `nth-*`*. Essa expressão não diz que existe um subtipo dentro dos seletores pseudoclasse. Foi apenas uma convenção que eu, autor, adotei para explicar seletores que tenham `nth` no início de sua escrita.

## Cascata

Uma folha estilo pode vir de três origens diferentes. Elas podem ser:

- **Autor**: é a folha de estilo criada pelo autor e segue, normalmente, uma tela projetada chamada de mockup, criada pelo design ou desenvolvedor;

- **Usuário**: é a folha de estilo criada pelo usuário que utiliza a aplicação. Normalmente, o agente do usuário permite isso para propor uma folha de estilo diferente a pessoas com alguma deficiência.

- **Agente de usuário**: é a folha de estilo fornecida pelas plataformas(normalmente, os navegadores). Elas definem os valores padrões às propriedades CSS.

Veja, por padrão, que existe uma folha de estilo do agente de usuário. Porém, quando escrevemos uma folha de estilo e a linkamos em nosso HTML, ela aplica o estilo que foi escrito por você, autor da folha. Conclui-se que as regras de estilo, contidas em nossas folhas de estilo, sobrepõem-se a outras, numa situação em que elas se encontram no mesmo arquivo ou não. **Esse comportamento é conhecido como efeito cascata** e existe uma ordem que decide qual regra de estilo será aplicada àquele elemento. O cálculo feito segue o seguinte padrão:

1. Encontrar a cada tipo de mídia as regras de estilo que se aplicam àquele elemento.
2. Classificar em ordem de precedência pelo valor de importância(normal e `!important`) e a origem(autor, usuário e agente do usuário)
	- Declarações do agente de usuário
	- Declarações normais do usuário
	- Declarações normais do autor
	- Declarações importantes do autor
	- Declarações importantes do usuário
3. Classificar as regras de mesmo peso pela sua especificidade(vamos entender o que é isso na próxima seção). Ou seja, seletores mais específicos têm maior precedência em relação aos menos específicos.
4. Classificar, observando a posição que ocupam no documento. Por exemplo, sejam 1 e 2 duas regras de estilo que mudam a propriedade `background-color` a um mesmo elemento. Suponha que 2 está escrito abaixo de 1, em se tratando de linhas. Logo, 2 terá mais precedência que 1. Caso 1 esteja escrito abaixo de 2, 1 terá precedência com relação a 2.

## Especificidade

Seja `p`, filho de uma `section` arbitrária, podemos declarar o tamanho da fonte de `p` da seguinte forma:

1. `p { font-size: 20px }`
2. `section p { font-size: 20px }`
3. `body section p { font-size: 20px }`
4. `section > p { font-size: 20px }`

Observe que para o seletor de uma regra de estilo, temos diferentes formas de selecionar o mesmo elemento. **Especificidade é justamente a caracteristica que leva em consideração como o autor escreveu o seletor**.

Agora, suponha que foram escritos os quatro itens acima em uma mesma folha de estilo e todas têm o valor de importância normal. O próximo item ao critério de desempate é a especificidade do seletor. Então, qual regra será aplicada, baseada no critério de especificidade? Devemos realizar um cálculo.

Baseado em como o seletor foi escrito, formamos um número em que `a` é o primeiro dígito, `b` é o segundo dígito, `c` é o terceiro dígito e `d` é o quarto dígito. Logo, teremos o algarismo `abcd`, em que o maior entre eles, possui a maior precedência. Existindo empate, é aplicado o item 4 do efeito cascata.

Para formar esse número, seguimos o seguinte passo:

1. Caso a regra seja inline, ou seja, escrita em um atributo `style`, o valor de `a` é 1, Caso contrário, `a` é 0;
2. O valor de `b` é o número de vezes que o atributo `id`(sinal #) aparece no seletor;
3. O valor de `c` é o número de vezes que outros atributos diferentes de `id` ou seletores pseudoclasse aparecem no seletor;
4. O Valor de `d` é o número de vezes que nomes de elementos e pseudoelementos aparecem no seletor;

Portanto, para as seguintes regras declaradas, temos `abcd` como:

1. `p { font-size: 20px } /* a=0; b=0; c=0; d=1; abcd=0001 */`
2. `section p { font-size: 20px } /* a=0; b=0; c=0; d=2; abcd=0002 */`
3. `body section p { font-size: 20px } /* a=0; b=0; c=0; d=3; abcd=0003 */`
4. `section > p { font-size: 20px } /* a=0; b=0; c=0; d=2; abcd=0002 */`

## Herança

Como filho de seus pais, você deve ter herdado algumas características deles. Seja cor do cabelo ou formato dos olhos. No CSS, é observado o mesmo tipo de comportamento, mas assim como a gente não herda tudo de nossos pais, elementos descendentes de outros também não herdam tudo. Esse mecanismo é conhecido, obviamente, como herança e com ele vem um valor que pode ser passado para quase todas as propriedades que é o `inherit`. Veja o código abaixo:

```html
<section>
	<p>Some text here!</p>
</section>
```

```css
section {
	color: green;
	border: 1px solid black;
}
```

Nesse exemplo, `p` herda a cor de `section`, mas não herda a borda de `section`. Logo, existem propriedades que os descendentes de um elemento herdam e outras que eles não podem herdar sem a utilização da palavra-chave `inherit`.
