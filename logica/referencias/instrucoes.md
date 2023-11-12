# Instruções

São separadas em 5 categorias, `Entrada e Saída`, `Controle de bloco`, `Operações`, `Controle de fluxo` e `Unidade de controle`

## Entrada e Saída

Possui interação com outros blocos de lógica.

### Read

`read [variavel] = [celula] at [indice]`

Essa instrução permite ler `números` armazenados em memórias e colocar seu valor em uma variável, onde o índice é um `inteiro` que possui o valor máximo a variar do bloco (Célula de memória 64 e Banco de memória 512).

ex.:

Suponhamos que o processador esteja conectado à uma célula `cell1` com a lista armazenada:
> [5, 2, -4, 1, 80, ...]

`read valor = cell1 at 2`

vai definir a variável `valor` com o valor -4, (o indice começa no 0)