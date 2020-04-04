Herança em Python
A herança nos permite definir uma classe que retira toda a funcionalidade da classe pai e nos permite adicionar mais. Neste artigo, você aprenderá a usar herança no Python.

O que é herança?
A herança é um recurso poderoso na programação orientada a objetos.

Refere-se à definição de uma nova classe com pouca ou nenhuma modificação em uma classe existente. A nova classe é chamada classe derivada (ou filha) e a classe da qual herda é chamada classe base (ou pai) .

Sintaxe de herança do Python
classe BaseClass:
  Corpo da classe base
classe DerivedClass (BaseClass):
  Corpo da classe derivada
A classe derivada herda recursos da classe base, adicionando novos recursos a ela. Isso resulta na reutilização do código.

Exemplo de herança em Python
Para demonstrar o uso da herança, vamos dar um exemplo.

Um polígono é uma figura fechada com 3 ou mais lados. Digamos, temos uma classe chamada Polygondefinida da seguinte forma.

class Polygon:
    def __init__(self, no_of_sides):
        self.n = no_of_sides
        self.sides = [0 for i in range(no_of_sides)]

    def inputSides(self):
        self.sides = [float(input("Enter side "+str(i+1)+" : ")) for i in range(self.n)]

    def dispSides(self):
        for i in range(self.n):
            print("Side",i+1,"is",self.sides[i])

Essa classe possui atributos de dados para armazenar o número de lados, ne a magnitude de cada lado como uma lista de lados .

O método inputSides()leva em magnitude de cada lado e, da mesma forma, dispSides()os exibirá corretamente.

Um triângulo é um polígono com 3 lados. Assim, podemos criar uma classe chamada Triangleherda de Polygon. Isso torna todos os atributos disponíveis na classe Polygonprontamente disponíveis em Triangle. Não precisamos defini-los novamente (reutilização de código). Triangleé definido da seguinte maneira.

class Triangle(Polygon):
    def __init__(self):
        Polygon.__init__(self,3)

    def findArea(self):
        a, b, c = self.sides
        # calculate the semi-perimeter
        s = (a + b + c) / 2
        area = (s*(s-a)*(s-b)*(s-c)) ** 0.5
        print('The area of the triangle is %0.2f' %area)
No entanto, a classe Trianglepossui um novo método findArea()para localizar e imprimir a área do triângulo. Aqui está uma amostra de execução.

>>> t = Triangle()

>>> t.inputSides()
Enter side 1 : 3
Enter side 2 : 5
Enter side 3 : 4

>>> t.dispSides()
Side 1 is 3.0
Side 2 is 5.0
Side 3 is 4.0

>>> t.findArea()
The area of the triangle is 6.00
Podemos ver que, embora não tenhamos definido métodos como inputSides()ou dispSides()para classe Triangle, fomos capazes de usá-los.

Se um atributo não for encontrado na classe, a pesquisa continuará na classe base. Isso se repete recursivamente, se a própria classe base for derivada de outras classes.

Substituição de método em Python
No exemplo acima, aviso de que __init__()método foi definido em ambas as classes, Trianglebem Polygon. Quando isso acontece, o método na classe derivada substitui o da classe base. Isso quer dizer, __init__()no Trianglerecebe preferência sobre o mesmo em Polygon.

Geralmente, ao substituir um método base, tendemos a estender a definição em vez de simplesmente substituí-la. O mesmo está sendo feito chamando o método na classe base daquele da classe derivada (chamando Polygon.__init__()de __init__()in Triangle).

Uma opção melhor seria usar a função interna super(). Portanto, super().__init__(3)é equivalente Polygon.__init__(self,3)e é o preferido. Você pode aprender mais sobre a função super () no Python .

Duas funções internas isinstance()e issubclass()são usadas para verificar heranças. A função isinstance()retornará Truese o objeto for uma instância da classe ou outras classes derivadas dele. Toda e qualquer classe no Python herda da classe base object.

>>> isinstance(t,Triangle)
True

>>> isinstance(t,Polygon)
True

>>> isinstance(t,int)
False

>>> isinstance(t,object)
True
Da mesma forma, issubclass()é usado para verificar a herança de classe.

>>> issubclass(Polygon,Triangle)
False

>>> issubclass(Triangle,Polygon)
True

>>> issubclass(bool,int)
True