# Conversão de tipo Python e conversão de tipo

Neste artigo, você aprenderá sobre a conversão de tipos e usos da conversão de tipos.

Antes de aprender a Conversão de tipos no Python, você deve ter conhecimento sobre os  tipos de dados do Python .

## Conversão de tipo

O processo de conversão do valor de um tipo de dados (inteiro, string, float etc.) para outro tipo de dados é chamado de conversão de tipo. Python tem dois tipos de conversão de tipos.

1. Conversão implícita de tipo
2. Conversão explícita de tipos

## Conversão implícita de tipo

Na conversão implícita de tipos, o Python converte automaticamente um tipo de dados para outro. Esse processo não precisa de nenhum envolvimento do usuário.

Vamos ver um exemplo em que o Python promove a conversão do tipo de dados mais baixo (número inteiro) para o tipo de dados mais alto (float) para evitar a perda de dados.

Exemplo 1: Convertendo Inteiro em Flutuante

```py
num_int = 123
num_flo = 1.23

num_new = num_int + num_flo

print("datatype of num_int:",type(num_int))
print("datatype of num_flo:",type(num_flo))

print("Value of num_new:",num_new)
print("datatype of num_new:",type(num_new))
```

Quando executamos o programa acima, a saída será

```py
datatype of num_int: <class 'int'>
datatype of num_flo: <class 'float'>

Value of num_new: 124.23
datatype of num_new: <class 'float'>
```

No programa acima,

1. Nós adicionamos duas variáveis `num_int` e `num_flo` , armazenando o valor em `num_new`.
2. Veremos o tipo de dados dos três objetos, respectivamente.
3. Na saída, podemos ver que o tipo de dados `num_int` é um `integer``, e o tipo de dados num_flo` é a `float`.
4. Além disso, podemos ver que o `num_new` possui floatum tipo de dados, porque o Python sempre converte um tipo de dados menor para outro, para evitar a perda de dados.

Agora, vamos tentar adicionar uma string e um número inteiro, e ver como o Python trata isso.

Exemplo 2: Adição do tipo de dados string(higher) e do tipo de dados inteiro(lower)

```py
num_int = 123
num_str = "456"

print("Data type of num_int:",type(num_int))
print("Data type of num_str:",type(num_str))

print(num_int+num_str)
```

Quando executamos o programa acima, a saída será

```py
Data type of num_int: <class 'int'>
Data type of num_str: <class 'str'>

Traceback (most recent call last):
  File "python", line 7, in <module>
TypeError: unsupported operand type(s) for +: 'int' and 'str'
```

No programa acima,

1. Nós adicionamos duas variáveis `num_int` e `num_str`.
2. Como podemos ver pela saída, conseguimos `typeerror`. O Python não pode usar a Conversão implícita nessa condição.
3. No entanto, o Python tem a solução para esse tipo de situação, conhecida como conversão explícita.

## Conversão explícita de tipos

Na Conversão explícita de tipos, os usuários convertem o tipo de dados de um objeto no tipo de dados necessário. Usamos as funções pré-definidas, como `int()`, `float()`, `str()`, etc para executar a conversão de tipo explícita.

Essa conversão de tipo também é chamada de conversão de texto, porque o usuário lança (altera) o tipo de dados dos objetos.

Sintaxe:

```py
(required_datatype)(expression)
```

A conversão de tipo pode ser feita atribuindo a função de tipo de dados necessária à expressão.

Exemplo 3: Adição de sequência e número inteiro usando conversão explícita

```py
num_int = 123
num_str = "456"

print("Data type of num_int:",type(num_int))
print("Data type of num_str before Type Casting:",type(num_str))

num_str = int(num_str)
print("Data type of num_str after Type Casting:",type(num_str))

num_sum = num_int + num_str

print("Sum of num_int and num_str:",num_sum)
print("Data type of the sum:",type(num_sum))
```

Quando executamos o programa acima, a saída será

```py
Data type of num_int: <class 'int'>
Data type of num_str before Type Casting: <class 'str'>

Data type of num_str after Type Casting: <class 'int'>

Sum of num_int and num_str: 579
Data type of the sum: <class 'int'>
```

No programa acima,

1. Nós adicionamos `num_str` e `num_int` variável.
2. Convertemos `num_str` do tipo strin(higher) para integer(lowe) usando a `int()` função para realizar a adição.
3. Depois de converter `num_str` em um valor inteiro, o Python pode adicionar essas duas variáveis.
4. Temos o valor `num_sum` e o tipo de dados como inteiro.

## Pontos-chave a serem lembrados

1. Conversão de tipo é a conversão de objeto de um tipo de dados para outro.
2. A conversão implícita de tipo é realizada automaticamente pelo interpretador Python.
3. O Python evita a perda de dados na conversão implícita de tipos.
4. A conversão explícita de tipos também é chamada de conversão de tipos, os tipos de dados do objeto são convertidos usando a função predefinida pelo usuário.
5. Em Tipo de transmissão, a perda de dados pode ocorrer à medida que aplicamos o objeto a um tipo de dados específico.
