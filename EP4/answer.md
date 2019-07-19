1. 
```css
	#navbar ul { abcd = 0101 }
	nav ul { abcd = 0002 }
	header nav ul { abcd = 0003 }
```
header nav ul possui a maior precedência pelo algarismo abcd.

2.
```css
	nav ul li { abcd = 0003 }
	header nav ul li { abcd = 0004 }
	.navbar-item { abd = 0010 }
```
.navbar-item possui a maior precedência pelo algarismo abcd.

3.
```css
	nav ul .navbar-item { abcd = 0012 }
	.navbar-item { abcd = 0010 }
	nav[id="navbar"] ul li { abcd = 0012 }
```
nav ul.navbar-item e nav[id="navbar"] ul li possuem as maiores precedências pelo algarismo abcd.
