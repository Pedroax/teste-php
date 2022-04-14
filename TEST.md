# Teste para pessoa desenvolvedora PHP

[← Voltar](README.md).

⚠️ Todas as perguntas são baseadas no **PHP 7.4.28**.

## Exemplo

### 0. Quais os valores de `$a` e `$b` no código abaixo? Por quê?

```php
$a = array_merge(array(1,2), NULL);
$b = array_merge($a, array(3));

var_dump($a);
var_dump($b);
```

> ```
> NULL
> NULL
> ```
> 
> A função `array_merge` retorna `NULL` quando qualquer um dos argumentos não for do tipo `array`. Embora o PHP 7 emita warnings sobre erro no tipo do argumento nem toda instalação está configurada para exibir warnings, logo é importante o desenvolvedor verificar os valores maualmente antes da chamada do `array_merge`, especialmente quando estamos concatenando o retorno de um `array_merge`.
>
> No PHP 8 esse comportamento foi atualizado para emitir um erro, o que ajuda a prevenir problemas.
> 
> ```
> Fatal error: Uncaught TypeError: array_merge(): Argument #2 must be of type array
> ```

## Perguntas

### 1. Qual a diferença entre `echo` e `print`?

> Echo e print é uma maneira de mostrar um resultado na tela. O echo pode mostrar uma variavel, varias variaveis, pode fazer somas, é como se fosse uma saída. Quando vamos usar o echo junto com varivel, precisamos colocar aspas duplas, pq ele consegue entender que é uma variavel e imprimir o texto com o valor dela. se usar aspas simples ele entende a variavel como um texte normal. O 2 são não funções.
echo: Com o echo é possivel ultilizar varias strigins.
echo "hello Word!!", "Olá mundo!!";
vai imprimir na tela.

 Print: so aceita 1 argumento e sempre retorna 1. Pode ultilizaar 1 string.
print "hello Word!!", "Olá mundo!!";

Parse error: syntax error, unexpected ',' in C:\xampp\htdocs\exemplos\exemplo-001.php on line 3 

### 2. Qual é a saída do código abaixo? Por quê?

```php
$x = true and false;
var_dump($x);
```

> Vai retornar um: bool(true)

A resposta a cima da um valor true. Por quê? = tem uma procedêcia maior do que and, então a variável $x recebe o valor de true.
ex: ($x = true) and false 
Se o desenvolvedor quiser que a resposta de false, é so trocar o and por &&.

### 3. Qual é a saída do código abaixo? Por quê?

```php
$x = 5;
$a = array(
    $x++ + $x++,
    $x,
    $x-- - $x--,
    $x,
);

var_dump($a);
```

> A variavel $a que é um array na posção [0] você tem o operado ++ que incrementa 1 na equoação, isso faz om o que o valor da posção [0] seja 11, pq 5 + 1 + 1 = 11.
A chave [1] do arry $a é 7, pois ele conta com os incrementadores passados.
A chave [2] que é que vale a 1 também leva me conta um incrementador passado, por isso seu valor é 1.
A chave [3] que é um 5 não leva em conta nenhum dos indrementadores.

### 4. Quais serão os valores de `$a` e `$b` após a execução do código abaixo? Por quê?

```php
$a = '1';
$b = &$a;
$b = "2$b";
```

>   O valor de $a é 21 e o valor de $b é 21 tbm. por quê? Quando você atualiza o valor de $b, você está realmente atualizando o valor armazenado no bloco de memória para o qual $a e $b apontam, então, uma vez que você tenha definido $b para um valor específico, $a será o mesmo valor porque ambos fazem referência à mesma coisa.

### 5. O que são Traits e para que servem? 

> O traits é possivel definir metodos e propriedades para complementar as classes sem que seja necressario estender dessas classes. Pode ser chamado de herança orizontal, pq não tem alteração do nivel na hierarquia. Nas classes so podemos estender metodos e propiedades da classe pai em sua totalidade, porém tem momentos que precisamos compartilhar comportamentos entre classes que não estão no mesmo contexto. Quando isso acontecer o desenvolvedor precisa utilizar os Traits, para resolver esse problema.

