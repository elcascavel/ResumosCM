# Portugol
Portugol é a primeira linguagem a que os estudantes de CM são expostos. É baseada em C e PHP.

## Olá Mundo
```C
// Comentário
/* Isto também é um comentário */
programa 
{ 
	funcao inicio () 
	{
		escreva("Olá Mundo!\n")
	} 
}
```

## Comentários
Como podemos ver no exemplo, `//` seguido do que o autor quiser, é um comentário em Portugol. Tudo o que se vê dentro de `/*` `*/` é também um comentário. Este último pode ser de múltiplas linhas!

## Função inicio()
A função `inicio` é sempre a primeira função a ser executada num programa. Uma função é um conjunto de código que é executado quando a função é chamada. Quando uma função é chamada, tudo o que está dentro das chavetas é executado.

Esta função, como todas, contém uma assinatura de função.
```C
funcao inicio()
/* É o mesmo que 
funcao vazio inicio()
*/
```
Esta função é de tipo `vazio`; Não retorna nada. Este tipo não precisa de ser explícito, ou seja, escrito pelo programador. Para além disso, a função não recebe argumentos.

Já vamos ver o que são tipos e argumentos.

Todas as assinaturas de funções são escritas desta forma:
```
tipo nomeDaFuncao(tipo1 argumento1, tipo2 argumento 2, tipo1 argumento3, [etc])
```
Em Portugol temos vários tipos, sendo estes:
*   inteiro
*   real
*   caracter
*   cadeia
*   logico
*   vazio

O tipo `inteiro` usa-se quando é necessário usar valores inteiros. Uma variável de tipo inteiro pode conter qualquer número que pertença ao conjunto dos números inteiros. Podem ser positivos, negativos ou nulos.
Exemplo de sintaxe
```
inteiro nome_da_variavel
```

O tipo `real` é semelhante ao `inteiro`. Usa-se quando queremos armazenar valores que não pertencem aos números inteiros. Os valores do tipo real são números separados por pontos e não por vírgulas.
Exemplo de sintaxe

```
real nome_da_variavel
```

O tipo `caracter` usa-se quando queremos armazenar apenas um carácter alfanúmerico ou especial. Letras, números, etc.
Exemplo de sintaxe

```
caracter nome_da_variavel
```

O tipo `cadeia` serve para armazenar texto ou uma quantidade grande de caracteres.
Exemplo de sintaxe

```
cadeia nome_da_variavel
```

O tipo `logico` é usado em operações lógicas, como estruturas de decisão. Possui somente dois valores, sendo eles `verdadeiro` ou `falso`.
Exemplo de sintaxe

```
logico nome_da_variavel
```

## Corpo de uma função

O corpo de uma função, ou seja, o que ela faz, é todo escrito entre as chavetas. 

No exemplo acima, temos uma função `inicio` que chama a função `escreva` e dá output de "Olá Mundo!". O símbolo `\n` troca para a linha de baixo.

### Como se chama uma função?
Como vemos no exemplo acima, chamamos uma função ao escrever o seu nome e passando os argumentos que este pede.
```C
escreva("Olá Mundo!\n")

/*
A função escreva recebe o argumento:
"Olá Mundo\n"
*/
```

## Retorne
A nossa função `inicio` como é de tipo vazio, não retorna nada. Vamos ver um exemplo de um programa com uma função de tipo inteiro que retorne uma soma.

```C
programa 
{
    funcao inteiro soma()
    {
        retorne 1 + 1
    }
    
	funcao inicio () 
	{
		escreva(soma())
	} 
}
```
Como podemos ver, `soma` retorna a soma de 1 + 1. No entanto, isto não é muito útil. Se calhar, gostávamos que esta função recebesse dois números que o utilizador escolhe e depois faça a soma. Vamos ver outro exemplo:
```C
programa 
{
    funcao inteiro soma(inteiro num1, inteiro num2)
    {
        retorne num1 + num2
    }
    
	funcao inicio () 
	{
	    inteiro numero1, numero2
	    
	    escreva("Introduza o primeiro número\n")
	    leia(numero1)
	    escreva("Introduza o segundo número\n")
	    leia(numero2)
	    
	    escreva("O resultado é: ")
		escreva(soma(numero1, numero2))
	} 
}
```
`leia` é uma função que recebe input do utilizador e coloca essa informação na variável pretendida. No programa acima colocámos dois números; um na variável `numero1` e outro na variável `numero2`.
