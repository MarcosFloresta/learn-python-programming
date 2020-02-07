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

No loop while, a expressão de teste é verificada primeiro. O corpo do loop é inserido apenas se `test_expression` for avaliado como `True`. Após uma iteração, a expressão de teste é verificada novamente. Esse processo continua até a avaliação de `test_expression` for `False`.

Em Python, o corpo do loop while é determinado por meio de indentação.

O corpo começa com recuo e a primeira linha sem recuo marca o fim.

Python interpreta qualquer valor diferente de zero como `True`. `None` e `0` são interpretados como False.

Fluxograma do loop while

![Loop while  na programação Python](/images/whileLoopFlowchart.jpg)

Exemplo: Python enquanto Loop

```py
# Program to add natural
# numbers upto 
# sum = 1+2+3+...+n

# To take input from the user,
# n = int(input("Enter n: "))

n = 10

# initialize sum and counter
sum = 0
i = 1

while i <= n:
    sum = sum + i
    i = i+1    # update counter

# print the sum
print("The sum is", sum)
```

Quando você executa o programa, a saída será:

```py
Enter n: 10
The sum is 55
```

No programa acima, a expressão de teste será `True` contanto que nossa variável de contador `i` seja menor ou igual a `n` (10 em nosso programa).

Precisamos aumentar o valor da variável do contador no corpo do loop. Isso é muito importante (e principalmente esquecido). Não fazer isso resultará em um loop infinito (loop sem fim).

Finalmente, o resultado é exibido.

## Loop while com else

Igual ao `loop for`, também podemos ter um bloco `else` opcional com loop while.

A peça `else` é executada se a condição no loop while for avaliada como `False`.

O loop while pode ser finalizado com uma instrução `break` . Nesse caso, a peça `else` é ignorada. Portanto, a parte `else` de um loop while é executada se nenhuma interrupção ocorrer e a condição for falsa.

Aqui está um exemplo para ilustrar isso.

```py
# Example to illustrate
# the use of else statement
# with the while loop

counter = 0

while counter < 3:
    print("Inside loop")
    counter = counter + 1
else:
    print("Inside else")
```

Resultado

```txt
Inside loop
Inside loop
Inside loop
Inside else
```

Aqui, usamos uma variável de contador para imprimir a string `Inside loop` três vezes.

Na quarta iteração, a condição em `while` se torna False. Portanto, a parte else é executada.
