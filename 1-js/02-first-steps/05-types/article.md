# Tipos de dados

Uma variável em JavaScript pode conter quaisquer dados. Uma variável pode em um momento ser uma string e em outro um número:

```js
// nenhum erro
let message = "olá";
message = 123456;
```

As linguagens de programação que permitem tais coisas são chamadas "dinamicamente tipadas", o que significa que existem tipos de dados, mas as variáveis não estão vinculadas a nenhum deles.

<<<<<<< HEAD
Há sete tipos de dados básicos em JavaScript. Aqui, vamos cobri-los em geral e nos próximos capítulos vamos falar sobre cada um deles em detalhe.

## Um número
=======
There are eight basic data types in JavaScript. Here, we'll cover them in general and in the next chapters we'll talk about each of them in detail.

## Number
>>>>>>> c89ddc5d92195e08e2c32e30526fdb755fec4622

```js
let n = 123;
n = 12.345;
```

O tipo *número* representa números inteiros e números de ponto flutuante.

Existem muitas operações para números, por exemplo, multiplicação `*`, divisão `/`, adição `+`, subtração `-`, e assim por diante.

Além dos números regulares, existem os chamados "valores numéricos especiais" que também pertencem a este tipo de dados: `Infinito`, `-Infinito` e `NaN`.

