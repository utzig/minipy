# Interface de Linha de Comando (CLI)

Quando abrimos um terminal (às vezes chamado de console ou prompt de comando), somos recebidos por um prompt, que nos diz o diretório atual e, talvez, o nome do usuário e do computador.

O diretório do usuário (`HOME`) costuma ser abreviado por `~`.

```
caue@lenny ~ $
```

Podemos usar o comando `ls` para listar o conteúdo do diretório atual (`dir`, no Windows).

```
caue@lenny ~ $ ls
Downloads  Documentos  Imagens  minipy
```

Para acessar outro diretório usamos o comando `cd` (***c**hange **d**irectory*).

```
caue@lenny ~ $ cd minipy

caue@lenny ~/minipy $ ls
aula1.md   aula2.md   cli.md  fact.py  fib.py
primes.py  README.md
```

Uma vez dentro do diretório desejado, podemos executar o Python da seguinte forma:

```
caue@lenny ~/minipy $ python fib.py
1
1
2
3
5
8
13
21
34
55
```

O diretório atual é referenciado por `.` e o diretório acima por `..`

Portanto, se desejamos sair de um diretório, fazemos:

```
caue@lenny ~/minipy $ cd ..

caue@lenny ~ $
```
