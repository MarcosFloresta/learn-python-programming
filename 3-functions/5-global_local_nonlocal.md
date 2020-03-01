# Variáveis ​​globais, locais e não-locais do Python

Neste artigo, você aprenderá sobre variável global do Python, variável local e variável não-local e onde usá-los.

## Variáveis ​​globais

No Python, uma variável declarada fora da função ou no escopo global é conhecida como variável global. Isso significa que a variável global pode ser acessada dentro ou fora da função.

Vamos ver um exemplo de como uma variável global é criada em Python.

Exemplo 1: Criar uma variável global

```py
x = "global"

def foo():
    print("x inside :", x)

foo()
print("x outside:", x)
```

Quando executamos o código, o resultado será:

```oy
x inside : global
x outside: global
```

No código acima, criamos `x` como uma variável global e definimos a `foo()` para imprimir a variável global `x` . Finalmente, chamamos o `foo()` que imprimirá o valor de `x` .

E se você quiser alterar o valor de `x` dentro de uma função?

```py
x = "global"

def foo():
    x = x * 2
    print(x)
foo()
```

Quando executamos o código, o resultado será:

```py
UnboundLocalError: local variable 'x' referenced before assignment
```

A saída mostra um erro porque Python trata `x` como uma variável local e `X` também não é definida dentro `foo()`.

Para fazer esse trabalho, usamos a palavra-chave `global`.

## Variáveis ​​locais

Uma variável declarada dentro do corpo da função ou no escopo local é conhecida como variável local.

Exemplo 2: Acessando Variável Local Fora do Escopo

```py
def foo()
    y = "local"

foo()
print(y)
```

Quando executamos o código, o resultado será:

```py
NameError: name 'y' is not defined
```

A saída mostra um erro, porque estamos tentando acessar uma variável local `y` em um escopo global, enquanto a variável local funciona apenas dentro do `foo()` ou em escopo local.

Vamos ver um exemplo de como uma variável local é criada no Python.

Exemplo 3: Criar uma variável local
Normalmente, declaramos uma variável dentro da função para criar uma variável local.

```py
def foo():
    y = "local"
    print(y)

foo()
```

Quando executamos o código, ele produzirá:

```py
local
```

Vamos dar uma olhada no problema anterior, em que `x` era uma variável global e queríamos modificar `x` por dentro `foo()`.

## Variáveis ​​globais e locais

Aqui, mostraremos como usar variáveis ​​globais e variáveis ​​locais no mesmo código.

Exemplo 4: Usando variáveis ​​globais e locais no mesmo código

```py
x = "global"

def foo():
    global x
    y = "local"
    x = x * 2
    print(x)
    print(y)

foo()
```

Quando executamos o código, o resultado será:

```py
global global
local
```

No código acima, declaramos `x` como uma variável global e `y` como uma variável local no `foo()`. Em seguida, usamos o operador de multiplicação `*` para modificar a variável global `x` e imprimimos `x` e `y`.

Após chamar o foo(), o valor de x se torna global globalporque usamos o x * 2para imprimir duas vezes global. Depois disso, imprimimos o valor da variável local y ie local.

Exemplo 5: Variável global e variável local com o mesmo nome
script.py
IPython Shell

Corre
Desenvolvido por DataCamp
Quando executamos o código, o resultado será:

local x: 10
global x: 5
No código acima, usamos o mesmo nome x para a variável global e a variável local. Obtemos resultados diferentes quando imprimimos a mesma variável porque a variável é declarada nos dois escopos, ou seja, o escopo local dentro foo()e o escopo global fora foo().

Quando imprimimos a variável dentro da foo()saída local x: 10, isso é chamado de escopo local da variável.

Da mesma forma, quando imprimimos a variável fora da foo()saída global x: 5, isso é chamado de escopo global da variável.

Variáveis ​​não-locais
Variáveis ​​não locais são usadas na função aninhada cujo escopo local não está definido. Isso significa que a variável não pode estar no escopo local nem global.

Vamos ver um exemplo de como uma variável global é criada em Python.

Usamos nonlocalpalavras-chave para criar variáveis ​​não-locais.

Exemplo 6: Criar uma variável não-local
script.py
IPython Shell

Corre
Sessão inativa
Desenvolvido por DataCamp
Quando executamos o código, o resultado será:

interno: não-local
exterior: não-local
No código acima, há uma função aninhada inner(). Usamos nonlocalpalavras-chave para criar variáveis ​​não-locais. A inner()função é definida no escopo de outra função outer().

Nota: Se alterarmos o valor da variável não local, as alterações aparecerão na variável local.