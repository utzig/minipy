# Aula 1

## Sobre Python 3 e instalação
O interpretador pode ser obtido no [site oficial](https://python.org) e instalado nas plataformas mais populares (Linux/Mac/Windows).

Na maioria das distribuições Linux ele já virá instalado por padrão, porém em algumas (Debian, Ubuntu e derivados, normalmente) o comando `python` aponta por padrão para o `python2`, sendo necessário executar explicitamente `python3`.

Tenha sempre preferência pela versão estável mais recente, a não ser que seja *realmente* necessário trabalhar com o Python 2 ou outra versão, por razões de compatibilidade. No curso usaremos **Python 3.6 ou mais recente**.


## Linha de comando (CLI)
Faremos uso de uma interface não-gráfica, dispondo de comandos e parâmetros em texto para realizar tarefas. Não há o que temer e não há necessidade de memorizar tudo, sempre temos a internet para consultar.

Para iniciar o Python no modo interativo, abra o terminal (talvez encontrado como console ou, no Windows, prompt de comando), digite `python` e pressione `Enter`.


## Modo interativo (REPL)
**R**ead-**E**valuate-**P**rint **L**oop é um sistema que repetidamente lê os dados de entrada fornecidos, avalia-os e imprime o resultado. Dentro deste modo, podemos inserir qualquer código Python válido e ele será executado. Expressões serão avaliadas e o resultado será impresso na linha seguinte, tornando esse modo muito útil para experimentação e realização de tarefas simples. Acostume-se a abrir o Python no modo interativo sempre que surgir alguma dúvida: a melhor forma de aprender é fazendo.


## Tipos numéricos
Os tipos numéricos mais comuns são `int` e `float`.

+ O tipo `int` compreende os números inteiros, sem parte fracionária. Eles podem ser negativos e positivos de qualquer tamanho, assim como zero.
+ O tipo `float`, por outro lado, representa o conjunto dos números reais. Os números deste tipo são representados com um ponto (`.`) separando a parte inteira da parte fracionária.
É importante notar que a precisão destes números é limitada, assim como o seu tamanho. Tenha sempre em mente que não é garantida a exatidão nas operações.

*(`float`s no Python implementam a representação de números com ponto flutuante com precisão dupla (64bits) e suas operações aritméticas conforme descritos no padrão IEEE 754)*

O Python também dispõe do tipo `complex`, para números com parte real e parte imaginária.


## Operações aritméticas
As operações entre os tipos numéricos descritos acima são dadas pelos seguintes operadores:

+ `+` Soma
+ `-` Subtração
+ `*` Multiplicação
+ `/` Divisão
+ `//` Divisão inteira: a parte fracionária do quociente é ignorada (ocorre truncamento)
+ `**` Potenciação (são permitidos expoentes positivos e negativos, inteiros ou não)
+ `%` Módulo (retorna o resto da divisão entre os dois operandos)


## Variáveis
Quaisquer valores podem ser guardados como variáveis, fazendo uso do **operador de atribuição**(`=`). Vale notar que as variáveis não se comportam como na matemática, ou seja: atribuir `x = y` não fará com que o valor de `x` se altere caso o valor de `y` seja posteriormente alterado.

Variáveis podem ter qualquer nome, sendo preferida a convenção `snake_case`: palavras em letras minúsculas, separadas por underscores (`_`). Escolha nomes  que não sejam curtos ou longos demais, mas descritivos e legíveis.

Python não tem, formalmente, o conceito de constantes, mas a convenção é de usar letras maiúsculas e declará-las no início do código.


## Funções
Sempre que alguma operação precisar ser executada várias vezes, convém criar uma função para evitar a repetição de código. Observe o exemplo abaixo:

```python
def soma(a, b=1):
····c = a + b
····return c
```
Para definir uma função, escrevemos:
+ a keyword (palavra-chave) `def`, seguida de um espaço
+ o nome da função (a convenção para nomes de funções é a mesma que para variáveis, `snake_case`)
+ a lista de parâmetros, entre parênteses.

Note que nesse caso foi definido um valor padrão para o parâmetro `b`. Portanto, se a função for chamada com `soma(2)`, o valor tomado como `a` será `2` e, como `b`, `1`. Os parâmetros com valor padrão devem sempre vir ao fim.

Uma função exige indentação para demarcar o início e o fim do seu conteúdo. Para isso, usamos espaços ou tabs. A convenção é de usar 4 espaços, algo que a maioria dos editores de texto poderá fazer automaticamente mesmo quando for pressionada a tecla Tab. No exemplo acima foram usados pontos para indicar os espaços.

Uma chamada de função assumirá o valor de retorno desta, ou seja, a expressão `soma(2, 3)` será avaliada como `5`. Se a execução de uma função chegar ao fim sem encontrar uma keyword `return`, ela retornará `None`.


## Função `print`
É importante ter feedback da execução de um programa e para isso é comum usar `print`s. Simplesmente escreva `print('Algum texto')` ou `print(algum_objeto)`.

Isso será abordado mais a fundo no futuro, mas para imprimir algum texto com o valor de variáveis, use f-strings:
```python
nome = 'Cauê'
ano_de_nascimento = 1997
print(f'{nome} nasceu em {ano_de_nascimento}')
```


## Biblioteca padrão e Documentação
Da mesma forma que podemos escrever escrever nossas funções, podemos também usar funções escritas por outras pessoas. Só precisamos ter outros módulos instalados. Porém, o Python já traz uma extensa biblioteca padrão de módulos bastante úteis. Como exemplo, considere os módulos `math` e `statistics`.

+ `math` fornece uma variedade de funções matemáticas, como funções trigonométricas.
+ `statistics` implementa algumas funções estatísticas comuns, como mediana e desvio padrão.

Todos os módulos da biblioteca padrão encontram-se listados e bem explicados na [documentação oficial](https://docs.python.org/3/library). Não hesite em visitá-la sempre que necessário.


## Tipos Booleanos
Como todas as linguagens, Python conta com um tipo booleano: o nome pode parecer estranho, mas o conceito é bastante natural. Os valores booleanos são `True` e `False`, verdadeiro e falso. A álgebra booleana foi introduzida por George Boole e teve grande impacto nos estudos da lógica e da computação.

Em Python, a maioria das classes descreve como os objetos devem ser interpretados como `bool`. Tipos numéricos são avaliados como `True` quando não são zero e `False` em caso contrário. Listas e strings são avaliadas como `False` quando vazias e `True` em caso contrário, etc.


## Operadores de comparação
Python conta com alguns operadores de comparação, que têm como valor de retorno um `bool` (`True` ou `False`).
+ `<` Menor que
+ `<=` Menor ou igual que
+ `>` Maior que
+ `>=` Maior ou igual que
+ `==` Igual a
+ `!=` Diferente de

Além destes, há também os operadores de identidade, que podem gerar confusão no futuro. `is` e `is not` verificam se dois objetos são ou não **o mesmo objeto**. Com números, isto pode funcionar da mesma forma que testar por igualdade, mas cuidado: eles são a exceção e não a regra.


## Operadores Booleanas
+ `or` retorna o primeiro valor se este for avaliado como verdadeiro, senão o segundo
+ `and` retorna o primeiro valor se este for avaliado como falso, senão o segundo
+ `not` retorna o valor avaliado como `bool` e negado.


## Estruturas condicionais
Para garantir que uma porção de código seja executada dependendo de alguma circunstância, usamos expressões condicionais, e.g.:

```python
if n % 2 == 0:
    print(f'{n} é par')
else:
    print(f'{n} é ímpar')
```

```python
if n < 10:
    print(f'{n} é menor que 10')

elif n < 100:
    print(f'{n} é menor que 100, mas maior ou igual a 10')

else:
    print(f'{n} é maior ou igual a 100')
```

A expressão depois de `if` é avaliada como `bool` e se for `True`, o bloco abaixo é executado (este deve estar indentado em relação ao `if`).

Pode-se usar um ou mais `elif` para fazer outros testes ou um `else` para cobrir os casos que não passaram nos testes. Só um dos blocos é executado.
(`if`, `elif`, `else`)
