# Técnicas de looping em Python

Neste artigo, você aprenderá a controlar a execução de um loop usando instruções de controle de loop como break e continue.

A programação Python oferece dois tipos de loop, o loop `for` e o `while`. Usando esses loops junto com instruções de controle de loop, como `break` e `continue`, podemos criar várias formas de loop.

## O loop infinito

Podemos criar um loop infinito usando a instrução while. Se a condição do loop while for sempre `True`, obteremos um loop infinito.

Exemplo # 1: loop infinito usando while

```py
# An example of infinite loop
# press Ctrl + c to exit from the loop
while True:
   num = int(input("Enter an integer: "))
   print("The double of",num,"is",2 * num)
```

Resultado

```txt
Enter an integer: 3
The double of 3 is 6
Enter an integer: 5
The double of 5 is 10
Enter an integer: 6
The double of 6 is 12
Enter an integer:
Traceback (most recent call last):
```

## Loop com condição no topo

Este é um loop while normal sem instruções de interrupção. A condição do loop while está no topo e o loop termina quando essa condição estiver False.

Fluxograma de loop com condição no topo

![Técnica de loop: loop com condição no topo](/images/condition-top.jpg)

Exemplo # 2: Loop com condição no topo

```py
# Program to illustrate a loop with condition at the top

# Try different numbers
n = 10

# Uncomment to get user input
#n = int(input("Enter n: "))

# initialize sum and counter
sum = 0
i = 1

while i <= n:
   sum = sum + i
   i = i+1    # update counter

# print the sum
print("The sum is",sum)
```

Quando você executa o programa, a saída será:

```txt
The sum is 55
```

## Loop com condição no meio

Esse tipo de loop pode ser implementado usando um loop infinito, juntamente com uma quebra condicional entre o corpo do loop.

Fluxograma de loop com condição no meio

![Técnica de loop: loop com condição no meio](/images/condition-middle.jpg)

Exemplo # 3: Loop com condição no meio

```py
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
```

Resultado

```txt
Enter a vowel: r
That is not a vowel. Try again!
Enter a vowel: 6
That is not a vowel. Try again!
Enter a vowel: ,
That is not a vowel. Try again!
Enter a vowel: u
Thank you!
```

## Loop com condição na parte inferior

Esse tipo de loop garante que o corpo do loop seja executado pelo menos uma vez. Ele pode ser implementado usando um loop infinito junto com uma quebra condicional no final. Isso é semelhante ao loop `do ... while` em C.

Fluxograma de loop com condição na parte inferior

![Técnica de loop: loop com condição no topo](/images/condition-bottom.jpg)

Exemplo # 4: Loop com condição na parte inferior

```py
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
```

Resultado

```txt
Press enter to roll the dice
You got 1
Roll again?(y/n) y
Press enter to roll the dice
You got 5
Roll again?(y/n) n
```
