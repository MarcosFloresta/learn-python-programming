# Variáveis, constantes e literais Python

Neste artigo, você aprenderá sobre variáveis, constantes, literais e seus casos de uso Python.

## Variáveis ​​Python

Uma variável é um local nomeado usado para armazenar dados na memória. É útil pensar nas variáveis ​​como um contêiner que contém dados que podem ser alterados posteriormente durante a programação. Por exemplo,

```py
number = 10
```

Aqui, criamos um `number` nomeado . Atribuímos o valor 10 à variável.

Você pode pensar em variável como uma sacola para armazenar livros nela e esses livros podem ser substituídos a qualquer momento.

```py
number = 10
number = 1.1
```

Inicialmente, o valor do `number` era 10. Depois, é alterado para 1.1.

Nota: No Python, não atribuímos valores às variáveis, enquanto o Python fornece a referência do objeto (valor) à variável.

## Atribuindo um valor a uma variável em Python

Como você pode ver no exemplo acima, você pode usar o operador de atribuição `=` para atribuir um valor a uma variável.

Exemplo 1: Declarando e atribuindo um valor a uma variável

```py
website = "apple.com"
print(website)
```

Quando você executa o programa, a saída será:

```py
apple.com
```

No programa acima, atribuímos um valor `apple.com` ao `website` variável . Em seguida, imprimimos o valor atribuído ao `website`, ou seja, `apple.com`

Nota: Python é uma linguagem inferida por tipo; ele pode saber automaticamente que  `apple.com` é uma string e declarar `website` como uma string.

Exemplo 2: Alterando o valor de uma variável

```py
website = "apple.com"
print(website)

#assigning a new variable to website
website = "google.com'
print(website)
```

Quando você executa o programa, a saída será:

```py
apple.com
google.com
```

No programa acima, atribuímos `apple.com` a variável `website` inicialmente. Então, seu valor é alterado para `google.com`.

Exemplo 3: Designando Vários Valores a Diversas Variáveis

```py
a, b, c = 5, 3.2, "Hello"

print(a)
print(b)
print(c)
```

Se queremos atribuir o mesmo valor a várias variáveis ​​de uma só vez, podemos fazer isso da seguinte maneira:

```py
x = y = z = "same"

print(x)
print(y)
print(z)
```

O segundo programa atrubui a string "same" para todas as três variáveis x , y e z .

## Constantes

Uma constante é um tipo de variável cujo valor não pode ser alterado. É útil pensar nas constantes como contêineres que contêm informações que não podem ser alteradas posteriormente.

Tecnicamente, você pode pensar em constante como uma sacola para guardar alguns livros e esses livros não podem ser substituídos uma vez colocados dentro da sacola.

### Atribuindo valor a uma constante em Python

No Python, as constantes geralmente são declaradas e atribuídas em um módulo. Aqui, o módulo significa um novo arquivo contendo variáveis, funções, etc, que é importado para o arquivo principal. Dentro do módulo, as constantes são escritas em letras maiúsculas e sublinhados que separam as palavras.

Exemplo 4: Declarando e atribuindo valor a uma constante
Crie um constant.py

```py
PI = 3.14
GRAVITY = 9.8
```

Crie um main.py

```py
import constant
print(constant.PI)
print(constant.GRAVITY)
```

Quando você executa o programa, a saída será:

```py
3,14
9,8
```

No programa acima, criamos um arquivo de módulo constant.py. Em seguida, atribuímos o valor constante a `PI` e `GRAVITY`. Depois disso, criamos um arquivo main.py e importamos o módulo constante. Finalmente, imprimimos o valor constante.

Nota: Na realidade, não usamos constantes no Python. O módulo globals ou constantes é usado em todos os programas Python.

## Regras e Convenção de Nomenclatura para Variáveis ​​e Constantes

1. Os nomes de constantes e variáveis ​​devem ter uma combinação de letras em minúsculas (a a z) ou maiúsculas (A a Z) ou dígitos (0 a 9) ou um sublinhado (_). Por exemplo:

    ```py
    snake_case
    MACRO_CASE
    camelCase
    CapWords
    ```

2. Crie um nome que faça sentido. Por exemplo,  vogal faz mais sentido que v .
3. Se você deseja criar um nome de variável com duas palavras, use sublinhado para separá-las. Por exemplo:

    ```py
    my_name
    current_salary
    ```

4. Use letras maiúsculas possíveis para declarar uma constante. Por exemplo:

   ```py
    PI
    G
    MASSA
    VELOCIDADE DA LUZ
    TEMP
    ```

5. Nunca use símbolos especiais como!, @, #, $,% Etc.
6. Não inicie um nome de variável com um dígito.

## Literais

Literal é um dado bruto fornecido em uma variável ou constante. No Python, existem vários tipos de literais, eles são os seguintes:

### Literais Numéricos

