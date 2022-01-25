# PHP (Teoria)

Linguagem de script fracamente tipada (não é necessário declarar que tipo é a variável manualmente).

Entra o HTTPD que é um programa que corre no servidor web, em segundo plano, e espera por pedidos ao servidor. Este é responsável por copiar o conteúdo do código HTML presente nos ficheiros php para o corpo da mensagem que será enviada ao cliente.

O código PHP é executado pelo HTTPD e insere o texto resultante no corpo da mensagem que será enviada ao cliente juntamente com qualquer HTML.

Para escrever código PHP, usamos uma espécie de chavetas especiais.

```PHP
<?php // <-- chaveta para abrir
echo "Obrigado por leres os meus resumos!;"
?> // <-- chaveta para fechar!
```

O código PHP pode aparecer num ficheiro inteiro e dar `echo` a tags HTML, juntamente com outro texto. Pode também estar no meio de HTML assim:

```PHP
<body>
<p>
<?php // <-- chaveta para abrir
$string = "Obrigado por leres os meus resumos!";
echo $string;
?> // <-- chaveta para fechar!
</p>
</body>
```

## Variáveis
As variáveis são usadas para guardar valores, como texto, números ou arrays. O tipo é atribuído automaticamente consoante o dado que lhe é passado. É possível forçar o tipo.

```PHP
// Inicializadas por valor
$a = 3;
$b = 'gato';
// Inicializadas com tipagem forçada
$valor = (int)10.5;
// Inicializadas por referência
$k = &$a;
```

## Operadores de comparação
Devolvem true ou false consoante o resultado da comparação.
```PHP
$y = 2;
$x = 3;

$y == 2; // verdadeiro pois atribuímos o valor 3 à variável na linha anterior.

$y != $x // verdadeiro pois y é diferente de x.

/*
> maior
>= maior ou igual
< menor
<= menor ou igual
*/
```

## Operadores lógicos

```PHP
&& = e
|| = ou
xor = xor // verdadeiro se um dos operandos for verdadeiro mas não ambos
! = // se for falso
```