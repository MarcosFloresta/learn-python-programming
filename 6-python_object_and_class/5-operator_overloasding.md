# Sobrecarga do operador Python

Você pode alterar o significado de um operador no Python, dependendo dos operandos usados. Essa prática é conhecida como sobrecarga operacional.

## O que é sobrecarga de operador em Python?

Operadores Python trabalham para classes internas. Mas o mesmo operador se comporta de maneira diferente com tipos diferentes. Por exemplo, o  `+` executará adição aritmética em dois números, mesclará duas listas e concatenará duas seqüências.

Esse recurso no Python, que permite que o mesmo operador tenha significado diferente de acordo com o contexto, é chamado de sobrecarga do operador.

Então, o que acontece quando os usamos com objetos de uma classe definida pelo usuário? Vamos considerar a seguinte classe, que tenta simular um ponto no sistema de coordenadas 2D.

```py
class Point:
    def __init__(self, x = 0, y = 0):
        self.x = x
        self.y = y
```

Agora, execute o código e tente adicionar dois pontos no shell do Python.

```py
>>> p1 = Point(2,3)
>>> p2 = Point(-1,2)
>>> p1 + p2
Traceback (most recent call last):
...
TypeError: unsupported operand type(s) for +: 'Point' and 'Point'
```

Uau! Isso é um monte de reclamações. `TypeError` foi criado porque o Python não sabia como adicionar dois objetos `Point` juntos.

No entanto, a boa notícia é que podemos ensinar isso ao Python através da sobrecarga do operador. Mas primeiro, vamos ter uma noção sobre funções especiais.

## Funções especiais em Python

As funções de classe que começam com sublinhado duplo __ são chamadas de funções especiais no Python. Isso ocorre porque, bem, eles não são comuns. A função `__init__()` que definimos acima, é uma delas. É chamado toda vez que criamos um novo objeto dessa classe. Existem inúmeras funções especiais no Python`.

Usando funções especiais, podemos tornar nossa classe compatível com funções internas.

```py
>>> p1 = Point(2,3)
>>> print(p1)
<__main__.Point object at 0x00000000031F8CC0>
```

Isso não foi bem impresso. Mas se definirmos o método `__str__()` em nossa classe, poderemos controlar como ele será impresso. Então, vamos adicionar isso à nossa classe.

```py
class Point:
    def __init__(self, x = 0, y = 0):
        self.x = x
        self.y = y
    
    def __str__(self):
        return "({0},{1})".format(self.x,self.y)
```

Agora vamos tentar a print()função novamente.

```py
>>> p1 = Point(2,3)
>>> print(p1)
(2,3)
```

Isso é melhor. Acontece que esse mesmo método é chamado quando usamos a função interna `str()` ou `format()`.

```py
>>> str(p1)
'(2,3)'

>>> format(p1)
'(2,3)'
```

Então, quando você faz `str(p1)` ou `format(p1)`, Python está fazendo internamente `p1.__str__()`. Daí o nome, funções especiais.

Ok, agora voltemos à sobrecarga do operador.

## Sobrecarregando o operador + em Python

Para sobrecarregar o  sinal `+`, precisaremos implementar a função `__add__()` na classe. Com grandes poderes vem grandes responsabilidades. Podemos fazer o que quisermos dentro desta função. Mas é sensato retornar um objeto `Point` da soma de coordenadas.

```py
class Point:
    def __init__(self, x = 0, y = 0):
        self.x = x
        self.y = y

    def __str__(self):
        return "({0},{1})".format(self.x,self.y)

    def __add__(self,other):
        x = self.x + other.x
        y = self.y + other.y
        return Point(x,y)
```

Agora vamos tentar essa adição novamente.

```py
>>> p1 = Point(2,3)
>>> p2 = Point(-1,2)
>>> print(p1 + p2)
(1,5)
```

O que realmente acontece é que, quando o fizer `p1 + p2`, o Python chamará o `p1.__add__(p2)` que, por sua vez, é `Point.__add__(p1,p2)`. Da mesma forma, também podemos sobrecarregar outros operadores. A função especial que precisamos implementar está tabulada abaixo.

Operador sobrecarregando funções especiais em Python
| Operador | Expressão | Internamente |
| --- | --- | --- |
| Adição | p1 + p2 | `p1.__adicione__(p2)` |
| Subtração| p1 - ​​p2 | `p1.sub__(p2)` |
| Multiplicação | p1 * p2 | `p1.__mul__(p2)` |
| Poder | p1 ** p2 | `p1.__pow__(p2)` |
| Divisão | p1 / p2 | `p1.__truediv__(p2)` |
| Divisão Floor | p1 // p2 | `p1.__floordiv__(p2)` |
| Restante (módulo)| p1 % p2 | `p1.__mod__(p2)` |
| Deslocamento à esquerda bit a bit | p1 << p2 | `p1.__lshift__(p2)` |
| Deslocamento à direita bit a bit | p1 >> p2 | `p1.__rshift__(p2)` |
| AND bit a bit | p1 & p2 | `p1.__e__(p2)` |
| OR bit a bit| p1 \| p2 | `p1.__ou__(p2)` |
| Bitwise XOR | p1 ^ p2 | `p1.__xor__(p2)` |
| Bitwise NOT | ~ p1 | `p1.__inverter__()` |

## Sobrecarregando operadores de comparação em Python

O Python não limita a sobrecarga do operador apenas aos operadores aritméticos. Também podemos sobrecarregar os operadores de comparação.

Suponha que desejássemos implementar o símbolo menor que o símbolo `<` em nossa classe `Point`.

Vamos comparar a magnitude desses pontos da origem e retornar o resultado para esse fim. Pode ser implementado da seguinte maneira.

```py
class Point:
    def __init__(self, x = 0, y = 0):
        self.x = x
        self.y = y
    
    def __str__(self):
        return "({0},{1})".format(self.x,self.y)
    
    def __lt__(self,other):
        self_mag = (self.x ** 2) + (self.y ** 2)
        other_mag = (other.x ** 2) + (other.y ** 2)
        return self_mag < other_mag
```

Experimente estas amostras executadas no shell Python.

```py
>>> Point(1,1) < Point(-2,-3)
True

>>> Point(1,1) < Point(0.5,-0.2)
False

>>> Point(1,1) < Point(1,1)
False
```

Da mesma forma, as funções especiais que precisamos implementar, para sobrecarregar outros operadores de comparação, estão tabuladas abaixo.

Sobrecarga de operador de comparação em Python
| Operador | Expressão | Internamente |
| --- | --- | --- |
| Menor que | p1 < p2 | `p1.__lt__(p2)` |
| Menos que ou igual a | p1 <= p2 | `p1.__le__(p2)` |
| Igual a | p1 == p2 | `p1.__eq__(p2)` |
| Diferente de | p1 != p2 | `p1.__ne__(p2)` |
| Maior que | p1 > p2 | `p1.__gt__(p2)` |
| Melhor que ou igual a | p1 >= p2 | `p1.__ge__(p2)` |
