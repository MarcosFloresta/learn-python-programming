# Argumentos da função Python

No Python, você pode definir uma função que recebe um número variável de argumentos. Você aprenderá a definir essas funções usando argumentos padrão, palavra-chave e arbitrários neste artigo.

## Argumentos

No tópico de função definida pelo usuário , aprendemos sobre como definir uma função e chamá-la. Caso contrário, a chamada de função resultará em um erro. Aqui está um exemplo.

```py
def greet(name,msg):
   """This function greets to
   the person with the provided message"""
   print("Hello",name + ', ' + msg)

greet("Monica","Good morning!")
```

Resultado

```py
Hello Monica, Good morning!
```

Aqui, a função `greet()` possui dois parâmetros.

Como chamamos essa função com dois argumentos, ela funciona sem problemas e não obtemos nenhum erro.

Se o chamarmos com um número diferente de argumentos, o intérprete reclamará. Abaixo está uma chamada para esta função com um e sem argumentos, juntamente com suas respectivas mensagens de erro.

```py
>>> greet("Monica")    # only one argument
TypeError: greet() missing 1 required positional argument: 'msg'
```

```py
>>> greet()    # no arguments
TypeError: greet() missing 2 required positional arguments: 'name' and 'msg'
```

## Argumentos de Função Variável

Até agora, as funções tinham um número fixo de argumentos. No Python, existem outras maneiras de definir uma função que pode receber um número variável de argumentos.

Três formas diferentes deste tipo são descritas abaixo.

### Argumentos padrão do Python

Argumentos de função podem ter valores padrão em Python.

Podemos fornecer um valor padrão para um argumento usando o operador de atribuição (=). Aqui está um exemplo.

```py
def greet(name, msg = "Good morning!"):
   """
   This function greets to
   the person with the
   provided message.

   If message is not provided,
   it defaults to "Good
   morning!"
   """

   print("Hello",name + ', ' + msg)

greet("Kate")
greet("Bruce","How do you do?")
```

Nesta função, o parâmetro `name` não possui um valor padrão e é necessário (obrigatório) durante uma chamada.

Por outro lado, o parâmetro `msg` tem um valor padrão de "Good morning!". Portanto, é opcional durante uma chamada. Se um valor for fornecido, ele substituirá o valor padrão.

Qualquer número de argumentos em uma função pode ter um valor padrão. Mas uma vez que tenhamos um argumento padrão, todos os argumentos à direita também deverão ter valores padrão.

Isso significa dizer que argumentos não padrão não podem seguir argumentos padrão. Por exemplo, se tivéssemos definido o cabeçalho da função acima como:

```py
def greet(msg = "Good morning!", name):
```

Ocorreríamos um erro como:

```py
SyntaxError: non-default argument follows default argument
```

### Argumentos de palavra-chave Python

Quando chamamos uma função com alguns valores, esses valores são atribuídos aos argumentos de acordo com sua posição.

Por exemplo, na função acima greet(), quando o chamamos como greet("Bruce","How do you do?"), o valor "Bruce"é atribuído ao nome do argumento e da mesma forma "How do you do?"para msg .

O Python permite que funções sejam chamadas usando argumentos de palavra-chave. Quando chamamos funções dessa maneira, a ordem (posição) dos argumentos pode ser alterada. As chamadas a seguir para a função acima são válidas e produzem o mesmo resultado.

>>> # 2 argumentos da palavra-chave
>>> greet (name = "Bruce", msg = "Como você está?")

>>> # 2 argumentos de palavras-chave (fora de ordem)
>>> greet (msg = "Como você está?", name = "Bruce") 

>>> # 1 posicional, 1 argumento de palavra-chave
>>> greet ("Bruce", msg = "Como você está?")           
Como podemos ver, podemos misturar argumentos posicionais com argumentos de palavras-chave durante uma chamada de função. Mas devemos ter em mente que os argumentos das palavras-chave devem seguir os argumentos posicionais.

Ter um argumento posicional após os argumentos da palavra-chave resultará em erros. Por exemplo, a chamada de função da seguinte maneira:

greet (name = "Bruce", "Como você está?")
Irá resultar em erro como:

SyntaxError: arg sem palavra-chave após arg
Argumentos arbitrários em Python
Às vezes, não sabemos antecipadamente o número de argumentos que serão passados ​​para uma função. O Python nos permite lidar com esse tipo de situação por meio de chamadas de função com número arbitrário de argumentos.

Na definição da função, usamos um asterisco (*) antes do nome do parâmetro para denotar esse tipo de argumento. Aqui está um exemplo.

script.py
IPython Shell

Corre
Desenvolvido por DataCamp
Resultado

Olá Monica
Olá Luke
Olá Steve
Olá john
Aqui, chamamos a função com vários argumentos. Esses argumentos são agrupados em uma tupla antes de serem passados ​​para a função. Dentro da função, usamos um forloop para recuperar todos os argumentos de volta.