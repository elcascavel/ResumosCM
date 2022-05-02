# Programação Orientada a Objetos (OOP)

Em termos simples:
- Programação Procedimental consiste numa série de passos a executar.
- Programação Orientada a Objetos baseia-se em objetos que são instâncias de classes.

## Classes

A definição de uma classe começa com a palavra chave `class`, seguido de um nome para a mesma.
Esta pode conter `variáveis` que neste contexto são chamadas de `propriedades` e `funções` chamadas de `métodos`.

Uma propriedade declarada sem um modificador de acesso (public, protected ou private) será public automaticamente.

```php
<?php
    class MyClass
    {
        // propriedade
        public $var = 'a minha variável';

        // método
        public function displayVar() 
        {
            echo $this->$var;
        }
    }
?>
```

`$this` é uma pseudo-variável usada quando queremos aceder a uma propriedade do objeto em que está inserida. Caso `$this` não fosse usada no exemplo acima, estariamos a criar uma variável nova.

```php
public function displayVar() 
        {
            echo $var;
        }
```
O `echo` acima não estaria fazer algo! Seria mostrada uma página completamente em branco.

Para criar uma instância da classe teriamos que escrever...
```php
$instance = new MyClass();
```

## Construtores

Construtores são chamados automaticamente quando criamos uma instância da classe. No entanto, podemos declarar o construtor manualmente quando queremos passar parâmetros ao instanciar o objeto.

```php
<?php
    class Dog
    {
        public $_name = "Godrick";
        public $_breed;
        public $_age;

        public function __construct($name, $breed, $age) 
        {
            $this->_breed = $breed;
            $this->_age = $age;
        }
    }

    $dog = new Dog("Margit", "German Shepherd", 3);
    echo "The dog's name is " . $dog->_name . "<br>";
    echo "The dog's breed is " . $dog->_breed . "<br>";
    echo "The dog's age is " . $dog->_age . " years old";
?>
```

Isto daria print do seguinte:
The dog's name is Godrick
The dog's breed is German Shepherd
The dog's age is 3 years old

Como não dissemos que a propriedade `$_name` é igual ao parâmetro `$name` do construtor, o nome permanecerá Godrick e não Margit.

