# Arrays

Array é uma estrutura de dados que representam uma lista de tamanho estático (não é possível mudar o tamanho após ter sido definida), onde podemos guardar elementos de um tipo à nossa escolha.

```C
inteiro array[10]
```

Acima declaramos um array de inteiros com 10 posições. No entanto não definimos valores nessas mesmas posições. Em Portugol, ao contrário de outras linguagens como C, os elementos são definidos com o valor de 0 quando não os definimos explicitamente.

## Declarar um array

Declarar um array explicitamente. Aqui todas as posições têm o valor de 1:

```C
inteiro array[] = {1, 1, 1, 1}
```

Declarar um array com 4 posições sem definir valores.

```C
inteiro array[4]
```

## Como aceder e alterar os valores de um array?

`array[0] = 2` guarda na posição 0 do array o valor 2.

`array[0] = x` podemos guardar o valor de uma variável também!