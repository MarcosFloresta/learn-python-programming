# Loop for

Neste artigo, você aprenderá a iterar em uma sequência de elementos usando as diferentes variações do loop for.

## O que é loop em Python?

O loop for no Python é usado para iterar sobre uma sequência (list, tuple, string) ou outros objetos iteráveis. A iteração sobre uma sequência é chamada de passagem.

Sintaxe de para Loop

```py
for val in sequence:
    Body of for
```

Aqui `val` é a variável que leva o valor do item dentro da sequência em cada iteração.

O loop continua até chegarmos ao último item da sequência. O corpo do loop for é separado do restante do código usando indentação.

Fluxograma de Loop

![Fluxograma de for Loop na programação Python](/images/forLoop.jpg)

Exemplo: Python para Loop

```py
# Program to find the sum of all numbers stored in a list

# List of numbers
numbers = [6, 5, 3, 8, 4, 2, 5, 4, 11]

# variable to store the sum
sum = 0

# iterate over the list
for val in numbers:
    sum = sum+val

# Output: The sum is 48
print("The sum is", sum)
```

Quando você executa o programa, a saída será:

```py
The sum is 48
```

## A função range()

Podemos gerar uma sequência de números usando a função `range()`. `range(10)` irá gerar números de 0 a 9 (10 números).

Também podemos definir o tamanho de início, parada e passo como `range(start, stop, step size)`. o step size é padronizado como 1 se não for fornecido.

Esta função não armazena todos os valores na memória, seria ineficiente. Assim, ele lembra o início, a parada, o tamanho da etapa e gera o próximo número em movimento.

Para forçar esta função para saída de todos os itens, podemos usar a função `list()`.

O exemplo a seguir esclarecerá isso.

```py
# Output: range(0, 10)
print(range(10))

# Output: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
print(list(range(10)))

# Output: [2, 3, 4, 5, 6, 7]
print(list(range(2, 8)))

# Output: [2, 5, 8, 11, 14, 17]
print(list(range(2, 20, 3)))
```

Podemos usar a função `range()` em loops para iterar através de uma sequência de números. Ele pode ser combinado com a função `len()` para iterar por uma sequência usando indexação. Aqui está um exemplo.

```py
# Program to iterate through a list using indexing

genre = ['pop', 'rock', 'jazz']

# iterate over the list using index
for i in range(len(genre)):
    print("I like", genre[i])
```

Quando você executa o programa, a saída será:

```py
I like pop
I like rock
​I like jazz
```

## Loop for com else

Um loop for também pode ter um bloco else opcional. A peça `else` é executada se os itens na sequência usados ​​no loop for esgotados.

A instrução `break` pode ser usada para parar um loop for. Nesse caso, a parte else é ignorada.

Portanto, uma outra parte do loop for é executada se nenhuma interrupção ocorrer.

Aqui está um exemplo para ilustrar isso.

```py
digits = [0, 1, 5]

for i in digits:
    print(i)
else:
    print("No items left.")
```

Quando você executa o programa, a saída será:

```py
0
1
5
No items left.
```

Aqui, o loop for imprime itens da lista até o loop esgotar. Quando o loop for se esgota, ele executa o bloco de código no `else` e imprime

```py
No items left.
```
