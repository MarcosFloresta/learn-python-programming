# Herança Múltipla em Python

Neste artigo, você aprenderá o que é herança múltipla no Python e como usá-la em seu programa. Você também aprenderá sobre a herança multinível e a ordem de resolução do método.

Como o C ++, uma classe pode ser derivada de mais de uma classe base no Python. Isso é chamado de herança múltipla.

Na herança múltipla, os recursos de todas as classes base são herdados na classe derivada. A sintaxe da herança múltipla é semelhante à herança única .

```py
Exemplo
class Base1:
    pass

class Base2:
    pass

class MultiDerived(Base1, Base2):
    pass
```

Aqui, o `MultiDerived` é derivado das classes `Base1` e `Base2`.

![Herança Múltipla em Python](/images/MultipleInheritance.jpg)

A classe `MultiDerived` herda de ambos `Base1` e `Base2`.

## Herança multinível em Python

Por outro lado, também podemos herdar de uma classe derivada. Isso é chamado de herança multinível. Pode ser de qualquer profundidade em Python.

Na herança multinível, os recursos da classe base e da classe derivada são herdados na nova classe derivada.

Um exemplo com a visualização correspondente é dado abaixo.

```py
class Base:
    pass

class Derived1(Base):
    pass

class Derived2(Derived1):
    pass
```

Aqui, Derivado1 é derivado de Base e Derivado2 é derivado de Derivado1 .

![Herança multinível em Python](/images/MultilevelInheritance.jpg)

## Ordem de resolução de método em Python

Toda classe no Python é derivada da classe `object`. É o tipo mais básico em Python.

Portanto, tecnicamente, todas as outras classes, internas ou definidas pelo usuário, são classes derivadas e todos os objetos são instâncias da classe `object`.

```py
# Output: True
print(issubclass(list,object))

# Output: True
print(isinstance(5.5,object))

# Output: True
print(isinstance("Hello",object))
```

No cenário de herança múltipla, qualquer atributo especificado é pesquisado primeiro na classe atual. Se não for encontrada, a pesquisa continuará nas classes pai de maneira aprofundada, esquerda-direita, sem pesquisar a mesma classe duas vezes.

Assim, no exemplo acima de classe `MultiDerived` a ordem de pesquisa é `[ MultiDerived, Base1, Base2, object]`. Essa ordem também é chamada de linearização de MultiDerivedclasse e o conjunto de regras usado para encontrar essa ordem é chamado MRO (Method Resolution Order) .

O MRO deve impedir a ordem de precedência local e também fornecer monotonicidade. Ele garante que uma classe sempre apareça diante de seus pais e, no caso de vários pais, a ordem é igual à tupla das classes base.

O MRO de uma classe pode ser visto como o atributo `__mro__` ou método `mro()`. O primeiro retorna uma tupla, enquanto o último retorna uma lista.

```py
>>> MultiDerived.__mro__
(<class '__main__.MultiDerived'>,
 <class '__main__.Base1'>,
 <class '__main__.Base2'>,
 <class 'object'>)

>>> MultiDerived.mro()
[<class '__main__.MultiDerived'>,
 <class '__main__.Base1'>,
 <class '__main__.Base2'>,
 <class 'object'>]
 ```

Aqui está um exemplo de herança múltipla um pouco mais complexo e sua visualização junto com o MRO.

1[Visualização de herança múltipla](/images/MRO.jpg)

```py
class X: pass
class Y: pass
class Z: pass

class A(X,Y): pass
class B(Y,Z): pass

class M(B,A,Z): pass

# Output:
# [<class '__main__.M'>, <class '__main__.B'>,
# <class '__main__.A'>, <class '__main__.X'>,
# <class '__main__.Y'>, <class '__main__.Z'>,
# <class 'object'>]

print(M.mro())
```
