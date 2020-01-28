# Operadores Python

Neste artigo, você aprenderá tudo sobre os diferentes tipos de operadores no Python, sua sintaxe e como usá-los com exemplos.

## O que são operadores em python

Operadores são símbolos especiais em Python que executam cálculos aritméticos ou lógicos. O valor em que o operador opera é chamado de operando.

Por exemplo:

```py
>>> 2+3
5
```

Aqui, `+` é o operador que executa a adição. `2` e `3` são os operandos e `5` é a saída da operação.

## Operadores aritméticos

Operadores aritméticos são usados ​​para executar operações matemáticas como adição, subtração, multiplicação, etc.

Operadores aritméticos em Python
| Operador | Significado | Exemplo |
| --- | --- | --- |
| `+` | Adicione dois operandos ou mais unário | x + y; +2 |
| `-` | Subtrair operando direito da esquerda ou unário menos | x - y; -2 |
| `*` | Multiplica dois operandos | x * y |
| `/` | Divida o operando esquerdo pelo direito (sempre resulta em flutuação) | x / y |
| `%` | Módulo - restante da divisão do operando esquerdo pelo direito | x % y (restante de x / y) |
| `//` | Divisão de piso - divisão que resulta em um número inteiro ajustado à esquerda na linha numérica | x // y |
| `**` | Expoente - operando esquerdo elevado à potência do direito | x ** y (x para a potência y) |

Exemplo #1: Operadores aritméticos em Python

```py
x = 15
y = 4
# Output: x + y = 19
print('x + y =',x+y)
# Output: x - y = 11
print('x - y =',x-y)
# Output: x * y = 60
print('x * y =',x*y)
# Output: x / y = 3.75
print('x / y =',x/y)
# Output: x // y = 3
print('x // y =',x//y)
# Output: x ** y = 50625
print('x ** y =',x**y)
```

Quando você executa o programa, a saída será:

```py
x + y = 19
x - y = 11
x * y = 60
x / y = 3,75
x // y = 3
x ** y = 50625
```

## Operadores de comparação

Operadores de comparação são usados ​​para comparar valores. Ele retorna `True` ou `False` de acordo com a condição.

Operadores de comparação em Python
| Operador | Significado | Exemplo |
| --- | --- | --- |
| `>` | Maior que - Verdadeiro se o operando esquerdo for maior que o direito | x > y |
| `<` | Menor que - Verdadeiro se o operando esquerdo for menor que o direito | x < y |
| `==` | Igual a - Verdadeiro se os dois operandos forem iguais | x == y |
| `!=` | Diferente de - Verdadeiro se operandos não forem iguais | x != y |
| `>=` | Maior que ou igual a - True se o operando esquerdo for maior que ou igual à direita | x >= y |
| `<=` | Menor ou igual a - True se o operando esquerdo for menor ou igual à direita | x <= y |

Exemplo #2: Operadores de comparação em Python

```py
x = 10
y = 12
# Output: x > y is False
print('x > y  is',x>y)
# Output: x < y is True
print('x < y  is',x<y)
# Output: x == y is False
print('x == y is',x==y)
# Output: x != y is True
print('x != y is',x!=y)
# Output: x >= y is False
print('x >= y is',x>=y)
# Output: x <= y is True
print('x <= y is',x<=y)
```

## Operadores lógicos

Os operadores lógicos são os operadores `and`, `or` e `not`.

Operadores lógicos em Python
| Operador | Significado | Exemplo |
| --- | --- | --- |
| `and` | Verdadeiro se ambos os operandos forem verdadeiros | x and y |
| `or` | Verdadeiro se um dos operandos for verdadeiro | x or y |
| `not` | Verdadeiro se o operando for falso (complementa o operando) | not x |

Exemplo #3: Operadores lógicos em Python

```py
x = True
y = False

print('x and y is',x and y)
# Output: x and y is False
print('x or y is',x or y)
# Output: x or y is True
print('not x is',not x)
# Output: not x is False
```

## Operadores bit a bit

Os operadores bit a bit atuam nos operandos como se fossem uma sequência de dígitos binários. Opera pouco a pouco, daí o nome.

Por exemplo, 2 é `10` em binário e 7 é `111`.

Na tabela abaixo: Seja x = 10 (`0000 1010` em binário) e y = 4 (`0000 0100` em binário)

