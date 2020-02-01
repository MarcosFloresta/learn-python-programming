# Loop while

Loops são usados ​​na programação para repetir um bloco de código específico. Neste artigo, você aprenderá a criar um loop while no Python.

## O que é o loop while no Python?

O loop while no Python é usado para iterar sobre um bloco de código, desde que a expressão de teste (condição) seja verdadeira.

Geralmente usamos esse loop quando não sabemos de antemão o número de vezes para iterar.

Sintaxe de while Loop em Python

```py
while test_expression:
    Body of while
```

No loop while, a expressão de teste é verificada primeiro. O corpo do loop é inserido apenas se test_expression for avaliado como True. Após uma iteração, a expressão de teste é verificada novamente. Esse processo continua até a test_expressionavaliação de False.

Em Python, o corpo do loop while é determinado por meio de indentação.

O corpo começa com recuo e a primeira linha sem recuo marca o fim.

Python interpreta qualquer valor diferente de zero como True. Nonee 0são interpretados como False.

Fluxograma do loop while
while Loop na programação Python

Exemplo: Python enquanto Loop
script.py
IPython Shell

Corre
Desenvolvido por DataCamp

Quando você executa o programa, a saída será:

Digite n: 10
A soma é 55
No programa acima, a expressão de teste será Truecontanto que nossa variável de contador i seja menor ou igual a n (10 em nosso programa).

Precisamos aumentar o valor da variável do contador no corpo do loop. Isso é muito importante (e principalmente esquecido). Não fazer isso resultará em um loop infinito (loop sem fim).

Finalmente, o resultado é exibido.

enquanto loop com else
Igual ao loop for , também podemos ter um elsebloco opcional com loop while.

A elsepeça é executada se a condição no loop while for avaliada como False.

O loop while pode ser finalizado com uma instrução break . Nesse caso, a elsepeça é ignorada. Portanto, a elseparte de um loop while é executada se nenhuma interrupção ocorrer e a condição for falsa.

Aqui está um exemplo para ilustrar isso.

script.py
IPython Shell

Corre
Desenvolvido por DataCamp
Resultado

Laço interno
Laço interno
Laço interno
Dentro de mais
Aqui, usamos uma variável de contador para imprimir a string Inside looptrês vezes.

Na quarta iteração, a condição em enquanto se torna False. Portanto, a elsepeça é executada.