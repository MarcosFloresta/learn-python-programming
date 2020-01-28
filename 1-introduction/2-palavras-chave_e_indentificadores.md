# Palavras-chave e identificadores Python

Neste tutorial, você aprenderá sobre palavras-chave (palavras reservadas em Python) e identificadores (nomes dados a variáveis, funções, etc.).

## Palavras-chave Python

Palavras-chave são as palavras reservadas em Python.

Não podemos usar uma palavra-chave como  nome de variável , nome da função ou qualquer outro identificador. Eles são usados ​​para definir a sintaxe e a estrutura da linguagem Python.

No Python, as palavras-chave diferenciam maiúsculas de minúsculas.

Existem 33 palavras-chave no Python 3.7. Esse número pode variar um pouco ao longo do tempo.

Todas as palavras-chave exceto True, Falsee e None estão em minúsculas e devem ser escritas como estão. A lista de todas as palavras-chave é fornecida abaixo.

Palavras-chave em Python

|  |  |  |  |  |
| :---: | :---: | :---: | :---: | :---: |
| False | class | finally | is | return |
| None | continue | for | lambda | try |
| True | def | from | nonlocal | while |
| and | del | global | not | with |
| as | elif | if | or | yield |
| assert | else | import | pass | |
| break | except | in | raise | |

Olhar todas as palavras-chave de uma só vez e tentar descobrir o que elas significam pode ser esmagador.

Se você deseja ter uma visão geral, aqui está a lista completa de todas as palavras - chave com exemplos.

## Identificadores Python

Um identificador é um nome dado a entidades como classe, funções, variáveis ​​etc. Isso ajuda a diferenciar uma entidade da outra.

### Regras para escrever identificadores

1. Os identificadores podem ser uma combinação de letras em minúsculas **(a a z)** ou maiúsculas **(A a Z)** ou dígitos **(0 a 9)** ou um sublinhado `_`. Nomes como  `myClass`, `var_1` e `print_this_to_screen`, todos são exemplos válidos.
2. Um identificador não pode começar com um dígito. `1variable` é inválido, mas `variable1` está perfeitamente correto.
3. Palavras-chave não podem ser usadas como identificadores.

    ```py
    >>> global = 1
    File "<interactive input>", line 1
        global = 1
            ^
    SyntaxError: invalid syntax
    ```

4. Não podemos usar símbolos especiais como **! , @ , # , $ , %** etc. no nosso identificador.

    ```py
    >>> a@ = 0
    File "<interactive input>", line 1
        a@ = 0
        ^
    SyntaxError: invalid syntax
    ```

5. identificador pode ter qualquer comprimento.

## Coisas para lembrar

Python é uma linguagem que diferencia maiúsculas de minúsculas. Isso significa `Variable` e `variable` não é o mesmo. Sempre nomeie identificadores que façam sentido.

Enquanto, `c = 10` é válido. Escrever `count = 10` faria mais sentido e seria mais fácil descobrir o que faz, mesmo quando você olha seu código após um longo intervalo.

Várias palavras podem ser separadas usando um sublinhado `this_is_a_long_variable`,.
