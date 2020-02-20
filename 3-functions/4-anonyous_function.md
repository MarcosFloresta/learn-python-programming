# Função Python Anônimo / Lambda

Neste artigo, você aprenderá sobre a função anônima, também conhecida como funções lambda. Você aprenderá o que é, sua sintaxe e como usá-lo (com exemplos).

O que são funções lambda no Python?
No Python, função anônima é uma função definida sem um nome.

Enquanto funções normais são definidas usando a defpalavra - chave, no Python, funções anônimas são definidas usando a lambdapalavra - chave.

Portanto, funções anônimas também são chamadas de funções lambda.

Como usar as funções lambda no Python?
Uma função lambda em python possui a seguinte sintaxe.

Sintaxe da função Lambda em python
argumentos lambda: expressão
As funções do Lambda podem ter qualquer número de argumentos, mas apenas uma expressão. A expressão é avaliada e retornada. As funções Lambda podem ser usadas sempre que objetos de função forem necessários.

Exemplo de função Lambda em python
Aqui está um exemplo da função lambda que dobra o valor de entrada.

script.py
IPython Shell

Corre
Desenvolvido por DataCamp

No programa acima, lambda x: x * 2é a função lambda. Aqui x é o argumento e x * 2é a expressão que é avaliada e retornada.

Esta função não tem nome. Retorna um objeto de função que é atribuído ao identificador double. Agora podemos chamá-lo como uma função normal. A declaração

double = lambda x: x * 2
é quase o mesmo que

def duplo (x):
   retornar x * 2
Uso da função Lambda em python
Usamos funções lambda quando exigimos uma função sem nome por um curto período de tempo.

Em Python, geralmente o usamos como argumento para uma função de ordem superior (uma função que aceita outras funções como argumentos ). Funções de lambda são utilizados juntamente com funções internas de gosto filter(), map()etc.

Exemplo de uso com filter ()
A filter()função no Python usa uma função e uma lista como argumentos.

A função é chamada com todos os itens da lista e é retornada uma nova lista que contém itens para os quais a função é avaliada True.

Aqui está um exemplo de uso da filter()função para filtrar apenas números pares de uma lista.

script.py
IPython Shell

Corre
Desenvolvido por DataCamp
Exemplo de uso com map ()
A map()função no Python aceita uma função e uma lista.

A função é chamada com todos os itens da lista e é retornada uma nova lista que contém itens retornados por essa função para cada item.

Aqui está um exemplo de uso da map()função para dobrar todos os itens em uma lista.