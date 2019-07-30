Dado os seletores abaixo, forme o número de especificidade.

body ul li { ... }.----------------------------> 0003
.section-item > p.-----------------------------> 0012
head + body { ... }.---------------------------> 0002
#section-father ul li::before { ... }.---------> 0103
section ul li:hover { ... }.-------------------> 0013