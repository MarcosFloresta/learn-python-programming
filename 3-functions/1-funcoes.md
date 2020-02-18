# Funções em Python

Neste artigo, você aprenderá sobre funções; o que é uma função, a sintaxe, os componentes e os tipos de uma função. Além disso, você aprenderá a criar uma função no Python.

## O que é uma função no Python?

No Python, function é um grupo de instruções relacionadas que executam uma tarefa específica.

As funções ajudam a dividir nosso programa em blocos menores e modulares. À medida que nosso programa cresce, as funções o tornam mais organizado e gerenciável.

Além disso, evita repetições e torna o código reutilizável.

Sintaxe da Função

```py
def function_name(parameters):
    """docstring"""
    statement(s)
```

Acima é mostrada uma definição de função que consiste nos seguintes componentes.

1. A palavra-chave `def` marca o início do cabeçalho da função.
2. Um nome de função para identificá-lo exclusivamente. A nomeação de funções segue as mesmas regras para escrever identificadores no Python.
3. Parâmetros (argumentos) através dos quais passamos valores para uma função. Eles são opcionais.
4. Dois pontos (:) para marcar o final do cabeçalho da função.
5. Sequência de documentação opcional (docstring) para descrever o que a função faz.
6. Uma ou mais instruções python válidas que compõem o corpo da função. As instruções devem ter o mesmo nível de indentação (geralmente 4 espaços).
7. Uma instrução `return` opcional para retornar um valor da função.

Exemplo de uma Função

```py
def greet(name):
    """This function greets to
    the person passed in as
    parameter"""
    print("Hello, " + name + ". Good morning!")
```

## Como chamar uma função em python?

Depois de definir uma função, podemos chamá-la de outra função, programa ou mesmo do prompt do Python. Para chamar uma função, basta digitar o nome da função com os parâmetros apropriados.

```py
>>> greet('Paul')
Hello, Paul. Good morning!
```

Nota:  Tente executar o código acima no Python shell para ver a saída.

## Docstring

A primeira string após o cabeçalho da função é chamada de docstring e é a abreviação de string de documentação. É usado para explicar resumidamente o que uma função faz.

Embora opcional, a documentação é uma boa prática de programação. A menos que você se lembre do que comeu na semana passada, sempre documente seu código.

No exemplo acima, temos uma string de documento imediatamente abaixo do cabeçalho da função. Geralmente, usamos aspas triplas para que a sequência de caracteres possa se estender até várias linhas. Essa sequência está disponível para nós como atributo da função `__doc__` .

Por exemplo:

Tente executar o seguinte no Python shell para ver a saída.

```py
>>> print(greet.__doc__)
This function greets to
    the person passed into the
    name parameter
```

## A declaração de retorno

A instrução `return` é usada para sair de uma função e voltar ao local de onde foi chamada.

Sintaxe de return

```py
return [expression_list]
```

Esta declaração pode conter expressão que é avaliada e o valor é retornado. Se não houver expressão na instrução ou a returnprópria instrução não estiver presente dentro de uma função, a função retorn ará o Noneobjeto.

Por exemplo:

```py
>>> print(greet("May"))
Hello, May. Good morning!
None
```

Aqui, `None` é o valor retornado.

Exemplo de retorno

```py
def absolute_value(num):
    """This function returns the absolute
    value of the entered number"""

    if num >= 0:
        return num
    else:
        return -num

# Output: 2
print(absolute_value(2))

# Output: 4
print(absolute_value(-4))
```

Como funciona a função em Python?

![Como a função funciona em Python?](/images/python-how-function-works_1.jpg)

## Escopo e tempo de vida das variáveis

O escopo de uma variável é a parte de um programa em que a variável é reconhecida. Parâmetros e variáveis ​​definidos dentro de uma função não são visíveis de fora. Portanto, eles têm um escopo local.

A vida útil de uma variável é o período durante o qual a variável sai na memória. O tempo de vida das variáveis ​​dentro de uma função é contanto que a função seja executada.

Eles são destruídos quando retornamos da função. Portanto, uma função não lembra o valor de uma variável de suas chamadas anteriores.

Aqui está um exemplo para ilustrar o escopo de uma variável dentro de uma função.

```py
def my_func():
    x = 10
    print("Value inside function:",x)

x = 20
my_func()
print("Value outside function:",x)
```

Resultado

```txt
Value inside function: 10
Value outside function: 20
```

Aqui, podemos ver que o valor de `x` é 20 inicialmente. Mesmo que a função `my_func()` alterou o valor de `x` para 10, ela não afetou o valor fora da função.

Isso ocorre porque a variável `x` dentro da função é diferente (local da função) da externa. Embora tenham o mesmo nome, são duas variáveis ​​diferentes com escopo diferente.

Por outro lado, variáveis ​​fora da função são visíveis a partir de dentro. Eles têm um escopo global.

Podemos ler esses valores de dentro da função, mas não podemos alterá-los (gravá-los). A fim de modificar o valor de variáveis fora da função, eles devem ser declarados como variáveis globais usando a palavra-chave `global`.

## Tipos de funções

Basicamente, podemos dividir funções nos dois seguintes tipos:

Funções internas - Funções que são incorporadas ao Python.
Funções definidas pelo usuário - Funções definidas pelos próprios usuários