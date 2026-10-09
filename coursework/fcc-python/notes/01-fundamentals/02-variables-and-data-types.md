# 📦 Entendendo variáveis e tipos de dados

> Módulo **Fundamentos de Python** · aula de teoria

---

## 🏷️ Declarando variáveis

Para criar uma variável, escrevemos o nome à esquerda e usamos o operador de atribuição (`=`) para guardar o valor que está à direita.

![Exemplo de declaração de variáveis: name recebe a string "exethew" e commits recebe o inteiro 0, com um comentário acima](/assets/fcc-python/01-fundamentals/02-variables-and-data-types/variable-example.svg "Exemplo da Declaração de Variável")

No exemplo, a variável `name` guarda o valor `"exethew"`, que é uma **string** (cadeia de caracteres usada para representar texto). Podemos declarar strings com aspas duplas `""` ou simples `''`.

### Regras de nomenclatura

- Só podem começar com **letra** ou **underscore** (`_`), nunca com número.
- Só podem conter caracteres alfanuméricos (`a-z`, `A-Z`, `0-9`) e underscores.
- São **sensíveis a maiúsculas e minúsculas**: `age`, `Age` e `AGE` são três variáveis diferentes.
- Não podem ser **palavras reservadas** do Python, como `if`, `class` ou `def`.

### Convenções

- Usamos **snake case**: letras minúsculas, com as palavras separadas por underscore.

```python
my_variable_name = 'freeCodeCamp'
```

- Preferimos **nomes descritivos** e evitamos abreviações. Para guardar a idade de um usuário, `user_age` é melhor que `age` ou `ua`.

```python
user_age = 30
```

- Evitamos nomes abreviados demais e variáveis de uma única letra. Nomes claros deixam o código mais fácil de entender.

### 💬 Comentários

Usamos o símbolo `#` (hashtag ou cerquilha) para escrever um comentário. O Python ignora tudo o que vem depois dele na linha. Dá para ver um comentário na primeira linha do exemplo das variáveis acima.

---

## 🖨️ A função `print()`

O **terminal** é a área onde vemos a saída de texto de um programa. A função `print()` já vem embutida no Python, então podemos usá-la sem definir nada. Ela envia texto e outros valores para o terminal.

Para exibir um texto, colocamos a string entre os parênteses da chamada:

```python
print('Hello world!') # Hello world!
```

Nesse caso, `'Hello world!'` é um **argumento** passado para a função.

Também podemos exibir **vários argumentos** de uma vez, separando-os por vírgulas:

![Exemplo de print com vários argumentos: print('My favorite colors are', 'blue', 'green', 'red') mostra My favorite colors are blue green red](/assets/fcc-python/01-fundamentals/02-variables-and-data-types/print-multiple-arguments.svg "Exemplo de como utilizar a função Print")

> 💡 O Python adiciona automaticamente um **espaço** entre cada item separado por vírgula.

---

## 🧬 Tipos de dados

Um **tipo de dado** descreve o tipo de valor que uma variável guarda, como um número ou um texto. As linguagens usam tipos para saber como armazenar e manipular cada informação.

O Python é **dinamicamente tipado**: não declaramos o tipo ao criar a variável. Ele descobre o tipo pelo valor atribuído.

```python
name = 'John Doe' # Python sabe que é uma string
age = 25          # Python sabe que é um inteiro
```

Uma variável pode receber depois um valor de **outro tipo**:

```python
age = 25
age = 'Twenty-five'
```

> ⚠️ Após a segunda atribuição, `age` passa a guardar uma **string**, e não mais um inteiro.

### Os quatro tipos principais

![Exemplo dos quatro tipos de dados: integer_var com 10, float_var com 1.5, string_var com 'exethew' e boolean_var com True, com comentários explicando cada tipo](/assets/fcc-python/01-fundamentals/02-variables-and-data-types/data-types.svg "Mostrando os tipos de variáveis")
| Tipo | Nome no Python | Descrição | Exemplo |
|------|----------------|-----------|---------|
| Inteiro | `int` | Número sem casas decimais | `10`, `-5` |
| Float | `float` | Número com casas decimais | `4.41`, `-0.4` |
| String | `str` | Sequência de caracteres entre aspas | `'Hello world!'` |
| Booleano | `bool` | Verdadeiro ou falso | `True`, `False` |

> 📌 O Python tem outros tipos. Vamos aprendê-los conforme precisarmos de cada um.

---

## 🔍 `type()` e `isinstance()`

### `type()`: descobrindo o tipo

Para ver o tipo de uma variável, usamos a função `type()`:

![Exemplo de type(): developer recebe 'exethew' e print(type(developer)) mostra a classe str](/assets/fcc-python/01-fundamentals/02-variables-and-data-types/type-example.svg "Demonstração de como utilizar a função Type")

O que `type()` mostra para cada tipo que vimos:

| Valor | Saída |
|-------|-------|
| `10` | `<class 'int'>` |
| `4.50` | `<class 'float'>` |
| `'hello'` | `<class 'str'>` |
| `True` | `<class 'bool'>` |

> ⚠️ Se chamarmos `type()` **sem argumento**, recebemos um `TypeError` (`type() takes 1 or 3 arguments`).

### `isinstance()`: verificando o tipo

Às vezes precisamos conferir o tipo de uma variável **antes** de fazer operações com ela. Por exemplo, tentar dividir uma string por um número gera erro:

![Exemplo de erro: dividir a string '12' por 2 gera TypeError: unsupported operand type(s) for /: 'str' and 'int'](/assets/fcc-python/01-fundamentals/02-variables-and-data-types/type-error-example.svg "Demonstração de erro com diferentes dados")

Para checar se `account_balance` é um inteiro, usamos `isinstance()`:

```python
account_balance = '12'

isinstance(account_balance, int) # False
```

A função recebe **um valor** e **o tipo** contra o qual queremos verificar, e retorna um **booleano**. Como `account_balance` é uma string, o resultado é `False`.

Também podemos verificar **vários tipos de uma vez**, passando-os numa tupla:

![Exemplo de isinstance(): account_balance recebe 12 e isinstance(account_balance, (int, float)) retorna True](/assets/fcc-python/01-fundamentals/02-variables-and-data-types/isinstance-example.svg "Utilização da função isinstance")

Aqui `account_balance` é um inteiro, então o retorno é `True`. Se fosse `12.0`, ainda retornaria `True`, porque estamos checando por `int` **ou** `float`.

> 🎯 Nas próximas oficinas, vamos usar `type()` e `isinstance()` para garantir que as variáveis têm o tipo certo antes de operar com elas.

---

## ✅ Resumo rápido

- Criamos variáveis com `nome = valor`.
- Nomes em **snake case**, descritivos, sem começar por número e sem palavras reservadas.
- `#` inicia um comentário.
- `print()` exibe valores no terminal; com vírgulas, ele mostra vários argumentos separados por espaço.
- Python é **dinamicamente tipado**: o tipo vem do valor, e pode mudar numa nova atribuição.
- Tipos principais: `int`, `float`, `str` e `bool`.
- `type()` mostra o tipo; `isinstance()` confere se o valor é de um tipo (ou de vários) e retorna `True` ou `False`.
