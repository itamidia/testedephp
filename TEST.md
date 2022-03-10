# Teste para pessoa desenvolvedora PHP


[← Voltar](README.md).

⚠️ Todas as perguntas são baseadas no **PHP 7.4.28**.

## Exemplo

### 0. Qual é a saída do código abaixo? Por quê?

```php
$a = array_merge(array(1,2), NULL);
var_dump($a);
$b = array_merge(array(1,2), 3);
var_dump($b);
```

> ```
> NULL
> NULL
> ```
>
> A função `array_merge` retorna `NULL` quando qualquer um dos argumentos não for do tipo `array`. 
Embora o PHP 7 emita warnings sobre erro no tipo do argumento nem toda instalação está configurada para exibir warnings, 
logo é importante o desenvolvedor verificar os valores maualmente antes da chamada do `array_merge`.
>
> No PHP 8 esse comportamento foi corrigido para emitir um erro, o que ajuda a prevenir problemas.
> 
> ```
> Fatal error: Uncaught TypeError: array_merge(): Argument #2 must be of type array
> ```

## Perguntas

### 1. Qual a diferença entre `echo` e `print`?

> Print é uma função ex: Print () onde sempre é retornado o valor 1
Echo é uma declaração embutida da linguagem e não retorna, 
sendo assim sendo ligeiramente mais rapido, o mesmo retorna qualquer tipo de valor ex: echo ("Texto").

### 2. Qual é a saída do código abaixo? Por quê?

```php
$x = true and false;
var_dump($x);
```

Saida impresso algo como:
bool(true)


> A constante true é atribuida a $x antes que o and ocorra a ação funcionando tal como: (($x = true) and false) 
ou seja a execução primeiro entre os parenteses ()

### 3. Qual é a saída do código abaixo? Por quê?

```php
$x = 5;

var_dump(array(
    $x++ + $x++, $x,
    $x-- + $x--, $x,
));
```

> Saida impresso:
array(4) { [0]=> int(11) [1]=> int(7) [2]=> int(13) [3]=> int(5) } int(5)

Arrays e objetos são explorados recursivamente com valores identados na estrutura mostrada

### 4. Quais serão os valores de `$a` e `$b` após a execução do código abaixo? Por quê?

```php
$a = '1';
$b = &$a;
$b = "2$b";
```

> Ambas terão resultado impresso string(2) "21" 
Porque nesse caso será concatenado o valor 2 + 1 como string e não como numero

### 5. O que são Traits e para que servem? 

> Traits podem ser utilizadas para que compartilhemos determinadas funcionalidades, como o famoso copiar e colar
entre classes que não são relacionadas por hierarquia ou tipos diferentes.

### 6. Qual será a saída do código abaixo? Por quê?

```php
var_dump(0123 == 123);
var_dump('0123' == 123);
var_dump('0123' === 123);
```

> Saida impressa para bool(false) bool(true) bool(false)
A resposta de var_dump(0123 == 123) vai produzir bool(falso) porque o líder 0 em 0123 diz ao intérprete PHP para tratar o valor como valor octal (em vez de decimal), 
e 123 octal é igual a 83 decimais, de modo que os valores não são iguais. var_dump ('0123' == 123) produzirá bool(verdade) uma vez que a string 0123 será automaticamente coagida a um inteiro quando comparada com um valor inteiro. 
quando essa conversão é realizada, o líder 0 é ignorado e o valor é tratado como um valor decimal (em vez de octal), de modo que os valores são incomodados 123 (decimais) e, portanto, são iguais. var_dump ('0123' === 123) sai bool(falso) 
uma vez que realiza uma comparação mais rigorosa e não faz a coerção automática do tipo da corda a um inteiro.‎

### 7. Qual será a saída do código abaixo? Por quê?

```php
$a = '';
$b = 0;
$c = '0a';

var_dump($a == $b);
var_dump($b == $c);
var_dump($c == $a);
```

> Saida impressa bool(true) bool(true) bool(false)

### 8. Qual será o valor de `$x` após a execução do código abaixo? Por quê?

```php
$x = 3 + "15%";
```

>Será impresso o valor int(18)

### 9. Qual a diferença entre `require_once()` e `include_once()`?

> Ambas permitem a inclusão de um arquivo uma unica vez, ignorando caso você erre e a chame mais de uma vez.
No caso de erro o require para sua execução enquanto o include não para.


### 10. Qual será o valor de `$name` após a execução do código abaixo? Por quê?

```php
$name = 'John ';
$name[10] = 'Doe';
```

> Saida impressa string(11) "John D"
Array de John + Doe 

### 11. Qual será a saída do código abaixo? Por quê?

```php
$x = PHP_INT_MAX;
echo gettype($x + 1);
echo (int)($x + 1);

$y = 1.0;
echo is_float($y);
echo gettype($y);
```

> Saida impressa:
double
-9223372036854775808

1
double

‎A função gettype () é uma ‎‎função embuttililhada em‎‎ PHP que é usada para obter o tipo de variável. 
É usado para verificar o tipo de variável existente. 
Parâmetro: Esta função aceita um único parâmetro $var. 
É o nome da variável que é necessário para ser verificado para o tipo de variável. 
Valor de retorno: Esta função retorna um valor de tipo de sequência.‎


### 12. Qual será o valor de `$x` após a execução do código abaixo? Por quê?

```php
$x = "one" + 1;
```

>Saida impressa int(1)

Variavel inteira

### 13. Qual a diferença entre `isset()` e `empty()`?

> Isset verifica a existencia de uma variavel ou outro elemento e o empty verifica se existe valor na variavel