Os literais numéricos são imutáveis ​​(imutáveis). Literais numéricos podem pertencer a 3 tipos numéricos diferentes Inteiro, Flutuante e Complexo.

Exemplo 5: Como usar literais numéricos em Python?

```py
a = 0b1010 #Binary Literals
b = 100 #Decimal Literal
c = 0o310 #Octal Literal
d = 0x12c #Hexadecimal Literal

#Float Literal
float_1 = 10.5
float_2 = 1.5e2

#Complex Literal
x = 3.14j

print(a, b, c, d)
print(float_1, float_2)
print(x, x.imag, x.real)
```

Quando você executa o programa, a saída será:

```py
10 100 200 300
10,5 150,0
3,14j 3,14 0,0
```

No programa acima,

- Atribuímos literais inteiros em diferentes variáveis. Aqui, `a` é um literal binário, `b` é um literal decimal, `c` é um literal octal e `d` é um literal hexadecimal.
- Quando imprimimos as variáveis, todos os literais são convertidos em valores decimais.
- 10.5 e 1.5e2 são literais de ponto flutuante. 1.5e2 é expresso com exponencial e é equivalente a `1,5 * 10^2` .
- Atribuímos um literal complexo, isto é, 3,14j na variável x. Em seguida, usamos literal imaginário (x.imag) e literal real (x.real) para criar parte imaginária e real de um número complexo.
  
Para saber mais sobre literais numéricos, consulte  Python Numbers .

### Literais de string

Um literal de string é uma sequência de caracteres entre aspas. Podemos usar aspas simples, duplas ou triplas para uma string. E, um literal de caractere é um caractere único cercado por aspas simples ou duplas.

Exemplo 6: Como usar literais de string em Python?

```py
strings = "This is Python"
char = "C"
multiline_str = """This is a multiline string with more than one line code."""
unicode = u"\u00dcnic\u00f6de"
raw_str = r"raw \n string"

print(strings)
print(char)
print(multiline_str)
print(unicode)
print(raw_str)
```

Quando você executa o programa, a saída será:

```py
This is Python
C
This is a multiline string with more than one line code.
Ünicöde
raw \n string
```

No programa acima, `This is Python` é uma string literal e `C` um caractere literal. O valor com aspas triplas `"""` atribuído no `multiline_str` é literal de cadeia de várias linhas. O `u"\u00dcnic\u00f6de"` é um literal unicode que suporta caracteres diferentes do inglês e `r"raw \n string"` é um literal de string bruto.

### Literais booleanos

Um literal booleano pode ter qualquer um dos dois valores: Trueou False.

Exemplo 7: Como usar literais booleanos em Python?

```py
x = (1 == True)
y = (1 == False)
a = True + 4
b = False + 10

print("x is", x)
print("y is", y)
print("a:", a)
print("b:", b)
```

Quando você executa o programa, a saída será:

```py
x is True
y is False
a: 5
b: 10
```

No programa acima, usamos literal booleano `Truee` e `False`. No Python, `True` representa o valor como `1` e `False` como `0`. O valor de `x` é `True` porque `1` é igual a `True`. E, o valor de `y` é `False` porque `1` não é igual a `False`.

Da mesma forma, podemos usar o `True` e `False` em expressões numéricas como o valor. O valor de `a` é `5` porque adicionamos o `True` como valor de `1` com `4`. Da mesma forma, `b` é `10` porque adicionamos o `False` como valor de ter `0` com `10`.

### Literais especiais

Python contém um literal especial, `None`. Nós o usamos para especificar para aquele campo que não é criado.

Exemplo 8: Como usar literais especiais em Python?

```py
drink = "Available"
food = None

def menu(x):
    if x == drink:
        print(drink)
    else:
        print(food)

menu(drink)
menu(food)
```

Quando você executa o programa, a saída será:

```py
Available
None
```

No programa acima, definimos uma função `mwnu`. Dentro de `menu`, quando definimos o parâmetro como `drink` então, ele é exibido `Available`. E, quando o parâmetro é `food`, ele é exibido `None`.

### Coleções literais

Existem quatro coleções literais diferentes: List literals, Tuple literals, Dict literals ,e Set literals.

Exemplo 9: Como usar coleções literais em Python?

```py
fruits = ["apple", "mango", "orange"] #list
numbers = (1, 2, 3) #tuple
alphabets = {'a':'apple', 'b':'ball', 'c':'cat'} #dictionary
vowels = {'a', 'e', 'i' , 'o', 'u'} #set

print(fruits)
print(numbers)
print(alphabets)
print(vowels)
```

Quando você executa o programa, a saída será:

```py
['apple', 'mango', 'orange']
(1, 2, 3)
{'a': 'apple', 'b': 'ball', 'c': 'cat'}
{'e', 'a', 'o', 'i', 'u'}
```

No programa acima, criamos uma lista de `fruits`, tuple de `numbers` , dicionário `dict` com valores com chaves desginadas para cada valor e conjunto de `vowels`.
