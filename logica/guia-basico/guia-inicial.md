---
description: Esse guia aborda o funcionamento de processadores lógicos e seu funcionamento.
---

# O que é um bloco de lógica ?

Bloco de lógica são blocos com o propósito de serem capazes de fazer lógica de programação, seus principais classes de componentes são `Mensagem`, `Alavanca`, `Processador`, `Memória` e `Monitor lógico`

Processador é uma classe de blocos capazes de executar código de programação. Vindo em 3 tamanhos com capacidades de programação diferentes, sendo capaz de ler 120, 480 ou 1500 instruções por segundo.

![Processadores](../../.gitbook/assets/logic-img1.png) 

# Exemplos

## Colocando uma mensagem

Para colocar uma mensagem em um bloco de mensagem, é necessário primeiramente conectar o processador e o bloco de mensagem.

![Colocando e conectando um processador](../../.gitbook/assets/logic-gif1.gif) 

Após cenario feito, hora de colocar comandos, é possivel fazer isso por meio de:
1 - copie o texto com os comandos (como o que vai ser mostrado logo agora), ir no processador, clicar em editar e em seguida, importar da area de transferência.
2 - Pode adicionar instrução por instrução através do botão `adicionar` (recomendado para pegar mais o costume).

Para escrever uma mensagem no bloco de mensagens se utiliza as seguintes instruções:

```
print "Olá Mundo!"
printflush message1
```

>  `print "Olá mundo!"`

armazenara o texto "Olá mundo!" para imprimir no próximo printflush.

> `printflush message1`

Imprimirá o texto armazenado no bloco chamado `message1`.

# Controlador de esteira

1 - Coloque um processador e conecte-o à uma esteira e à uma alavanca.

2 - Coloque o seguinte comando.

```
sensor ativo switch1 @enabled
jump 4 strictEqual ativo true
control enabled conveyor1 0 0 0 0
end
control enabled conveyor1 1 0 0 0
```

> sensor ativo switch1 @enabled

Essa instrução pega a informação `@enabled` da alavanca para ver se está ativa, e salva na variável `ativo`.
A variável pode ser qualquer nome (preferencia palavras alfanuméricas sem acento).

> jump 4 strictEqual ativo true

Pular para a ultima linha do processador (4 é o numero da linha, começando a contar com 0), se na variável `ativo` estiver exatamente o valor `true` e do mesmo tipo de `true` (no caso ele é um valor booleano e @enabled só retorna valores booleanos).

> control enabled conveyor1 0 0 0 0

Define a esteira como desativada, só vai ser possível a instrução passar por aqui se a linha anterior não deu como correta, ou seja, a alavanca não esta ativa.

> end

Ele volta o processador para linha 0 e começa tudo de novo em loop.

> control enabled conveyor1 1 0 0 0

Define a esteira como ativada, só possível caso a alavanca esteja também sendo ativa.
Como está no fim do código, processador volta para linha 0 e começa tudo de novo.