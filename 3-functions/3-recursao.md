# Recursão em Python

Neste artigo, você aprenderá a criar uma função recursiva; uma função que se chama.

## O que é recursão no Python?

A recursão é o processo de definir algo em termos de si mesmo.

Um exemplo do mundo físico seria colocar dois espelhos paralelos um de frente para o outro. Qualquer objeto entre eles seria refletido recursivamente.

## Função Recursiva em Python

Sabemos que no Python, uma função pode chamar outras funções. É até possível para a função se chamar. Esse tipo de construção é denominado como funções recursivas.

A seguir, é apresentado um exemplo de função recursiva para encontrar o fatorial de um número inteiro.

O fatorial de um número é o produto de todos os números inteiros de 1 a esse número. Por exemplo, o fatorial de `6` (indicado como `6!`) É `1 * 2 * 3 * 4 * 5 * 6 = 720`.

Exemplo de função recursiva

```py
# An example of a recursive function to
# find the factorial of a number

def calc_factorial(x):
    """This is a recursive function
    to find the factorial of an integer"""

    if x == 1:
        return 1
    else:
        return (x * calc_factorial(x-1))

num = 4
print("The factorial of", num, "is", calc_factorial(num))
```

No exemplo acima, `calc_factorial()` é uma função recursiva como se chama.

Quando chamamos essa função com um número inteiro positivo, ela se chama recursivamente diminuindo o número.

Cada chamada de função multiplica o número pelo fatorial do número 1 até que o número seja igual a um. Essa chamada recursiva pode ser explicada nas seguintes etapas.

```py
calc_factorial(4)              # 1st call with 4
4 * calc_factorial(3)          # 2nd call with 3
4 * 3 * calc_factorial(2)      # 3rd call with 2
4 * 3 * 2 * calc_factorial(1)  # 4th call with 1
4 * 3 * 2 * 1                  # return from 4th call as number=1
4 * 3 * 2                      # return from 3rd call
4 * 6                          # return from 2nd call
24                             # return from 1st call
```

Nossa recursão termina quando o número se reduz a 1. Isso é chamado de condição básica.

Toda função recursiva deve ter uma condição básica que interrompa a recursão, ou então a função se chama infinitamente.

## Vantagens da recursão

1. Funções recursivas fazem o código parecer limpo e elegante.
2. Uma tarefa complexa pode ser dividida em sub-problemas mais simples usando a recursão.
3. A geração de sequência é mais fácil com recursão do que com alguma iteração aninhada.

## Desvantagens da recursão

1. Às vezes, é difícil seguir a lógica por trás da recursão.
2. As chamadas recursivas são caras (ineficientes), pois consomem muita memória e tempo.
3. Funções recursivas são difíceis de depurar.
4. 