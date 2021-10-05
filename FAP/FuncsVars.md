# Funções, variáveis locais e globais

> Para uma visão mais aprofundada acerca de funções e Portugol em geral ver: [Portugol](./Portugol.md)

Em Portugol e tantas outras linguagens, temos algo que podemos chamar de escopo.

```C
programa 
{ 
	funcao inicio () 
	{
		escreva("Olá Mundo!\n")
	} 
}
```

O comando `programa` é obrigatório no Portugol. Dentro do `programa` declaramos variáveis globais e funções em qualquer ordem.

Vamos declarar uma variável global.

```C
programa 
{ 
    inteiro x = 1
	funcao inicio () 
	{
		mudarX()
        x = 5
        escreva("Agora x vale", x)
	} 

    funcao mudarX ()
    {
        x = 2
        escreva("x vale ", x, "\n")
    }
}
```
Em cima declaramos uma variável global chamada `x`. Isto significa que `x` pode ser alterada em qualquer função que declaremos.

Na função `inicio` chamamos a função `mudarX`. Dentro da função `mudarX`, mudamos o valor de `x` para 2 e escrevemos para a consola o valor de `x`.

Após a função `mudarX` executar, dentro da função `inicio`, mudamos o valor de `x` para 5 e escrevemos para a consola o valor de `x`.

Output final:

```
x vale 2
Agora x vale 5
```

Agora vamos mudar o código para que x seja uma variável local.

```C
programa 
{ 
	funcao inicio () 
	{
        inteiro x = 1
	    mudarX()
        x = 5
        escreva("Agora x vale", x)
	} 

    funcao mudarX ()
    {
        x = 2
        escreva("x vale ", x, "\n")
    }
}
```

O programa acima dá erro. O compilador do Portugol avisa-nos que `x` não foi declarado no escopo de `mudarX`.

Isto porque quando declaramos o `x` dentro da função `inicio`, `mudarX` não consegue saber o que é `x` e assim não consegue aceder a essa variável.

> Para quê usar variáveis locais? Não era mais fácil usar apenas variáveis globais?

Não. Variáveis globais têm desvantagens. Variáveis globais existem enquanto o programa executa e ocupam espaço que se calhar não é necessário estarem a ocupar durante a execução do programa inteiro.

Podemos também, alterar o valor de uma variável global em qualquer função acidentalmente.

Variáveis locais são libertadas da memória automaticamente quando a função onde são declaradas termina.

## Passar valores por referência

O argumento de uma função, quando declarado da maneira que já vimos na página [Portugol](./Portugol.md), recebe um valor por **cópia**.

```C
programa 
{
    inteiro x = 1
    funcao inicio () 
	{
	    escreva("Valor inicial de x: ", x, "\n")
        mudarX(x)
        escreva("Valor depois de x ser manipulado na função mudarX(): ", x, "\n")
	} 

    funcao mudarX (inteiro _x)
    {
        _x = 2
        escreva("Aqui dentro de mudarX() o x vale: ", _x, "\n")
    }
}
```

Output do programa:
```
Valor inicial de x: 1
Aqui dentro de mudarX() o x vale: 2
Valor depois de x ser manipulado na função mudarX(): 1
```

Então mudamos o valor de `x` dentro de `mudarX`. Porque é que o valor de `x` dentro da função `inicio` vale 1?

Isto porque, na verdade, não estamos a passar `x` diretamente para a função. Estamos a criar uma cópia e a manipular essa cópia.

Se quisermos alterar o `x` original, temos que usar `&` para passar `x` por referência.

```C
programa 
{
    inteiro x = 1
    funcao inicio () 
	{
	    escreva("Valor inicial de x: ", x, "\n")
        mudarX(x)
        escreva("Valor depois de x ser manipulado na função mudarX(): ", x, "\n")
	} 

    funcao mudarX (inteiro &_x) // <-- Reparem no &
    {
        _x = 2
        escreva("Aqui dentro de mudarX() o x vale: ", _x, "\n")
    }
}
```

Output do programa:
```
Valor inicial de x: 1
Aqui dentro de mudarX() o x vale: 2
Valor depois de x ser manipulado na função mudarX(): 2
```
Assim, passando o valor por referência, estamos a alterar a variável original!