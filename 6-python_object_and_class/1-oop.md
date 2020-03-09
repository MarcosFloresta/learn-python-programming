# Programação Orientada a Objetos em Python

Neste artigo, você aprenderá sobre a Programação Orientada a Objetos (OOP) em Python e seu conceito fundamental com exemplos.

## Introdução aos OOPs em Python

Python é uma linguagem de programação com vários paradigmas. Ou seja, ele suporta diferentes abordagens de programação.

Uma das abordagens populares para resolver um problema de programação é criar objetos. Isso é conhecido como Programação Orientada a Objetos (OOP).

Um objeto tem duas características:

- atributos
- comportamento

Vamos dar um exemplo:

Papagaio é um objeto,
- nome, idade, cor são atributos
- cantar, dançar é comportamento

O conceito de OOP no Python se concentra na criação de código reutilizável. Esse conceito também é conhecido como DRY (Don't Repeat Yourself).

Em Python, o conceito de POO segue alguns princípios básicos:

| | |
| --- | --- |
| Herança | Um processo de uso de detalhes de uma nova classe sem modificar a classe existente. |
| Encapsulamento | Ocultando os detalhes particulares de uma classe de outros objetos. |
| Polimorfismo | Um conceito de uso de operação comum de maneiras diferentes para entrada de dados diferentes. |

## Class

Uma classe é um blueprint para o objeto.

Podemos pensar na classe como um esboço de um papagaio com rótulos. Ele contém todos os detalhes sobre o nome, cores, tamanho, etc. Com base nessas descrições, podemos estudar sobre o papagaio. Aqui, papagaio é um objeto.

O exemplo para a classe de papagaio pode ser:

```py
class Parrot:
    pass
```

Aqui, usamos a palavra-chave `class` para definir uma classe vazia `Parrot`. Da classe, construímos instâncias. Uma instância é um objeto específico criado a partir de uma classe específica.

# Object

Um objeto (instância) é uma instanciação de uma classe. Quando classe é definida, apenas a descrição para o objeto é definida. Portanto, nenhuma memória ou armazenamento é alocado.

O exemplo para o objeto da classe papagaio pode ser:

```py
obj = Parrot()
```

Aqui, obj é objeto de classe Parrot.

Suponha que tenhamos detalhes de papagaio. Agora, vamos mostrar como construir a classe e os objetos do papagaio.

Exemplo 1: Criando classe e objeto em Python
script.py
IPython Shell

Corre
Desenvolvido por DataCamp
Quando executamos o programa, a saída será:

Blu é um pássaro
Woo também é um pássaro
Blu tem 10 anos
Woo tem 15 anos
No programa acima, criamos uma classe com o nome Parrot . Então, definimos atributos. Os atributos são uma característica de um objeto.


Em seguida, criamos instâncias da classe Parrot . Aqui, blu e woo são referências (valor) aos nossos novos objetos.

Então, acessamos o atributo class usando __class __.species. Os atributos de classe são os mesmos para todas as instâncias de uma classe. Da mesma forma, acessamos os atributos da instância usando blu.namee blu.age. No entanto, os atributos da instância são diferentes para cada instância de uma classe.

Para saber mais sobre classes e objetos, acesse Classes e objetos Python.

Métodos
Métodos são funções definidas dentro do corpo de uma classe. Eles são usados ​​para definir os comportamentos de um objeto.

Exemplo 2: Criando métodos em Python
script.py
IPython Shell

Corre
Desenvolvido por DataCamp
Quando executamos o programa, a saída será:

Blu canta 'Feliz'
Blu agora está dançando
No programa acima, definimos dois métodos, ie sing()e dance(). Eles são chamados de método de instância porque são chamados em um objeto de instância, ou seja blu.

Herança
A herança é uma maneira de criar nova classe para usar detalhes da classe existente sem modificá-la. A classe recém-formada é uma classe derivada (ou classe filho). Da mesma forma, a classe existente é uma classe base (ou classe pai).

Exemplo 3: Uso de herança em Python
script.py
IPython Shell

Corre
Desenvolvido por DataCamp
Quando executamos este programa, a saída será:

O pássaro está pronto
Pinguim está pronto
Pinguim
Nade mais rápido
Corra mais rápido
No programa acima, criamos duas classes, por exemplo, Bird (classe pai) e Penguin (classe filho). A classe filho herda as funções da classe pai. Podemos ver isso no swim()método Novamente, a classe filho modificou o comportamento da classe pai. Podemos ver isso no método whoisThis (). Além disso, estendemos as funções da classe pai, criando um novo run()método.

Além disso, usamos a super()função before __init__()method. Isso ocorre porque queremos extrair o conteúdo do __init__()método da classe pai para a classe filho.

Encapsulamento
Usando OOP em Python, podemos restringir o acesso a métodos e variáveis. Isso evita que os dados sejam modificados diretamente, chamados de encapsulamento. Em Python, denotamos atributo privado usando sublinhado como prefixo, ou seja, único “_“ ou duplo “__“.

Exemplo 4: Encapsulamento de dados em Python
script.py
IPython Shell

Corre
Desenvolvido por DataCamp
Quando executamos este programa, a saída será:

Preço de Venda: 900
Preço de Venda: 900
Preço de Venda: 1000
No programa acima, definimos uma classe Computador . Usamos o __init__()método para armazenar o preço máximo de venda do computador. Tentamos modificar o preço. No entanto, não podemos alterá-lo porque o Python trata o __maxprice como atributos privados. Para alterar o valor, usamos uma função setter, ou seja, setMaxPrice()que leva o preço como parâmetro.

Polimorfismo
Polimorfismo é uma capacidade (em OOP) de usar interface comum para múltiplas formas (tipos de dados).

Suponhamos que precisamos colorir uma forma, existem várias opções de forma (retângulo, quadrado, círculo). No entanto, poderíamos usar o mesmo método para colorir qualquer forma. Este conceito é chamado polimorfismo.

Exemplo 5: Usando polimorfismo em Python
script.py
IPython Shell

Corre
Desenvolvido por DataCamp
Quando executamos o programa acima, a saída será:

Papagaio pode voar
Pinguim não pode voar
No programa acima, definimos duas classes Parrot e Penguin . Cada um deles tem um método comum fly(). No entanto, suas funções são diferentes. Para permitir o polimorfismo, criamos uma interface comum, ou seja, flying_test()função que pode receber qualquer objeto. Em seguida, passamos os objetos blu e peggy na flying_test()função, que foram executados de forma eficaz.

Pontos-chave a serem lembrados:
A programação fica fácil e eficiente.
A classe é compartilhável, portanto, os códigos podem ser reutilizados.
A produtividade dos programadores aumenta
Os dados são seguros com a abstração de dados.