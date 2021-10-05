# Ciclos de Repetição

Como o próprio nome indica, o uso de ciclos de repetição serve para executar código várias vezes.

Em Portugol temos o `enquanto`, `faca enquanto` e o `para`.

## enquanto

A estrutura do `enquanto` é semelhante ao `se`. Avalia uma condição repetidamente e executa-a enquanto ela for verdadeira.

```C
inteiro i = 0
enquanto(i < 10) {
    escreva(i, "\n")
    i++
}
```
> Nota: `<` é um operador que compara o primeiro operando com o segundo. Aqui estamos a verificar se `i` é menor que 10. Se quisessemos ver se `i` é maior que 10, usávamos `>`.

Output do código acima:

```
0
1
2
3
4
5
6
7
8
9
```

Recapitulando, definimos `i` e demos-lhe o valor 0. Enquanto `i` for menor que 10, escreva o valor de `i` e incremente `i`.

> Nota: `i++` é o mesmo que `i = i + 1`

## faca enquanto
Este ciclo é semelhante ao `enquanto`. A única diferença é que a condição só é verificada no fim do ciclo. Isto significa que o código irá executar pelo menos uma vez!

```
faca {
    instrucao
} enquanto (condicao)
```

## para
O `para` é parecido ao `enquanto` e com este podemos simplificar o nosso código em cima.

```C
para(inteiro i = 0; i < 10; i++)
{
    escreva(i, "\n")
}
```

Reparem que o `para` tem três expressões separadas por ponto e vírgula. A primeira define o que podemos chamar de contador, o `i`.

`inteiro i = 0`

A segunda expressão define a condição que o `para` avalia.

`i < 10`

Finalmente, temos a terceira expressão que é executada no fim do corpo do `para`

`i++`