- `Infinito` representa a matemática [Infinity](https://en.wikipedia.org/wiki/Infinity) ∞. É um valor especial que é maior que qualquer número.

    Podemos obtê-lo como resultado da divisão por zero:

    ```js run
    alert( 1 / 0 ); // Infinito
    ```

     Ou apenas referi-lo directamente:

    ```js run
    alert( Infinity ); // Infinito
    ```
- `NaN` representa um erro computacional. É o resultado de uma operação matemática incorreta ou indefinida, por exemplo:

    ```js run
    alert( "not a number" / 2 ); // NaN, tal divisão é errônea
    ```

    `NaN` é pegajoso. Qualquer outra operação em `NaN` retorna `NaN`:

    ```js run
    alert( "not a number" / 2 + 5 ); // NaN
    ```

     Então, se há um `NaN` em algum lugar em uma expressão matemática, ele se propaga para o resultado inteiro.

```smart header="As operações matemáticas são seguras"
Fazer matemática é "seguro" em JavaScript. Podemos fazer qualquer coisa: dividir por zero, tratar strings não-numéricas como números, etc.

O script nunca vai parar com um erro fatal ("morrer"). Na pior das hipóteses, teremos o `NaN` como resultado.
```

Os valores numéricos especiais pertencem formalmente ao tipo "número". Claro que não são números no sentido comum desta palavra.

Veremos mais sobre como trabalhar com números no capítulo <info:number>.

<<<<<<< HEAD
## Uma string
=======
## BigInt

In JavaScript, the "number" type cannot represent integer values larger than <code>2<sup>53</sup></code> (or less than <code>-2<sup>53</sup></code> for negatives), that's a technical limitation caused by their internal representation. That's about 16 decimal digits, so for most purposes the limitation isn't a problem, but sometimes we need really big numbers, e.g. for cryptography or microsecond-precision timestamps.

`BigInt` type was recently added to the language to represent integers of arbitrary length.

A `BigInt` is created by appending `n` to the end of an integer literal:

```js
// the "n" at the end means it's a BigInt
const bigInt = 1234567890123456789012345678901234567890n;
```

As `BigInt` numbers are rarely needed, we devoted them a separate chapter <info:bigint>.

```smart header="Compatability issues"
Right now `BigInt` is supported in Firefox and Chrome, but not in Safari/IE/Edge.
```

## String
>>>>>>> c89ddc5d92195e08e2c32e30526fdb755fec4622

Uma string em JavaScript deve estar entre aspas.

```js
<<<<<<< HEAD
let str = "Olá";
let str2 = 'Aspas simples também são ok';
let phrase = `pode incorporar ${str}`;
=======
let str = "Hello";
let str2 = 'Single quotes are ok too';
let phrase = `can embed another ${str}`;
>>>>>>> c89ddc5d92195e08e2c32e30526fdb755fec4622
```

Em JavaScript, existem 3 tipos de citações.

1. Aspas duplas: `"Olá"`.
2. Aspas simples: `'Olá'`.
3. Backticks: <code>&#96;Olá&#96;</code>.

<<<<<<< HEAD
Aspas duplas e simples são citações "simples". Não há diferença entre elas em JavaScript.
=======
Double and single quotes are "simple" quotes. There's practically no difference between them in JavaScript.
>>>>>>> c89ddc5d92195e08e2c32e30526fdb755fec4622

Backticks são citações de "funcionalidade estendida". Eles nos permitem incorporar variáveis e expressões em uma string envolvendo-as em `$ {…}`, por exemplo:

```js run
let name = "John";

// embed a variable
alert( `Olá, *!*${name}*/!*!` ); // Olá, John!

// embed an expression
alert( `o resultado é *!*${1 + 2}*/!*` ); // o resultado é 3
```

A expressão dentro de `${…}` é avaliada e o resultado torna-se uma parte da string. Podemos colocar qualquer coisa lá: uma variável como `name` ou uma expressão aritmética como `1 + 2` ou algo mais complexo.

Por favor, note que isso só pode ser feito com backticks. Outras citações não têm esta funcionalidade de incorporação!
```js run
alert( "o resultado é ${1 + 2}" ); // o resultado é ${1 + 2} (aspas duplas não fazem nada)
```

Abordaremos as strings mais detalhadamente no capítulo <info:string>.

<<<<<<< HEAD
```smart header="Não há nenhum tipo de *caractere*."
Em algumas linguagens, existe um tipo especial de "caractere" para um único caractere. Por exemplo, na linguagem C e em Java é `char`.
=======
```smart header="There is no *character* type."
In some languages, there is a special "character" type for a single character. For example, in the C language and in Java it is called "char".
>>>>>>> c89ddc5d92195e08e2c32e30526fdb755fec4622

Em JavaScript, não existe tal tipo. Existe apenas um tipo: `string`. Uma string pode consistir de apenas um caractere ou muitos deles.
```

<<<<<<< HEAD
## Um booleano (tipo lógico)
=======
## Boolean (logical type)
>>>>>>> c89ddc5d92195e08e2c32e30526fdb755fec4622

O tipo booleano tem apenas dois valores: `true` e `false`.

Este tipo é comumente usado para armazenar valores de sim/não: `true` significa "sim, correto", e `false` significa "não, incorreto".

Por exemplo:

```js
let nameFieldChecked = true; // sim, o campo do nome é verificado
let ageFieldChecked = false; // não, o campo idade não é verificado
```

Os valores booleanos também vêm como resultado de comparações:

```js run
let isGreater = 4 > 1;

alert( isGreater ); // true (o resultado da comparação é "sim")
```

Abordaremos os booleanos mais profundamente no capítulo <info:logical-operators>.

## O valor "null"

O valor especial `null` não pertence a nenhum dos tipos descritos acima.

Ele forma um tipo separado do seu próprio que contém apenas o valor `null`:

```js
let age = null;
```

Em JavaScript, `null` não é uma "referência a um objeto não-existente" ou um "ponteiro nulo" como em alguns outros idiomas.

É apenas um valor especial que representa "nada", "vazio" ou "valor desconhecido".

O código acima declara que `age` é desconhecido ou vazio por alguma razão.

## O valor "undefined"

O valor especial `undefined` também se diferencia. Faz um tipo próprio, tal como `null`.

O significado de `undefined` é "o valor não é atribuído".

Se uma vaiável é declarada, mas não atribuida, então seu valor é `undefined`:

```js run
let x;

alert(x); // mostra "undefined"
```

Tecnicamente, é possível atribuir `undefined` a qualquer variável:

```js run
let x = 123;

x = undefined;

alert(x); // "undefined"
```

...mas não recomendamos fazer isso. Normalmente, usamos `null` para atribuir um valor "vazio" ou "desconhecido" a uma variável, e usamos `undefined` para verificações como ver se uma variável foi atribuída.

## Objetos e Símbolos

O tipo `object` é especial.

Todos os outros tipos são chamados de "primitivos" porque seus valores podem conter apenas uma única coisa (seja uma string ou um número ou qualquer outro). Por outro lado, os objetos são usados para armazenar coleções de dados e entidades mais complexas. Nós vamos lidar com eles mais adiante no capítulo <info: object> depois que aprendermos mais sobre primitivos.

O tipo `symbol` é usado para criar identificadores únicos para objetos. Nós temos que mencioná-lo aqui para completude, mas é melhor estudar este tipo após os objetos.

## The typeof operator [#type-typeof]

O operador `typeof` retorna o tipo do argumento. É útil quando queremos processar valores de diferentes tipos de forma diferente ou apenas queremos fazer uma verificação rápida.

Suporta duas formas de sintaxe:

1. Como operador: `typeof x`.
2. Como uma função: `typeof(x)`.

Em outras palavras, trabalha com parênteses ou sem eles. O resultado é o mesmo.

A chamada para `typeof x` retorna uma string com o nome do tipo:

```js
typeof undefined // "undefined"

typeof 0 // "number"

typeof 10n // "bigint"

typeof true // "boolean"

typeof "foo" // "string"

typeof Symbol("id") // "symbol"

*!*
typeof Math // "object"  (1)
*/!*

*!*
typeof null // "object"  (2)
*/!*

*!*
typeof alert // "function"  (3)
*/!*
```

As três últimas linhas podem precisar de explicações adicionais:

1. `Math` é um objeto embutido que fornece operações matemáticas. Nós o aprenderemos no capítulo <info:number>. Aqui, ele serve apenas como um exemplo de um objeto.
2. O resultado de `typeof null` é `"object"`. Isso é errado. É um erro oficialmente reconhecido em `typeof`, mantido para compatibilidade. Naturalmente, `null` não é um objeto. É um valor especial com um tipo separado próprio. Assim, outra vez, este é um erro na linguagem.
3. O resultado de `typeof alert` é `"function"`, porque `alert` é uma função da linguagem. Vamos estudar as funções nos próximos capítulos onde veremos que não há nenhum tipo de "função" especial em JavaScript. As funções pertencem ao tipo de objecto. Mas o `typeof` trata-as de forma diferente. Formalmente, é incorrecto, mas muito conveniente na prática.

<<<<<<< HEAD

## Resumo

Existem 7 tipos básicos em JavaScript.

- `number` para números de qualquer tipo: inteiro ou ponto flutuante.
- `string` para cordas. Uma cadeia de caracteres pode ter um ou mais caracteres, não há nenhum tipo de caractere único separado.
- `boolean` para `true`/`false`.
- `null` para valores desconhecidos -- um tipo autônomo que tem um único valor `null`.
- `undefined` para valores não atribuídos -- um tipo autônomo que tem um único valor `undefined`.
- `object` para estruturas de dados mais complexas.
- `symbol` para identificadores exclusivos.
=======
## Summary

There are 8 basic data types in JavaScript.

- `number` for numbers of any kind: integer or floating-point, integers are limited by ±2<sup>53</sup>.
- `bigint` is for integer numbers of arbitrary length.
- `string` for strings. A string may have one or more characters, there's no separate single-character type.
- `boolean` for `true`/`false`.
- `null` for unknown values -- a standalone type that has a single value `null`.
- `undefined` for unassigned values -- a standalone type that has a single value `undefined`.
- `object` for more complex data structures.
- `symbol` for unique identifiers.
>>>>>>> c89ddc5d92195e08e2c32e30526fdb755fec4622

O operador `typeof` nos permite ver qual tipo é armazenado em uma variável.

- Duas formas: `typeof x` ou `typeof(x)`.
- Retorna uma string com o nome do tipo, como `"string"`.
- Para `null` retorna `"object"` -- isso é um erro na linguagem, não é realmente um objeto.

Nos próximos capítulos, nos concentraremos nos valores primitivos e, uma vez familiarizados com eles, passaremos para os objetos.