### 6. Qual será a saída do código abaixo? Por quê?

```php
var_dump(0123 == 123);
var_dump('0123' == 123);
var_dump('0123' === 123);
```

> 
primeiro: false
segundo: true
terceiro: false

No php quando usamos == ele verifica se os valores são iguais, então 10=='10'=>true, quando usamos os operado === ele verifica se os valores e tipo de daos são iguais, logo 10==='10' => false.4

O primeiro é false, pois ele faz uma comparação direta entre os dois argumentos. 
O segundo é true, pq ele compara uma string com um número e ele encontra o numero dentro da string.
O terceiro é false, pois usando o === ele compara os tipos, no caso uma string e um numero, tornando este comparativo false.

### 7. Qual será a saída do código abaixo? Por quê?

```php
$a = '';
$b = 0;
$c = '0a';

var_dump($a == $b);
var_dump($b == $c);
var_dump($c == $a);
```

> A saidas desse codigo é: bool(true) bool(true) bool(false).

A primeira:$a é igual uma string vazia e $b é igual 0, por isso que da true , pq zero e vazio é a mesma coisa.
 A segunda: É pq $a é vazio,$c é 0a e tem zero dentro do $c, o php essta tentando comparar numeros com string.
A terceiro: $a é vazio , $c tem 0a , da false pq dentro de $c exite um a e o php esta tentando de novo comprar numero com string.

### 8. Qual será o valor de `$x` após a execução do código abaixo? Por quê?

```php
$x = 3 + "15%";
```

> Essa execução da um erro, pq esse valor numérico não esta certo. 

### 9. Qual a diferença entre `require_once()` e `include_once()`?

> A diferença de require e include.
O require ele obriga que o arquivo exista e que o arquivo esteja funcionando corretamente, se não estiver funcionando ou não existir, o require gera um erro. 

O include tenta funcionar mesmo que o arquivo não exista ou com alguma tipo de problema e o include tem mais recursos, por exemplo: exite um diretorio chamado include path que permite que o include traga arquivos direto de la, esse diretorio por padrão ele é configurado no php. 

Para evitar o laço de chamar um arquivo mais de duas vezes usamos o require_once ou inclide_once.

### 10. Qual será o valor de `$name` após a execução do código abaixo? Por quê?

```php
$name = 'John ';
$name[10] = 'Doe';
```

> Na primeira linha codigo, a bvariavel $name vai ter como valor a string john, na segunda linha de codigo na posição [10] a variavel tomara a string doe.

### 11. Qual será a saída do código abaixo? Por quê?

```php
$x = PHP_INT_MAX;
echo gettype($x + 1);
echo (int)($x + 1);

$y = 1.0;
echo is_float($y);
echo gettype($y);
```

> Na primeira linha de codigo a varaivel $x esta recebendo o valor maximo que o php pode guardar dentro de uma variavel.
Na segunda linha esta fazendo um echo do tipo da variavel $x, no caso um double + 1.
Na terça linha de codigo esta fazendo um typecast da variavel $x + 1 transformando esta equoação em um inteiro.
A variavel $y esta recebendo 1.0. E esta equoando a função is_float que valida se a variavel $y é um float.
Na linha seguinte a função gettype busca o tipo da variavel $y que no caso é um double.S

### 12. Qual será o valor de `$x` após a execução do código abaixo? Por quê?

```php
$x = "one" + 1;
```

> Da um erro. Esse código esta tentando atribuir algo não numerico a um valor numero.

### 13. Qual a diferença entre `isset()` e `empty()`?

> Empty: Ela verifica se uma variavel é considerada vazia e para que uma variavel seja considerada vazia ela precisa atender umas das duas condições: ou ela não existir (não deifinir um valor antes) ou se o valor dela igual a false.

Isset: Verifica se a varaivel foi iniciada , se foi declarada anteriormente. Aunica exceção que não atende que não antende a condição do isset é colocar null nunca variavel.
ex:
$i = null;
