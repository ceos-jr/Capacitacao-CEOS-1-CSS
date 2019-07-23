Dado o html abaixo, analise os itens com css e diga qual regra se aplica não levando em consideração a ordem na folha de estilo, ou seja, ignorando o 4 item do cálculo do efeito cascata.

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

                                       abcd
1.
	#navbar ul { ... }---------------> 0101 --> essa regra é aplica
	nav ul { ... }-------------------> 0002
	header nav ul { ... }------------> 0003


2.
	nav ul li { ... }----------------> 0003
	header nav ul li { ... }---------> 0004
	.navbar-item { ... }-------------> 0010 --> essa regra é aplica


3.
	nav ul .navbar-item { ... }------> 0012
	.navbar-item { ... }-------------> 0010 
	nav[id="navbar"] ul li { ... }---> 0102 --> essa regra é aplica