Operadores bit a bit em Python
| Operador | Significado | Exemplo |
| --- | --- | --- |
| `&` | AND bit a bit | x & y = 0 ( 0000 0000) |
| `|` | OR bit a bit | x y = 14 ( 0000 1110) |
| `~` | NOT bit a bit | ~ x = -11 ( 1111 0101) |
| `^` | XOR bit a bit | x ^ y = 14 ( 0000 1110) |
| `>>` |Deslocamento à direita bit a bit | x >> 2 = 2 ( 0000 0010) |
| `<<` | Deslocamento à esquerda bit a bit | x << 2 = 40 ( 0010 1000) |

## Operadores de atribuição

Operadores de atribuição são usados ​​no Python para atribuir valores a variáveis.

`a = 5` é um operador de atribuição simples que atribui o valor `5` à direita à variável `a` à esquerda.

Existem vários operadores compostos no Python assim a += 5adicionados à variável e posteriormente atribuídos à mesma. É equivalente a a = a + 5.

Operadores de atribuição em Python
| Operador | Exemplo | Equivalente a |
| :---: | :---: | :---: |
| = | x = 5 | x = 5 |
| += | x += 5 | x = x + 5 |
| -= | x -= 5 | x = x - 5 |
| *= | x *= 5 | x = x * 5 |
| /= | x /= 5 | x = x / 5 |
| %= | x %= 5 | x = x % 5 |
| //= | x //= 5 | x = x // 5 |
| **= | x **= 5 | x = x ** 5 |
| &= | x &= 5 | x = x & 5 |
| \|= | x \|= 5 | x = x \| 5 |
| ^= | x ^= 5 | x = x ^ 5 |
| >>= | x >>= 5 | x = x >> 5 |
| <<= | x <<= 5 | x = x << 5 |

## Operadores especiais

A linguagem Python oferece alguns tipos especiais de operadores, como o operador de identidade ou o operador de associação. Eles são descritos abaixo com exemplos.

### Operadores de identidade

`is` e `is not` são os operadores de identidade em Python. Eles são usados ​​para verificar se dois valores (ou variáveis) estão localizados na mesma parte da memória. Duas variáveis ​​iguais não significam que sejam idênticas.

Operadores de identidade em Python
| Operador | Significado | Exemplo |
| --- | --- | --- |
| is | Verdadeiro se os operandos forem idênticos (consulte o mesmo objeto) | x is True |
| is not | Verdadeiro se os operandos não forem idênticos (não se refiram ao mesmo objeto) | x is not True |

Exemplo #4: Operadores de identidade em Python

```py
x1 = 5
y1 = 5
x2 = 'Hello'
y2 = 'Hello'
x3 = [1,2,3]
y3 = [1,2,3]
# Output: False
print(x1 is not y1)
# Output: True
print(x2 is y2)
# Output: False
print(x3 is y3)
```

Aqui, vemos que `x1` e `y1` são números inteiros dos mesmos valores, portanto, são iguais e idênticos. O mesmo acontece com `x2` e `y2` (strings).

Mas `x3` e `y3` são lista. Eles são iguais, mas não idênticos. Isso ocorre porque o intérprete os localiza separadamente na memória, embora sejam iguais.

### Operadores de associação

`in` e `not in` são os operadores de associação no Python. Eles são usados ​​para testar se um valor ou variável é encontrado em uma sequência (string , list, tuple, set e dictionary).

Em um dicionário, podemos apenas testar a presença da chave, não o valor.

| Operador | Significado | Exemplo |
| --- | --- | --- |
| in | Verdadeiro se valor / variável for encontrado na sequência | 5 in x |
| not in | Verdadeiro se valor / variável não for encontrado na sequência | 5 não em x |

Exemplo # 5: Operadores de associação em Python

```py
x = 'Hello world'
y = {1:'a',2:'b'}
# Output: True
print('H' in x)
# Output: True
print('hello' not in x)
# Output: True
print(1 in y)
# Output: False
print('a' in y)
```

Aqui, `'H'` está em `x`, mas `'hello'` não está presente em `x` (lembre-se, Python faz distinção entre maiúsculas e minúsculas). Similar, `1` é a chave e `'a'` é o valor no dicionário `y` . Portanto, `'a' in y` retorna `False`.
