# Break e Continue

Neste artigo, você aprenderá a usar as instruções `break` e `continue` para alterar o fluxo de um loop.

##  Qual é o uso de break e continue no Python?

No Python, as instruções break e continue podem alterar o fluxo de um loop normal.

Os loops iteram sobre um bloco de código até que a expressão de teste seja falsa, mas às vezes desejamos terminar a iteração atual ou mesmo todo o loop sem verificar a expressão de teste.

As instruções break e continue são usadas nesses casos.

## Declaração de break no Python

A instrução break termina o loop que a contém. O controle do programa flui para a instrução imediatamente após o corpo do loop.

Se a instrução break estiver dentro de um loop aninhado (loop dentro de outro loop), break encerrará o loop mais interno.

Sintaxe de interrupção

```py
break
```

Fluxograma de quebra

![Fluxograma da instrução break em Python](/images/flowchart-break-statement.jpg)

O funcionamento da instrução break em loop for e while é mostrado abaixo.

![Como a declaração de quebra funciona em Python?](/images/how-break-statement-works.jpg)

Exemplo: quebra de Python

```py
# Use of break statement inside loop

for val in "string":
    if val == "i":
        break
    print(val)

print("The end")
```

Resultado

```py
s
t
r
The end
```

Neste programa, iteramos através da `"string"` sequência. Verificamos se a letra é `"i"` e sobre a qual rompemos o ciclo. Portanto, vemos em nossa saída que todas as letras até `"i"` são impressas. Depois disso, o loop termina.

Instrução Python continue
A instrução continue é usada para ignorar o restante do código dentro de um loop apenas para a iteração atual. O loop não termina, mas continua com a próxima iteração.

Sintaxe de Continuar
continuar
Fluxograma de continuar 
Fluxograma da instrução continue em Python

O funcionamento da instrução continue no loop for e while é mostrado abaixo.

Como a instrução continue funciona em python

Exemplo: Python continue
script.py
IPython Shell

Corre
Desenvolvido por DataCamp
Resultado

s
t
r
n
g
O fim
Este programa é o mesmo do exemplo acima, exceto que a instrução break foi substituída por continue.

Continuamos com o loop, se a string estiver "i", não executando o restante do bloco. Portanto, vemos em nossa saída que todas as letras, exceto, "i"são impressas