# Aula 2

## Executando scripts
Ao invés de interagir com o Python no modo interativo, podemos inserir todo o código em um arquivo de texto, para executá-lo todo de uma vez. A extensão para scripts Python é `.py`, mas isso é apenas uma convenção, indicando para outros programas como esse arquivo deve ser tratado.

Para executar um script, navegamos até o diretório em que se encontra o arquivo e invocamos o Python passando o nome do arquivo como parâmetro. Se não se sentir confortável com a interface linha de comando, dê uma olhada [nesta breve introdução](cli.md).

## Editores de texto
Para escrever nossos programas, fazemos uso de editores de texto. Diferente de processadores de texto (e.g. LibreOffice e Google Docs), editores de texto lidam com texto puro, sem formatação. Um bom editor traz recursos como realce de sintaxe, que colore o código auxiliando na legibilidade. Pessoalmente, recomendo o [Atom](https://atom.io/) ou o [VSCode](https://code.visualstudio.com/), ambos com código aberto e disponíveis em várias plataformas. Sinta-se à vontade para usar o editor com que se sentir mais confortável.

## Função `range`
Para fazer com que uma porção de código seja repetida, usamos um laço de repetição (loop):

```python
for i in range(10):
    print(i)
```

Laços de repetição serão abordados na próxima aula, mas por enquanto entenda que o código dentro de um laço será executado múltiplas vezes e em cada execução o iterando (no exemplo acima, `i`) tomará um valor.

+ `range(n)` gera inteiros de `0` até `n`, sem incluir `n`
+ `range(a, b)` gera inteiros de `a` até `b`, sem incluir `b`
+ `range(a, b, c)` gera inteiros de `a` até `b`, sem incluir `b`, incrementando `c` em cada iteração

Exemplos:

```python
>>> for i in range(5):
...     print(i)
...
0
1
2
3
4
```

```python
>>> for i in range(2, 6):
...     print(i)
...
2
3
4
5
```

```python
>>> for i in range(1, 9, 2):
...     print(i)
...
1
3
5
7
```

## Exercícios

### FizzBuzz
#### Desafio:

Para cada número até 50, imprimir :
+ "Fizz" se ele for múltiplo de 3
+ "Buzz" se ele for múltipli de 5
+ "FizzBuzz" se ele for múltiplo de 3 e de 5
+ o próprio número, se não for múltiplo de 3 nem de 5

#### Solução:
```python
for i in range(1, 50):
    if i % 3 == 0 and i % 5 == 0:
        print('Fizzbuzz')

    elif i % 3 == 0:
        print('Fizz')

    elif i % 5 == 0:
        print('Buzz')

    else:
        print(i)
```

### Fibonacci
#### Desafio:

Produzir a sequência de Fibonacci, que começa com `[1, 1]` e cada número seguinte é a soma dos dois que o precedem.

#### Solução:
```python
def fib(n):
    if n == 0 or n == 1:
        return 1

    else:
        return fib(n - 2) + fib(n - 1)


for i in range(50):
    print(fib(i))
```

Esta é uma solução **recursiva**, porque a função `fib` é definida em termos de si mesma. Uma função recursiva tem sempre um ou mais casos base e um ou mais casos genéricos.

Para Fibonacci, a solução recursiva é muito ineficiente. Uma alternativa iterativa seria:

```python
a, b = 1, 1
for i in range(50):
    print(a)
    a, b = b, a + b
```

### Fatorial

```python
def fact_iterativo(n):
    x = 1
    for i in range(1, n + 1):
        x *= i

    return x


def fact_recursivo(n):
    print(f'calculando fact({n})')
    if n < 2:
        return 1
    else:
        return n * fact_recursivo(n - 1)
```

### Números primos
```python
from math import sqrt


def is_prime(x):
    if x < 2:
        return False

    for i in range(2, round(sqrt(x)) + 1):
        if x % i == 0:
            return False

    return True


for n in range(2, 50):
    if is_prime(n):
        print(n)
```
