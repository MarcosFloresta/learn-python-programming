# Entrada, Saída e Importação em Python

Este tutorial se concentra em duas funções internas print() e input() para executar tarefas de I/O no Python. Além disso, você aprenderá a importar módulos e usá-los em seu programa.

O Python fornece inúmeras funções internas que estão prontamente disponíveis para nós no prompt do Python.

Algumas das funções gostam input()e print()são amplamente usadas para operações padrão de entrada e saída, respectivamente. Vamos ver a seção de saída primeiro.

## Saída Python usando a função print()

Usamos a função print() para enviar dados para o dispositivo de saída padrão (tela).

Também podemos gerar dados para um arquivo , mas isso será discutido mais adiante. Um exemplo de uso é dado abaixo.

```py
print('This sentence is output to the screen')
# Output: This sentence is output to the screen

a = 5

print('The value of a is', a)
# Output: The value of a is 5
```

Na segunda declaração print(), podemos notar que um espaço foi adicionado entre a string e o valor da variável `a`. Isso é por padrão, mas podemos alterá-lo.

A sintaxe real da função print() é

```py
print(*objects, sep=' ', end='\n', file=sys.stdout, flush=False)
```

Aqui, `objects` estão os valores a serem impressos.

O  separador `sep` é usado entre os valores. O padrão é um caractere de espaço.

Depois que todos os valores são impressos, `end` é impresso. O padrão é uma nova linha (\n).

O `file` é o objeto em que os valores são impressos e seu valor padrão é sys.stdout (tela). Aqui está um exemplo para ilustrar isso.

```py
print(1,2,3,4)
# Output: 1 2 3 4

print(1,2,3,4,sep='*')
# Output: 1*2*3*4

print(1,2,3,4,sep='#',end='&')
# Output: 1#2#3#4&
```

### Formatação de saída

Às vezes, gostaríamos de formatar nossa saída para torná-la atraente. Isso pode ser feito usando o método `str.format()`. Este método é visível para qualquer objeto de string.

```py
>>> x = 5; y = 10
>>> print('The value of x is {} and y is {}'.format(x,y))
The value of x is 5 and y is 10
```

Aqui, os chavetas {} são usadas como espaços reservados. Podemos especificar a ordem em que ela é impressa usando números (tuple index).

```py
print('I love {0} and {1}'.format('bread','butter'))
# Output: I love bread and butter

print('I love {1} and {0}'.format('bread','butter'))
# Output: I love butter and bread
```

Podemos até usar argumentos de palavra-chave para formatar a string.

```py
>>> print('Hello {name}, {greeting}'.format(greeting = 'Goodmorning', name = 'John'))
Hello John, Goodmorning
```

Podemos até mesmo formatar strings como o velho `sprintf()` estilo usado na linguagem de programação C . Usamos o `%` operador para fazer isso.

```py
>>> x = 12.3456789
>>> print('The value of x is %3.2f' %x)
The value of x is 12.35
>>> print('The value of x is %3.4f' %x)
The value of x is 12.3457
```

## Entrada Python

Até agora, nossos programas eram estáticos. O valor das variáveis ​​foi definido ou codificado no código fonte.

Para permitir flexibilidade, podemos querer receber as informações do usuário. No Python, temos a função `input()` de permitir isso. A sintaxe para `input()` é

```py
input([prompt])
```

Onde `prompt` é a string que queremos exibir na tela. É opcional

```py
>>> num = input('Enter a number: ')
Enter a number: 10
>>> num
'10'
```

Aqui, podemos ver que o valor inserido `10` é uma string, não um número. Para converter isso em um número, podemos usar as funções `int()` ou `float()`.

```py
>>> int('10')
10
>>> float('10')
10.0
```

Esta mesma operação pode ser realizada usando a função eval() Mas isso leva ainda mais longe. Ele pode avaliar expressões pares, desde que a entrada seja uma string

```py
>>> int('2+3')
Traceback (most recent call last):
  File "<string>", line 301, in runcode
  File "<interactive input>", line 1, in <module>
ValueError: invalid literal for int() with base 10: '2+3'
>>> eval('2+3')
5
```

## Importação de Python

Quando nosso programa cresce, é uma boa ideia dividi-lo em diferentes módulos.

Um módulo é um arquivo que contém definições e instruções Python. Os módulos Python têm um nome de arquivo e terminam com a extensão `.py`.

As definições dentro de um módulo podem ser importadas para outro módulo ou o intérprete interativo no Python. Usamos a palavra-chave `import` para fazer isso.

Por exemplo, podemos importar o módulo `math` digitando `import math`.

```py
import math
print(math.pi)
# Output: 3.141592653589793
```

Agora todas as definições dentro do módulo `math` estão disponíveis em nosso escopo. Também podemos importar apenas alguns atributos e funções específicos, usando a palavra-chave `from`. Por exemplo:

```py
>>> from math import pi
>>> pi
3.141592653589793
```

Ao importar um módulo, o Python examina vários locais definidos em `sys.path`. É uma lista de locais de diretório.

```py
>>> import sys
>>> sys.path
['', 
 'C:\\Python33\\Lib\\idlelib', 
 'C:\\Windows\\system32\\python33.zip', 
 'C:\\Python33\\DLLs', 
 'C:\\Python33\\lib', 
 'C:\\Python33', 
 'C:\\Python33\\lib\\site-packages']
```

Também podemos adicionar nossa própria localização a esta lista.
