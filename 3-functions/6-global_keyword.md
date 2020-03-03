# Palavra-chave global em Python

Neste artigo, você aprenderá sobre a palavra-chave `global`, variável global e quando usar palavras-chave globais.

Antes de ler este artigo, verifique se você tem alguns conceitos básicos de variáveis ​​globais, locais e não-locais do Python .

## Introdução à palavra-chave global

No Python, a globalpalavra-chave permite modificar a variável fora do escopo atual. É usado para criar uma variável global e fazer alterações na variável em um contexto local.

## Regras da palavra-chave global

As regras básicas para palavras-chaveglobal em Python são:

- Quando criamos uma variável dentro de uma função, ela é local por padrão.
- Quando definimos uma variável fora de uma função, ela é global por padrão. Você não precisa usar a globalpalavra-chave.
- Usamos palavras-chaveglobal para ler e escrever uma variável global dentro de uma função.
O uso de globalpalavras-chave fora de uma função não tem efeito
Uso da palavra-chave global (com exemplo)
Vamos dar um exemplo.

Exemplo 1: Acessando variável global de dentro de uma função
script.py
IPython Shell

Corre
Desenvolvido por DataCamp
Quando executamos o programa acima, a saída será:

1
No entanto, podemos ter alguns cenários em que precisamos modificar a variável global de dentro de uma função.

Exemplo 2: Modificando variável global de dentro da função
script.py
IPython Shell

Corre
Desenvolvido por DataCamp
Quando executamos o programa acima, a saída mostra um erro:

UnboundLocalError: variável local 'c' referenciada antes da atribuição
Isso ocorre porque só podemos acessar a variável global, mas não podemos modificá-la de dentro da função.

A solução para isso é usar a globalpalavra - chave.

Exemplo 3: Alterando variável global de dentro de uma função usando global
script.py
IPython Shell

Corre
Desenvolvido por DataCamp
Quando executamos o programa acima, a saída será:

Adicionar dentro (): 2
Principal: 2
No programa acima, definimos c como uma palavra-chave global dentro da add()função.

Então, incrementamos a variável c em 1, ie c = c + 2. Depois disso, chamamos a add()função Finalmente, imprimimos a variável global c .

Como podemos ver, a mudança também ocorreu na variável global fora da função c = 2,.

Variáveis ​​globais em módulos Python

No Python, criamos um único módulo config.pypara armazenar variáveis ​​globais e compartilhar informações entre os módulos do Python dentro do mesmo programa.

Aqui está como podemos compartilhar variáveis ​​globais entre os módulos python.

Exemplo 4: Compartilhar uma variável global entre módulos Python
Crie um config.pyarquivo para armazenar variáveis ​​globais

a = 0
b = "empty"
Crie um update.pyarquivo para alterar variáveis ​​globais

import config

config.a = 10
config.b = "alphabet"
Crie um main.pyarquivo para testar alterações de valor

import config
import update

print(config.a)
print(config.b)
Quando executamos o main.pyarquivo, a saída será

10
alfabeto
No exemplo acima, criamos três arquivos: config.py, update.pye main.py.

O módulo config.pyarmazena variáveis ​​globais de a e b . No update.pyarquivo, importamos o config.pymódulo e modificamos os valores de a e b . Da mesma forma, no main.pyarquivo, importamos os dois config.pye o update.pymódulo. Por fim, imprimimos e testamos os valores das variáveis ​​globais, sejam elas alteradas ou não.

Global em funções aninhadas
Aqui está como você pode usar uma variável global na função aninhada.

Exemplo 5: Usando uma variável global na função aninhada
script.py
IPython Shell

Corre
Desenvolvido por DataCamp
A saída é:

Antes de ligar para a barra: 20
Barra de chamada agora
Depois de ligar para a barra: 20
x no principal: 25
No programa acima, declaramos variável global dentro da função aninhada bar(). foo()Função interna , x não tem efeito da palavra-chave global.

Antes e depois da chamada bar(), a variável x assume o valor da variável local, ie x = 20. Fora da foo()função, a variável x assumirá o valor definido na bar()função ie x = 25. Isso ocorre porque usamos a globalpalavra-chave em x para criar uma variável global dentro da bar()função (escopo local).

Se fizermos alterações dentro da bar()função, as alterações aparecerão fora do escopo local, ou seja foo().