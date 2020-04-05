# Iteradores Python

Iteradores são objetos que podem ser iterados. Neste tutorial, você aprenderá como o iterador funciona e como criar seu próprio iterador usando os métodos `__iter__` e `__next__`.

# O que são iteradores no Python?

Os iteradores estão por toda parte no Python. Eles são elegantemente implementados em forloops, compreensões, geradores etc., mas ocultos à vista de todos.

O iterador no Python é simplesmente um objeto que pode ser iterado. Um objeto que retornará dados, um elemento de cada vez.

Tecnicamente falando, o objeto iterador do Python deve implementar dois métodos especiais `__iter__()` e `__next__()`, coletivamente chamado de protocolo do iterador .

Um objeto é chamado iterável se pudermos obter um iterador. A maioria dos contêineres embutidos no Python, como: lista , tupla , string etc., é iterável.

A função `iter()` (que por sua vez chama o método `__iter__()`) retorna um iterador a partir deles.

## Iterando Através de um Iterador em Python

Usamos a função `next()` para iterar manualmente todos os itens de um iterador. Quando chegamos ao fim e não há mais dados a serem retornados, eles aumentam `StopIteration`. A seguir está um exemplo.

```py
# define a list
my_list = [4, 7, 0, 3]

# get an iterator using iter()
my_iter = iter(my_list)

## iterate through it using next() 

#prints 4
print(next(my_iter))

#prints 7
print(next(my_iter))

## next(obj) is same as obj.__next__()

#prints 0
print(my_iter.__next__())

#prints 3
print(my_iter.__next__())

## This will raise error, no items left
next(my_iter)
```

Uma maneira mais elegante de iterar automaticamente é usando o loop for . Usando isso, podemos iterar sobre qualquer objeto que possa retornar um iterador, por exemplo, lista, string, arquivo etc.

```py
>>> for element in my_list:
...     print(element)
...     
4
7
0
3
```

## Como o loop for realmente funciona?

Como podemos ver no exemplo acima, o loop `for` foi capaz de percorrer automaticamente a lista.

De fato, o loop `for` pode iterar sobre qualquer iterável. Vamos dar uma olhada em como o loop `for` é realmente implementado no Python.

```py
for element in iterable:
    # do something with element
```

É realmente implementado como.

```py
# create an iterator object from that iterable
iter_obj = iter(iterable)

# infinite loop
while True:
    try:
        # get the next item
        element = next(iter_obj)
        # do something with element
    except StopIteration:
        # if StopIteration is raised, break from loop
        break
```

Portanto, internamente, o loop `for` cria um objeto iterador, `iter_obj` chamando o `iter()`  iterável.

Ironicamente, esse loop `for` é realmente um loop while infinito .

Dentro do loop, ele chama `next()` para obter o próximo elemento e executa o corpo do loop `for` com esse valor. Após a exaustão de todos os itens, `StopIteration` é levantado o que é capturado internamente e o loop termina. Observe que qualquer outro tipo de exceção passará.

## Construindo seu próprio iterador em Python

Construir um iterador do zero é fácil no Python. Nós apenas temos que implementar os métodos `__iter__()` e `__next__()`.

O método `__iter__()` retorna o próprio objeto iterador. Se necessário, alguma inicialização pode ser realizada.

O método `__next__()` deve retornar o próximo item na sequência. Ao chegar ao fim e nas chamadas subseqüentes, ele deve aumentar `StopIteration`.

Aqui, mostramos um exemplo que nos dará o próximo poder de 2 em cada iteração. O expoente de energia começa de zero até um número definido pelo usuário.

```py
class PowTwo:
    """Class to implement an iterator
    of powers of two"""

    def __init__(self, max = 0):
        self.max = max

    def __iter__(self):
        self.n = 0
        return self

    def __next__(self):
        if self.n <= self.max:
            result = 2 ** self.n
            self.n += 1
            return result
        else:
            raise StopIteration
```

Agora podemos criar um iterador e iterá-lo da seguinte maneira.

```py
>>> a = PowTwo(4)
>>> i = iter(a)
>>> next(i)
1
>>> next(i)
2
>>> next(i)
4
>>> next(i)
8
>>> next(i)
16
>>> next(i)
Traceback (most recent call last):
...
StopIteration
```

Também podemos usar um loop `for` para iterar sobre nossa classe de iterador.

```py
>>> for i in PowTwo(5):
...     print(i)
...
1
2
4
8
16
32
```

## Iteradores Infinitos em Python

Não é necessário que o item em um objeto iterador tenha que esgotar. Pode haver iteradores infinitos (que nunca terminam). Devemos ter cuidado ao manusear esse iterador.

Aqui está um exemplo simples para demonstrar iteradores infinitos.

A função interna `iter()` pode ser chamada com dois argumentos em que o primeiro argumento deve ser um objeto que pode ser chamado (função) e o segundo é o sentinela. O iterador chama essa função até que o valor retornado seja igual ao sentinela.

```py
>>> int()
0

>>> inf = iter(int,1)
>>> next(inf)
0
>>> next(inf)
0
```

Podemos ver que a função `int()` sempre retorna 0. Portanto, passá-la como `iter(int,1)` retornará um iterador que chama `int()` até que o valor retornado seja igual a 1. Isso nunca acontece e obtemos um iterador infinito.

Também podemos criar nossos próprios iteradores infinitos. O iterador a seguir, teoricamente, retornará todos os números ímpares.

```py
class InfIter:
    """Infinite iterator to return all
        odd numbers"""

    def __iter__(self):
        self.num = 1
        return self

    def __next__(self):
        num = self.num
        self.num += 2
        return num
```

Uma amostra de execução seria a seguinte.

```py
>>> a = iter(InfIter())
>>> next(a)
1
>>> next(a)
3
>>> next(a)
5
>>> next(a)
7
``

E assim por diante...

Tenha cuidado para incluir uma condição de finalização ao iterar sobre esse tipo de iteradores infinitos.

A vantagem de usar iteradores é que eles economizam recursos. Como mostrado acima, podemos obter todos os números ímpares sem armazenar todo o sistema numérico na memória. Podemos ter itens infinitos (teoricamente) na memória finita.

O iterador também torna nosso código legal.
