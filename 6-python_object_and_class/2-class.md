# Objetos e classe Python

Neste artigo, você aprenderá sobre as principais funcionalidades do Python, objetos e classes do Python. Você aprenderá o que é uma classe, como criá-la e usá-la em seu programa.

## O que são classes e objetos em Python?

Python é uma linguagem de programação orientada a objetos. Diferentemente da programação orientada a procedimentos, onde a ênfase principal está nas funções, a programação orientada a objetos enfatiza os objetos.

Objeto é simplesmente uma coleção de dados (variáveis) e métodos (funções) que atuam sobre esses dados. E classe é um modelo para o objeto.

Podemos pensar na classe como um esboço (protótipo) de uma casa. Ele contém todos os detalhes sobre pisos, portas, janelas, etc. Com base nessas descrições, construímos a casa. Casa é o objeto.

Como muitas casas podem ser feitas a partir de uma descrição, podemos criar muitos objetos a partir de uma classe. Um objeto também é chamado de instância de uma classe e o processo de criação desse objeto é chamado de instanciação .

## Definindo uma classe em Python

Como as definições de função começam com a palavra-chave `def`, no Python, definimos uma classe usando a palavra-chave `classe`.

A primeira string é chamada docstring e tem uma breve descrição sobre a classe. Embora não seja obrigatório, isso é recomendado.

Aqui está uma definição de classe simples.

```py
class MyNewClass:
    '''This is a docstring. I have created a new class'''
    pass
```

Uma classe cria um novo namespace local onde todos os seus atributos são definidos. Os atributos podem ser dados ou funções.

Também existem atributos especiais que começam com sublinhados duplos `__`. Por exemplo, `__doc__` nos fornece a documentação dessa classe.

Assim que definimos uma classe, um novo objeto de classe é criado com o mesmo nome. Esse objeto de classe nos permite acessar os diferentes atributos, bem como instanciar novos objetos dessa classe.

```py
class MyClass:
    "This is my second class"
    a = 10
    def func(self):
        print('Hello')

# Output: 10
print(MyClass.a)

# Output: <function MyClass.func at 0x0000000003079BF8>
print(MyClass.func)

# Output: 'This is my second class'
print(MyClass.__doc__)
```

Quando você executa o programa, a saída será:

```py
10
<function 0x7feaa932eae8="" at="" myclass.func="">
This is my second class
```

## Criando um objeto em Python

Vimos que o objeto de classe poderia ser usado para acessar diferentes atributos.

Também pode ser usado para criar novas instâncias de objetos (instanciação) dessa classe. O procedimento para criar um objeto é semelhante a uma chamada de função .

```py
>>> ob = MyClass()
```

Isso criará um novo objeto de instância chamado `ob`. Podemos acessar atributos de objetos usando o prefixo do nome do objeto.

Os atributos podem ser dados ou método. O método de um objeto são funções correspondentes dessa classe. Qualquer objeto de função que seja um atributo de classe define um método para objetos dessa classe.

Isso significa dizer que, uma vez que `MyClass.func` é um objeto de função (atributo da classe), `ob.func` será um objeto de método.

```py
class MyClass:
    "This is my second class"
    a = 10
    def func(self):
        print('Hello')

# create a new MyClass
ob = MyClass()

# Output: <function MyClass.func at 0x000000000335B0D0>
print(MyClass.func)

# Output: <bound method MyClass.func of <__main__.MyClass object at 0x000000000332DEF0>>
print(ob.func)

# Calling function func()
# Output: Hello
ob.func()
```

Você pode ter notado o parâmetro `self` na definição de função dentro da classe, mas chamamos o método simplesmente como `ob.func()` sem argumentos. Ainda funcionou.

Isso ocorre porque, sempre que um objeto chama seu método, o próprio objeto é passado como o primeiro argumento. Então, ob.`func()` traduz para `MyClass.func(ob)`.

Em geral, chamar um método com uma lista de n argumentos é equivalente a chamar a função correspondente com uma lista de argumentos criada inserindo o objeto do método antes do primeiro argumento.

Por esses motivos, o primeiro argumento da função na classe deve ser o próprio objeto. Isso é convencionalmente chamado de `self`. Pode ter outro nome, mas é altamente recomendável seguir a convenção.

Agora você deve estar familiarizado com o objeto de classe, objeto de instância, objeto de função, objeto de método e suas diferenças.

## Construtores em Python

As funções de classe que começam com sublinhado duplo `__` são chamadas de funções especiais, pois possuem um significado especial.

De um interesse particular é a `__init__()` função. Essa função especial é chamada sempre que um novo objeto dessa classe é instanciado.

Esse tipo de função também é chamado de construtores na Programação Orientada a Objetos (OOP). Nós normalmente o usamos para inicializar todas as variáveis.

```py
class ComplexNumber:
    def __init__(self,r = 0,i = 0):
        self.real = r
        self.imag = i

    def getData(self):
        print("{0}+{1}j".format(self.real,self.imag))

# Create a new ComplexNumber object
c1 = ComplexNumber(2,3)

# Call getData() function
# Output: 2+3j
c1.getData()

# Create another ComplexNumber object
# and create a new attribute 'attr'
c2 = ComplexNumber(5)
c2.attr = 10

# Output: (5, 0, 10)
print((c2.real, c2.imag, c2.attr))

# but c1 object doesn't have attribute 'attr'
# AttributeError: 'ComplexNumber' object has no attribute 'attr'
c1.attr
```

No exemplo acima, definimos uma nova classe para representar números complexos. Possui duas funções: `__init__()` inicializar as variáveis ​​(o padrão é zero) e `getData()` exibir o número corretamente.

Uma coisa interessante a ser observada na etapa acima é que os atributos de um objeto podem ser criados em tempo real. Criamos um novo atributo `attr` para o objeto `c2` e o lemos também. Mas isso não criou esse atributo para o objeto `c1`.

## Excluindo atributos e objetos

Qualquer atributo de um objeto pode ser excluído a qualquer momento, usando a instrução del. Tente o seguinte no shell Python para ver a saída.

```py
>>> c1 = ComplexNumber(2,3)
>>> del c1.imag
>>> c1.getData()
Traceback (most recent call last):
...
AttributeError: 'ComplexNumber' object has no attribute 'imag'

>>> del ComplexNumber.getData
>>> c1.getData()
Traceback (most recent call last):
...
AttributeError: 'ComplexNumber' object has no attribute 'getData'
```

Podemos até excluir o próprio objeto, usando a instrução del.

```py
>>> c1 = ComplexNumber(1,3)
>>> del c1
>>> c1
Traceback (most recent call last):
...
NameError: name 'c1' is not defined
```

Na verdade, é mais complicado do que isso. Quando o fazemos `c1 = ComplexNumber(1,3)`, um novo objeto de instância é criado na memória e o nome `c1` se liga a ele.

No comando del c1, essa ligação é removida e o nome `c1` é excluído do espaço para nome correspondente. No entanto, o objeto continua a existir na memória e, se nenhum outro nome estiver vinculado a ele, ele será destruído automaticamente mais tarde.

Essa destruição automática de objetos não referenciados no Python também é chamada de coleta de lixo.
