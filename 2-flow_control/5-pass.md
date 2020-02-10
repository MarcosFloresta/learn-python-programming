# Instrução pass do Python

Neste artigo, você aprenderá sobre a declaração de pass. É usado como um espaço reservado para implementação futura de funções, loops, etc.

## O que é uma declaração pass em Python?

Na programação Python, `pass` é uma declaração nula. A diferença entre um comentário e um `pass` instrução no Python é que, enquanto o intérprete ignora completamente um comentário, `pass` não é ignorado.

No entanto, nada acontece quando o `pass` é executado. Isso resulta em nenhuma operação (NOP).

Sintaxe de aprovação

```py
pass
```

Geralmente, o usamos como um espaço reservado.

Suponha que tenhamos um loop ou uma função que ainda não esteja implementada, mas queremos implementá-la no futuro. Eles não podem ter um corpo vazio. O intérprete reclamaria. Então, usamos a declaração `pass` para construir um corpo que não faz nada.

Exemplo: Instrução pass

```py
# pass is just a placeholder for
# functionality to be added later.
sequence = {'p', 'a', 's', 's'}
for val in sequence:
    pass
```

Podemos fazer o mesmo em uma função ou classe vazia também.

```py
def function(args):
    pass
class example:
    pass
```
