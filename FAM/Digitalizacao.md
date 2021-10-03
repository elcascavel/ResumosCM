# Digitalização
Digitalização é o processo pelo qual uma imagem ou sinal analógico é transformado em código digital. Este processo também engloba a conversão de sinais de áudio e vídeo. Transforma-se algo complexo para algo mais simples para que possa ser interagida por meio digital (telemóvel, PC, TV etc).

Existem três características usadas para processar diferentes tipos de informação: **amostragem, quantificação, codificação**.

## Amostragem

Amostrar com uma frequência no mínimo igual ao dobro da frequência máxima do sinal - conhecida como frequência de Nyquist. Isto é para que possa ser reproduzido integralmente sem erros.

> Porque não amostrar com uma frequência ainda maior? A digitalização não seria mais precisa?

**Não.** O processamento seria muito mais demorado e o ficheiro resultante ficaria muito maior.

## Quantificação

Consiste em definir uma escala (eixo vertical) e fazer atribuir cada valor da amostragem um valor determinado de amplitude.

Serve para quantificar a infinidade de valores obtidos para que sejam representados por uma quantidade finita de bits de modo a obter um sinal digital.
```
Exemplo
Quantos bits são necessários para codificar uma imagem de 480 por 100 píxeis numa escala de cinzentos com 16 níveis?

Fórmula: altura * largura * 2 elevado a um número cujo resultado, neste caso, seja 16. Portanto será 4 porque 2^4 = 16.

480 * 100 = 48000
48000 * 4 = 192000

São necessários 192,000 bits para codificar esta imagem.
```

```
Exemplo 2
Quantos bits são necessários para codificar um som com frequência máxima de 4kHz em 256 níveis?

Fórmula: 2 * frequência em hz * 2 elevado a um número cujo resultado, neste caso, seja 256. Portanto será 8 porque 2^8 = 256.

2 * 4000 = 8000
8000 * 8 = 64,000

São necessários 64,000 bits para codificar este som.
```