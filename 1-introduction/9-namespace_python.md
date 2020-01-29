# Namespace e escopo do Python

Neste artigo, você aprenderá sobre o espaço para nome; mapeamento de nomes para objetos e escopo de uma variável.

## O que é o nome em Python?

Se você já leu 'The Zen of Python' (digite "import this" no interpretador Python), a última linha declara: Namespaces are one honking great idea -- let's do more of those! Então, quais são esses namespaces misteriosos? Vamos primeiro olhar para o que é o nome.

Nome (também chamado identificador) é simplesmente um nome dado aos objetos. Tudo em Python é um objeto. Nome é uma maneira de acessar o objeto subjacente.

Por exemplo, quando fazemos a atribuição `a = 2`, aqui `2` é um objeto armazenado na memória e `a` é o nome ao qual o associamos. Podemos obter o endereço (na RAM) de algum objeto através da função built-in , `id()`. Vamos ver.

```py
# Note: You may get different value of id

a = 2
# Output: id(2)= 10919424
print('id(2) =', id(2))

# Output: id(a) = 10919424
print('id(a) =', id(a))
```

Aqui, ambos se referem ao mesmo objeto. Vamos tornar as coisas um pouco mais interessantes.

```py
# Note: You may get different value of id

a = 2

# Output: id(a) = 10919424
print('id(a) =', id(a))

a = a+1

# Output: id(a) = 10919456
print('id(a) =', id(a))

# Output: id(3) = 10919456
print('id(3) =', id(3))

b = 2

# Output: id(2)= 10919424
print('id(2) =', id(2))
```

O que está acontecendo na sequência de etapas acima? Um diagrama nos ajudará a explicar isso.

![Diagrama de memória de uma variável](/images/aEquals2.jpg)

Inicialmente, um objeto `2` é criado e o nome `a` é associado a ele; quando fazemos `a = a+1`, um novo objeto `3` é criado e agora `a` é associado a esse objeto.

Observe que `id(a)` e `id(3)` tem os mesmos valores.

Além disso, quando fazemos `b = 2`, o novo nome `b` é associado ao objeto `2` anterior.

Isso é eficiente, pois o Python não precisa criar um novo objeto duplicado. Essa natureza dinâmica da associação de nomes torna o Python poderoso; um nome pode se referir a qualquer tipo de objeto.

```py
>>> a = 5
>>> a = 'Hello World!'
>>> a = [1,2,3]
```

Todos esses são válidos e `a` se referirá a três tipos diferentes de objetos em diferentes instâncias. As funções também são objetos, portanto, um nome também pode se referir a elas.

```py
def printHello():
    print("Hello")
a = printHello()

a
# Output: Hello

```

Nosso mesmo nome `a` pode se referir a uma função e podemos chamá-la através dela, bastante elegante.

## O que é um espaço para nome em Python?

Portanto, agora que entendemos o que são nomes, podemos passar para o conceito de namespaces.

Simplificando, namespace é uma coleção de nomes.

No Python, você pode imaginar um namespace como um mapeamento de todos os nomes que você definiu para os objetos correspondentes.

Namespace diferentes podem coexistir em um determinado momento, mas são completamente isolados.

Um namespace contendo todos os nomes internos é criado quando iniciamos o interpretador Python e existe enquanto não saímos.

Esta é a razão pela qual funções internas como `id()`, `print()` , etc., estão sempre disponíveis para nós em qualquer parte do programa. Cada módulo cria seu próprio namespace global.

Esses diferentes namespaces são isolados. Portanto, o mesmo nome que pode existir em diferentes módulos não colide.

Os módulos podem ter várias funções e classes. Um namespace local é criado quando uma função é chamada, com todos os nomes definidos nela. Semelhante, é o caso da classe. O diagrama a seguir pode ajudar a esclarecer esse conceito.

![Namespaces aninhados na programação Python](/images/nested-namespaces-python.jpg)

## Escopo Variável do Python

Embora existam vários namespaces exclusivos definidos, talvez não possamos acessar todos eles de todas as partes do programa. O conceito de escopo entra em jogo.

Escopo é a parte do programa a partir da qual um espaço para nome pode ser acessado diretamente sem nenhum prefixo.

A qualquer momento, há pelo menos três escopos aninhados.

1. Escopo da função atual que possui nomes locais
2. Escopo do módulo que possui nomes globais
3. Escopo mais externo que possui nomes internos

Quando uma referência é feita dentro de uma função, o nome é pesquisado no namespace local, depois no namespace global e, finalmente, no namespace interno.

Se houver uma função dentro de outra função, um novo escopo será aninhado dentro do escopo local.

Exemplo de escopo e espaço para nome em Python

```py
def outer_function():
    b = 20
    def inner_func():
        c = 30

a = 10
```

Aqui, a variável `a` está no namespace global. Variável `b` está no namespace local `outer_function()` e `c` está no namespace local aninhado de `inner_function()`.

Quando estamos em `inner_function()`, `c` é local para nós, `b` é não-local e `a` é global. Podemos ler e atribuir novos valores a `c`, mas só podemos ler `b` e `a`  de `inner_function()`.

Se tentarmos atribuir valor para `b` , uma nova variável `b` será criada no namespace local diferente da `b` não-local . A mesma coisa acontece quando atribuir um valor para `a`.

No entanto, se declarar `a` como global, toda a referência e atribuição vão para a global `a`. Da mesma forma, se quisermos religar a variável `b`, ela deverá ser declarada como não-local. O exemplo a seguir esclarecerá mais isso.

```py
def outer_function():
    a = 20
    def inner_function():
        a = 30
        print('a =',a)

    inner_function()
    print('a =',a)
     
a = 10
outer_function()
print('a =',a)
```

Como você pode ver, a saída deste programa é

```py
a = 30
a = 20
a = 10
```

Neste programa, três variáveis ​​diferentes `a` são definidas em namespaces separados e acessadas de acordo. Enquanto no programa a seguir,

```py
def outer_function():
    global a
    a = 20
    def inner_function():
        global a
        a = 30
        print('a =',a)

    inner_function()
    print('a =',a)

a = 10
outer_function()
print('a =',a)
```

A saída do programa é.

```py
a = 30
a = 30
a = 30
```

Aqui, todas as referências e atribuições são para o global `a` devido ao uso da palavra-chave `global`.

