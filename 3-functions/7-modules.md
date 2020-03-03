Módulos Python
Neste artigo, você aprenderá a criar e importar módulos personalizados no Python. Além disso, você encontrará diferentes técnicas para importar e usar módulos personalizados e internos no Python.

O que são módulos no Python?
Módulos referem-se a um arquivo que contém instruções e definições Python.

Um arquivo contendo código Python, por exemplo:, example.pyé chamado de módulo e seu nome seria example.

Utilizamos módulos para dividir grandes programas em pequenos arquivos gerenciáveis ​​e organizados. Além disso, os módulos fornecem reutilização de código.

Podemos definir nossas funções mais usadas em um módulo e importá-las, em vez de copiar suas definições em diferentes programas.

Vamos criar um módulo. Digite o seguinte e salve-o como example.py.

# Python Module example

def add(a, b):
   """This program adds two
   numbers and return the result"""

   result = a + b
   return result
Aqui, definimos uma função add() dentro de um módulo chamado example. A função recebe dois números e retorna sua soma.

Como importar módulos no Python?
Podemos importar as definições dentro de um módulo para outro módulo ou o intérprete interativo em Python.

Usamos a importpalavra-chave para fazer isso. Para importar nosso módulo definido anteriormente example, digite o seguinte no prompt do Python.

>>> exemplo de importação
Isso não insere os nomes das funções definidas examplediretamente na tabela de símbolos atual. Ele apenas digita o nome do módulo examplelá.

Usando o nome do módulo, podemos acessar a função usando o . operador de ponto . Por exemplo:

>>> example.add (4,5.5)
9,5
Python tem uma tonelada de módulos padrão disponíveis.

Você pode conferir a lista completa dos módulos padrão do  Python e para que servem. Esses arquivos estão no diretório Lib dentro do local em que você instalou o Python.

Os módulos padrão podem ser importados da mesma maneira que importamos nossos módulos definidos pelo usuário.

Existem várias maneiras de importar módulos. Eles estão listados da seguinte maneira.

Instrução de importação Python
Podemos importar um módulo usando a importinstrução e acessar as definições dentro dele usando o operador de ponto, conforme descrito acima. Aqui está um exemplo.

script.py
IPython Shell

Corre
Desenvolvido por DataCamp

Quando você executa o programa, a saída será:

O valor de pi é 3,141592653589793
Importar com renomeação
Podemos importar um módulo renomeando-o da seguinte forma.

script.py
IPython Shell

Corre
Desenvolvido por DataCamp
Renomeamos o mathmódulo como m. Isso pode economizar tempo de digitação em alguns casos.

Observe que o nome mathnão é reconhecido em nosso escopo. Portanto, math.pié inválido, m.pié a implementação correta.

Instrução Python from ... import
Podemos importar nomes específicos de um módulo sem importar o módulo como um todo. Aqui está um exemplo.

script.py
IPython Shell

Corre
Desenvolvido por DataCamp
Importamos apenas o atributo pi do módulo.

Nesse caso, não usamos o operador de ponto. Poderíamos ter importado vários atributos da seguinte maneira.

>>> da matemática import pi, e
>>> pi
3.141592653589793
>>> e
2.718281828459045
Importar todos os nomes
Podemos importar todos os nomes (definições) de um módulo usando a seguinte construção.

script.py
IPython Shell

Corre
Desenvolvido por DataCamp
Importamos todas as definições do módulo de matemática. Isso torna todos os nomes, exceto aqueles que começam com um sublinhado, visíveis em nosso escopo.

Importar tudo com o símbolo de asterisco (*) não é uma boa prática de programação. Isso pode levar a definições duplicadas para um identificador. Isso também dificulta a legibilidade do nosso código.

Caminho de pesquisa do módulo Python
Ao importar um módulo, o Python examina vários lugares. O intérprete primeiro procura um módulo interno e depois (se não for encontrado) em uma lista de diretórios definidos em sys.path. A pesquisa está nesta ordem.

O diretório atual.
PYTHONPATH (uma variável de ambiente com uma lista de diretório).
O diretório padrão dependente da instalação.
>>> import sys
>>> sys.path
['',
'C: \\ Python33 \\ Lib \\ idlelib',
'C: \\ Windows \\ system32 \\ python33.zip',
'C: \\ Python33 \\ DLLs',
'C: \\ Python33 \\ lib',
'C: \\ Python33',
'C: \\ Python33 \\ lib \\ pacotes do site']
Podemos adicionar modificar esta lista para adicionar nosso próprio caminho.

Recarregando um módulo
O intérprete Python importa um módulo apenas uma vez durante uma sessão. Isso torna as coisas mais eficientes. Aqui está um exemplo para mostrar como isso funciona.

Suponha que temos o seguinte código em um módulo chamado my_module.

# This module shows the effect of
#  multiple imports and reload

print("This code got executed")
Agora vemos o efeito de várias importações.

>>> importar meu_modulo
Este código foi executado
>>> importar meu_modulo
>>> importar meu_modulo
Podemos ver que nosso código foi executado apenas uma vez. Isso significa que nosso módulo foi importado apenas uma vez.

Agora, se o nosso módulo mudar durante o curso do programa, teremos que recarregá-lo. Uma maneira de fazer isso é reiniciar o intérprete. Mas isso não ajuda muito.

Python fornece uma maneira elegante de fazer isso. Podemos usar a reload()função dentro do impmódulo para recarregar um módulo. Assim que se faz.

>>> importação imp
>>> importar meu_modulo
Este código foi executado
>>> importar meu_modulo
>>> imp.reload (meu_modulo)
Este código foi executado
<módulo 'my_module' de '. \\ my_module.py'>
A função interna dir ()
Podemos usar a dir()função para descobrir nomes que são definidos dentro de um módulo.

Por exemplo, definimos uma função add()no módulo exampleque tínhamos no começo.

>>> dir (exemplo)
['__builtins__',
'__cached__',
'__doc__',
'__Arquivo__',
'__inicialização__',
'__carregador__',
'__nome__',
'__pacote__',
'adicionar']
Aqui, podemos ver uma lista ordenada de nomes (junto com add). Todos os outros nomes que começam com um sublinhado são atributos padrão do Python associados ao módulo (nós não os definimos).

Por exemplo, o __name__atributo contém o nome do módulo.

>>> exemplo de importação
>>> exemplo .__ nome__
'exemplo'
Todos os nomes definidos em nosso namespace atual podem ser encontrados usando a dir()função sem argumentos.

>>> a = 1
>>> b = "olá"
>>> importar matemática
>>> dir ()
['__builtins__', '__doc__', '__name__', 'a', 'b', 'math', 'pyscripter']
