# Declaração, recuo e comentários do Python

Neste artigo, você aprenderá sobre as instruções Python, por que a indentação é importante e o uso de comentários na programação.

## Instrução Python

As instruções que um intérprete Python pode executar são chamadas de instruções. Por exemplo, `a = 1` é uma declaração de atribuição. `if` declaração, declaração, `for` declaração, while` etc. são outros tipos de declarações que serão discutidas mais adiante.

### Declaração de várias linhas

No Python, o final de uma instrução é marcado por um caractere de nova linha. Mas podemos fazer uma declaração se estender por várias linhas com o caractere de continuação de linha (\). Por exemplo:

```py
a = 1 + 2 + 3 + \
    4 + 5 + 6 + \
    7 + 8 + 9
```

Isso é continuação de linha explícita. No Python, a continuação da linha está implícita entre parênteses (), colchetes [] e chaves {}. Por exemplo, podemos implementar a declaração de várias linhas acima como

```py
a = (1 + 2 + 3 +
    4 + 5 + 6 +
    7 + 8 + 9)
```

Aqui, os parênteses circundantes () fazem a continuação da linha implicitamente. Mesmo é o caso com [] e {}. Por exemplo:

```py
colors = ['red',
          'blue',
          'green']
```

Também poderíamos colocar várias declarações em uma única linha usando ponto-e-vírgula, como a seguir

```py
a = 1; b = 2; c = 3
```

## Recuo do Python

A maioria das linguagens de programação, como C, C ++, Java, usa chaves {} para definir um bloco de código. Python usa indentação.

Um bloco de código (corpo de uma função , loop etc.) começa com recuo e termina com a primeira linha não recuada. A quantidade de recuo depende de você, mas deve ser consistente ao longo desse bloco.

Geralmente, quatro espaços em branco são usados ​​para indentação e são preferidos às guias. Aqui está um exemplo.

```py
para i na faixa(1, 11):
    impressao(i)
    se i == 5:
       pausa
```

A imposição de recuo no Python faz com que o código pareça limpo e arrumado. Isso resulta em programas Python que parecem semelhantes e consistentes.

O recuo pode ser ignorado na continuação da linha. Mas é uma boa ideia recuar sempre. Isso torna o código mais legível. Por exemplo:

```py
if True:
    print('Hello')
    a = 5
```

e

```py
if True: print('Hello'); a = 5
```

ambos são válidos e fazem a mesma coisa. Mas o estilo anterior é mais claro.

O recuo incorreto resultará em `IndentationError`.

## Comentários Python

Os comentários são muito importantes ao escrever um programa. Ele descreve o que está acontecendo dentro de um programa para que uma pessoa que olha o código-fonte não tenha dificuldade em descobrir. Você pode esquecer os principais detalhes do programa que acabou de escrever dentro de um mês. Portanto, dedicar tempo para explicar esses conceitos em forma de comentários é sempre proveitoso.

No Python, usamos o símbolo de hash (#) para começar a escrever um comentário.

Ele se estende até o caractere de nova linha. Os comentários são para programadores para melhor compreensão de um programa. O intérprete Python ignora o comentário.

```py
#This is a comment
#print out Hello
print('Hello')
```

### Comentários em várias linhas

Se tivermos comentários que estendem várias linhas, uma maneira de fazer isso é usar o hash (#) no início de cada linha. Por exemplo:

```py
#This is a long comment
#and it extends
#to multiple lines
```

Outra maneira de fazer isso é usar aspas triplas, `'''`ou `"""`.

Essas aspas triplas geralmente são usadas para seqüências de várias linhas. Mas eles também podem ser usados ​​como comentário de várias linhas. A menos que não sejam documentos, eles não geram código extra.

```py
"""This is also a
perfect example of
multi-line comments"""
```

### Docstring em Python

Docstring é a abreviação de string de documentação.

É uma sequência que ocorre como a primeira instrução em uma definição de módulo, função, classe ou método. Devemos escrever o que uma função / classe faz na doutrina.

As aspas triplas são usadas durante a escrita de documentos. Por exemplo:

```py
def double( num ):
    "" "Function to double the value" ""
    return 2 * num
```

A documentação está disponível para nós como o atributo `__doc__` da função. Emita o seguinte código no shell depois de executar o programa acima.

```py
>>> print(double.__doc__)
Function to double the value
```
