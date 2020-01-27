Tipos de dados Python
Neste tutorial, você aprenderá sobre os diferentes tipos de dados que você pode usar no Python.

Tipos de dados em Python
Todo valor no Python tem um tipo de dados. Como tudo é um objeto na programação Python, os tipos de dados são realmente classes e variáveis ​​são instância (objeto) dessas classes.

Existem vários tipos de dados no Python. Alguns dos tipos importantes estão listados abaixo.

Números Python
Inteiros, números de ponto flutuante e números complexos se enquadram na categoria de números Python . Eles são definidos como int, floate complexclasse em Python.

Podemos usar a type()função para saber a qual classe uma variável ou valor pertence e a isinstance()função para verificar se um objeto pertence a uma classe específica.

script.py
IPython Shell

Corre
Desenvolvido por DataCamp
Os números inteiros podem ter qualquer comprimento, apenas são limitados pela memória disponível.

Um número de ponto flutuante tem precisão de até 15 casas decimais. Pontos inteiros e pontos flutuantes são separados por pontos decimais. 1é inteiro, 1.0é o número do ponto flutuante.

Números complexos são escritos no formato, x + yjonde x é a parte real e y é a parte imaginária. Aqui estão alguns exemplos.

>>> a = 1234567890123456789
>>> a
1234567890123456789
>>> b = 0.1234567890123456789
>>> b
0.12345678901234568
>>> c = 1+2j
>>> c
(1+2j)
Observe que a floatvariável b foi truncada.

Lista Python
Lista é uma sequência ordenada de itens. É um dos tipos de dados mais usados ​​em Python e é muito flexível. Todos os itens em uma lista não precisam ser do mesmo tipo.


Declarar uma lista é bastante simples. Os itens separados por vírgulas são colocados entre colchetes [].

>>> a = [1, 2.2, 'python']
Podemos usar o operador de fatiar [] para extrair um item ou um intervalo de itens de uma lista. O índice inicia o formulário 0 no Python.

script.py
IPython Shell

Corre
Desenvolvido por DataCamp
As listas são mutáveis, ou seja, o valor dos elementos de uma lista pode ser alterado.

>>> a = [1,2,3]
>>> a[2]=4
>>> a
[1, 2, 4]
Tupla Python
A tupla é uma sequência ordenada de itens, igual à lista. A única diferença é que as tuplas são imutáveis. Tuplas criadas uma vez não podem ser modificadas.

As tuplas são usadas para proteger dados contra gravação e geralmente são mais rápidas que a lista, pois não podem ser alteradas dinamicamente.

É definido entre parênteses () onde os itens são separados por vírgulas.

>>> t = (5,'program', 1+3j)
Podemos usar o operador de fatiar [] para extrair itens, mas não podemos alterar seu valor.

script.py
IPython Shell

Corre
Desenvolvido por DataCamp
Python Strings
String é uma sequência de caracteres Unicode. Podemos usar aspas simples ou duplas para representar strings. As cadeias de linhas múltiplas podem ser indicadas usando aspas triplas '''ou """.

>>> s = "This is a string"
>>> s = '''a multiline
Como lista e tupla, o operador de fatiamento [] pode ser usado com string. Strings são imutáveis.

script.py
IPython Shell

Corre
Desenvolvido por DataCamp
Conjunto Python
Conjunto é uma coleção não ordenada de itens exclusivos. Conjunto é definido por valores separados por vírgula dentro de chaves {}. Os itens de um conjunto não são pedidos.

script.py
IPython Shell

Corre
Desenvolvido por DataCamp
Podemos executar operações de conjuntos como união, interseção em dois conjuntos. O conjunto possui valores exclusivos. Eles eliminam duplicatas.

>>> a = {1,2,2,3,3,3}
>>> a
{1, 2, 3}
Como set não é uma coleção ordenada, a indexação não tem significado. Portanto, o operador de fatiar [] não funciona.

>>> a = {1,2,3}
>>> a[1]
Traceback (most recent call last):
  File "<string>", line 301, in runcode
  File "<interactive input>", line 1, in <module>
TypeError: 'set' object does not support indexing
Dicionário Python
Dicionário é uma coleção não ordenada de pares de valores-chave.

Geralmente é usado quando temos uma enorme quantidade de dados. Os dicionários são otimizados para recuperar dados. Precisamos conhecer a chave para recuperar o valor.

No Python, os dicionários são definidos entre chaves {}, com cada item sendo um par no formulário key:value. Chave e valor podem ser de qualquer tipo.

>>> d = {1:'value','key':2}
>>> type(d)
<class 'dict'>
Usamos key para recuperar o respectivo valor. Mas não o contrário.

script.py
IPython Shell

Corre
Desenvolvido por DataCamp
Conversão entre tipos de dados
Podemos converter entre diferentes tipos de dados usando funções de conversão de tipos diferentes, como int (), float (), str () etc.

>>> float(5)
5.0
A conversão de float para int truncará o valor (aproxime-o de zero).

>>> int(10.6)
10
>>> int(-10.6)
-10
A conversão de e para string deve conter valores compatíveis.

>>> float('2.5')
2.5
>>> str(25)
'25'
>>> int('1p')
Traceback (most recent call last):
  File "<string>", line 301, in runcode
  File "<interactive input>", line 1, in <module>
ValueError: invalid literal for int() with base 10: '1p'
Podemos até converter uma sequência para outra.

>>> set([1,2,3])
{1, 2, 3}
>>> tuple({5,6,7})
(5, 6, 7)
>>> list('hello')
['h', 'e', 'l', 'l', 'o']
Para converter em dicionário, cada elemento deve ser um par

>>> dict([[1,2],[3,4]])
{1: 2, 3: 4}
>>> dict([(3,26),(4,44)])
{3: 26, 4: 44}