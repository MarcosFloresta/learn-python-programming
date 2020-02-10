#Técnicas de looping em Python

Neste artigo, você aprenderá a controlar a execução de um loop usando instruções de controle de loop como break e continue.

A programação Python oferece dois tipos de loop, o loop for e o while . Usando esses loops junto com instruções de controle de loop, como break e continue, podemos criar várias formas de loop.

O loop infinito
Podemos criar um loop infinito usando a instrução while. Se a condição do loop while for sempre True, obteremos um loop infinito.

Exemplo # 1: loop infinito usando while
# An example of infinite loop
# press Ctrl + c to exit from the loop
while True:
   num = int(input("Enter an integer: "))
   print("The double of",num,"is",2 * num)
Resultado

Digite um número inteiro: 3
O dobro de 3 é 6
Digite um número inteiro: 5
O dobro de 5 é 10
Digite um número inteiro: 6
O dobro de 6 é 12
Digite um número inteiro:
Traceback (última chamada mais recente):
Loop com condição no topo
Este é um loop while normal sem instruções de interrupção. A condição do loop while está no topo e o loop termina quando essa condição estiver False.

Fluxograma de loop com condição no topo
Técnica de loop: loop com condição no topo

Exemplo # 2: Loop com condição no topo
script.py
IPython Shell

Corre
Desenvolvido por DataCamp

Quando você executa o programa, a saída será:

A soma é 55
Loop com condição no meio
Esse tipo de loop pode ser implementado usando um loop infinito, juntamente com uma quebra condicional entre o corpo do loop.

Fluxograma de loop com condição no meio
Técnica de loop: loop com condição no meio

Exemplo # 3: Loop com condição no meio
# Program to illustrate a loop with condition in the middle. 
# Take input from the user untill a vowel is entered
vowels = "aeiouAEIOU"
# infinite loop
while True:
   v = input("Enter a vowel: ")
   # condition in the middle
   if v in vowels:
       break
   print("That is not a vowel. Try again!")
print("Thank you!")
Resultado

Digite uma vogal: r
Isso não é uma vogal. Tente novamente!
Digite uma vogal: 6
Isso não é uma vogal. Tente novamente!
Digite uma vogal:,
Isso não é uma vogal. Tente novamente!
Digite uma vogal: u
Obrigado!
Loop com condição na parte inferior
Esse tipo de loop garante que o corpo do loop seja executado pelo menos uma vez. Ele pode ser implementado usando um loop infinito junto com uma quebra condicional no final. Isso é semelhante ao loop do ... while em C.

Fluxograma de loop com condição na parte inferior
Técnica de loop: loop com condição no topo

Exemplo # 4: Loop com condição na parte inferior
# Python program to illustrate a loop with condition at the bottom
# Roll a dice untill user chooses to exit
# import random module
import random
while True:
   input("Press enter to roll the dice")
   # get a number between 1 to 6
   num = random.randint(1,6)
   print("You got",num)
   option = input("Roll again?(y/n) ")
   # condition
   if option == 'n':
       break
 
Resultado

Pressione enter para rolar os dados
Você tem 1
Rolar novamente? (S / n) y
Pressione enter para rolar os dados
Você tem 5
Rolar novamente? (S / n) n
INSTRUÇÃO ANTERIOR do