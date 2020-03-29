Objetos e classe Python
Neste artigo, você aprenderá sobre as principais funcionalidades do Python, objetos e classes do Python. Você aprenderá o que é uma classe, como criá-la e usá-la em seu programa.

O que são classes e objetos em Python?
Python é uma linguagem de programação orientada a objetos. Diferentemente da programação orientada a procedimentos, onde a ênfase principal está nas funções, a programação orientada a objetos enfatiza os objetos.

Objeto é simplesmente uma coleção de dados (variáveis) e métodos (funções) que atuam sobre esses dados. E classe é um modelo para o objeto.

Podemos pensar na classe como um esboço (protótipo) de uma casa. Ele contém todos os detalhes sobre pisos, portas, janelas, etc. Com base nessas descrições, construímos a casa. Casa é o objeto.

Como muitas casas podem ser feitas a partir de uma descrição, podemos criar muitos objetos a partir de uma classe. Um objeto também é chamado de instância de uma classe e o processo de criação desse objeto é chamado de instanciação .

Definindo uma classe em Python
Como as definições de função começam com a palavra-chave def , no Python, definimos uma classe usando a palavra-chave classe .

A primeira string é chamada docstring e tem uma breve descrição sobre a classe. Embora não seja obrigatório, isso é recomendado.

Aqui está uma definição de classe simples.

class MyNewClass:
    '''This is a docstring. I have created a new class'''
    pass
Uma classe cria um novo espaço para nome local onde todos os seus atributos são definidos. Os atributos podem ser dados ou funções.

Também existem atributos especiais que começam com sublinhados duplos (__). Por exemplo, __doc__ nos fornece a documentação dessa classe.

Assim que definimos uma classe, um novo objeto de classe é criado com o mesmo nome. Esse objeto de classe nos permite acessar os diferentes atributos, bem como instanciar novos objetos dessa classe.

script.py
IPython Shell

Corre
Desenvolvido por DataCamp
Quando você executa o programa, a saída será:

10
<function 0x7feaa932eae8 = "" at = "" myclass.func = "">
Esta é a minha segunda aula
Criando um objeto em Python
Vimos que o objeto de classe poderia ser usado para acessar diferentes atributos.

Também pode ser usado para criar novas instâncias de objetos (instanciação) dessa classe. O procedimento para criar um objeto é semelhante a uma chamada de função .

>>> ob = MyClass()
Isso criará um novo objeto de instância chamado ob . Podemos acessar atributos de objetos usando o prefixo do nome do objeto.

Os atributos podem ser dados ou método. O método de um objeto são funções correspondentes dessa classe. Qualquer objeto de função que seja um atributo de classe define um método para objetos dessa classe.

Isso significa dizer que, uma vez que MyClass.funcé um objeto de função (atributo da classe), ob.funcserá um objeto de método.

script.py
IPython Shell

Corre
Desenvolvido por DataCamp

Você pode ter notado o parâmetro auto na definição de função dentro da classe, mas chamamos o método simplesmente como ob.func()sem argumentos . Ainda funcionou.

Isso ocorre porque, sempre que um objeto chama seu método, o próprio objeto é passado como o primeiro argumento. Então, ob.func()traduz para MyClass.func(ob).

Em geral, chamar um método com uma lista de n argumentos é equivalente a chamar a função correspondente com uma lista de argumentos criada inserindo o objeto do método antes do primeiro argumento.

Por esses motivos, o primeiro argumento da função na classe deve ser o próprio objeto. Isso é convencionalmente chamado de eu . Pode ter outro nome, mas é altamente recomendável seguir a convenção.

Agora você deve estar familiarizado com o objeto de classe, objeto de instância, objeto de função, objeto de método e suas diferenças.

Construtores em Python
As funções de classe que começam com sublinhado duplo (__) são chamadas de funções especiais, pois possuem um significado especial.

De um interesse particular é a __init__()função. Essa função especial é chamada sempre que um novo objeto dessa classe é instanciado.

Esse tipo de função também é chamado de construtores na Programação Orientada a Objetos (OOP). Nós normalmente o usamos para inicializar todas as variáveis.

script.py
IPython Shell

Corre
Desenvolvido por DataCamp
No exemplo acima, definimos uma nova classe para representar números complexos. Possui duas funções: __init__()inicializar as variáveis ​​(o padrão é zero) e getData()exibir o número corretamente.

Uma coisa interessante a ser observada na etapa acima é que os atributos de um objeto podem ser criados em tempo real. Criamos um novo atributo attr para o objeto c2 e o lemos também. Mas isso não criou esse atributo para o objeto c1 .

Excluindo atributos e objetos
Qualquer atributo de um objeto pode ser excluído a qualquer momento, usando a instrução del. Tente o seguinte no shell Python para ver a saída.

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
Podemos até excluir o próprio objeto, usando a instrução del.

>>> c1 = ComplexNumber(1,3)
>>> del c1
>>> c1
Traceback (most recent call last):
...
NameError: name 'c1' is not defined
Na verdade, é mais complicado do que isso. Quando o fazemos c1 = ComplexNumber(1,3), um novo objeto de instância é criado na memória e o nome c1 se liga a ele.

No comando del c1, essa ligação é removida e o nome c1 é excluído do espaço para nome correspondente. No entanto, o objeto continua a existir na memória e, se nenhum outro nome estiver vinculado a ele, ele será destruído automaticamente mais tarde.

Essa destruição automática de objetos não referenciados no Python também é chamada de coleta de lixo.