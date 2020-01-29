# Instrução if ... else em Python

Neste artigo, você aprenderá a criar decisões em um programa Python usando diferentes formas de instrução if..else.

## O que são as declarações if ... else em Python?

A tomada de decisão é necessária quando queremos executar um código apenas se uma determinada condição for atendida.

A declaração `if…elif…else` é usada no Python para tomada de decisão.

Sintaxe da instrução if Python if

```py
if test expression:
    statement(s)
```

Aqui, o programa avalia as `test expression` e executará (s) apenas se a `test expression` for True.

Se a `test expression` for False, a instrução não será executada.

Em Python, o corpo da instrução if é indicado pelo recuo. O corpo começa com um recuo e a primeira linha sem indentação marca o fim.

Python interpreta valores diferentes de zero como True. Nonee 0são interpretados como False.

Fluxograma de instrução if

![Fluxograma da instrução if na programação Python](/images/Python_if_statement.jpg)

Exemplo: Python if Statement

```py
# If the number is positive, we print an appropriate message

num = 3
if num > 0:
    print(num, "is a positive number.")
print("This is always printed.")

num = -1
if num > 0:
    print(num, "is a positive number.")
print("This is also always printed.")
```

Quando você executa o programa, a saída será:

```py
3 is a positive number
This is always printed
This is also always printed.

```

No exemplo acima, `num > 0` é a expressão de teste.

O corpo de `if` é executado apenas se for avaliado como True.

Quando a variável `num` é igual a `3`, a expressão de teste é verdadeira e o corpo dentro do corpo de `if` é executado.

Se a variável `num` for igual a `-1`, a expressão de teste será falsa e o corpo dentro do corpo `if` será ignorado.

A declaração `print()` fica fora do bloco if (sem indentação). Portanto, é executado independentemente da expressão de teste.

## Instrução if ... else

Sintaxe de if ... else

```py
if test expression:
    Body of if
else:
    Body of else
```

A instrução `if..else` avalia `test expression` e executará o corpo `if` somente quando a condição de teste estiver `True`.

Se a condição for `False`, o corpo de `else` é executado. Recuo é usado para separar os blocos.

Fluxograma if..else
![Fluxograma da instrução if ... else na Programação em Python](/images/Python_if_else_statement.jpg)

Exemplo de if ... else

```py
# Program checks if the number is positive or negative
# And displays an appropriate message

num = 3

# Try these two variations as well.
# num = -5
# num = 0

if num >= 0:
    print("Positive or Zero")
else:
    print("Negative number")
```

No exemplo acima, quando `num` é igual a `3`, a expressão de teste é verdadeira e o corpo de `if` é executado e o corpo de else é ignorado.

Se `num` for igual a `-5`, a expressão de teste será falsa e o corpo de `else` será executado e o corpo de `if` será ignorado.

Se `num` for igual a `0`, a expressão de teste é verdadeira e o corpo de `if` é executado e o corpo de else é ignorado.

## Instrução if ... elif ... else

Sintaxe de if ... elif ... else

```py
if test expression:
    Body of if
elif test expression:
    Body of elif
else:
    Body of else
```

O `elif` é curto para else if. Ele nos permite verificar várias expressões.

Se a condição for `if` for `False`, ele verifica a condição do próximo bloco `elif` e assim por diante.

Se todas as condições forem `False`, o corpo de `else` é executado.

Apenas um bloco entre os vários blocos `if...elif...else` é executado de acordo com a condição.

O bloco `if` pode ter apenas um bloco `else`. Mas pode ter vários blocos `elif`.

Fluxograma de if ... elif ... else

![Fluxograma de if ... elif .... else na programação python](/images/Python_if_elif_else_statement.jpg)

Exemplo de if ... elif ... else

```py
# In this program,
# we check if the number is positive or
# negative or zero and
# display an appropriate message

num = 3.4

# Try these two variations as well:
# num = 0
# num = -4.5

if num > 0:
    print("Positive number")
elif num == 0:
    print("Zero")
else:
    print("Negative number")
```

Quando a variável `num` é positiva, *Positive number* é impresso.

Se `num` for igual a `0`, *Zero* é impresso.

Se `num` for negativo, *Negative number* é impresso

## Instruções If aninhadas em Python

Podemos ter uma declaração if...elif...else dentro de outra declaração if...elif...else. Isso é chamado de aninhamento na programação de computadores.

Qualquer número dessas instruções pode ser aninhado um dentro do outro. O recuo é a única maneira de descobrir o nível de aninhamento. Isso pode ficar confuso, portanto deve ser evitado se pudermos.

Python aninhado se exemplo

```py
# In this program, we input a number
# check if the number is positive or
# negative or zero and display
# an appropriate message
# This time we use nested if
num = float(input("Enter a number: "))
if num >= 0:
    if num == 0:
        print("Zero")
    else:
        print("Positive number")
else:
    print("Negative number")
```

Output 1

```py
Enter a number: 5
Positive number
```

Output 2

```py
Enter a number: -1
Negative number
```

Output 3

```py
Enter a number: 0
Zero
```
