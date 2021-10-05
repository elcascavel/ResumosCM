# Estruturas de Decisão

## se e senao se

O `se` e `senao se` executam código quando uma condição lógica, definida pelo programador, é cumprida.

Vamos ver um exemplo.

```C
inteiro x = 1
se (x == 1) {
    escreva("A variável x tem o valor de " + x)
}
/* Output:
A variável x tem o valor de 1
*/
```
Como definimos que `x` continha o valor de 1, o `se` avaliou `x == 1` e portanto cumpre a condição definida. Logo executa o trecho de código dentro do `se`.

> Nota: `==` é um operador que se usa para comparar dois operandos. Neste caso comparámos o valor de `x` com 1.

Vamos ver outro exemplo onde usamos `senao se` e `senao`

```C
inteiro x
leia(x)

se (x == 1) {
    escreva("A variável x tem o valor de " + x)
}
senao se (x == 2)
{
    escreva("A variável x vale dois!")
}
senao {
    escreva("A variável x não vale 1 nem 2")
}
```

Aqui o utilizador do programa escolhe o valor de `x`. O primeiro `se` é semelhante ao primeiro mas desta vez avalia um `x` que não sabemos o valor que lhe será passado. Fazemos duas condições lógicas.

Caso `x` não tenha o valor de 1 ou 2, o `senao` entra em jogo e executa o trecho de código dentro dele. O `senao` executa sempre que a condição do `se` e `senao se` é falsa.

> Nota: Podemos ter vários `senao se`. O `senao` é opcional.

## escolha caso
Imaginemos que queremos programar um menu de um café. Usar estruturas de decisão como o `se` seria demorado em comparação com o escolha caso.

Vamos ver um exemplo.

```C
inteiro opcao
escreva("Qual é o seu pedido?\n")
leia(opcao)
escolha(opcao)
{
    caso 1:
    escreva("Pediu um shot da casa")
    pare

    caso 2:
    escreva("Pediu um café")
    pare

    caso 3:
    escreva("Pediu um bolinho")
    pare

    [etc...]

    caso contrario:
    escreva("A sua opção não é válida!")   
}
```

Esta estrutura de decisão tem uma peculiaridade; não é possível usar operadores lógicos como no `se`. Aceita apenas valores definidos, ou o valor é igual ou é diferente.

