O JavaScript é uma linguagem conhecida por suas falhas e considerada por muitos uma linguagem inconfiável. Isso porque é possível concatenar objetos, somar strings com classes, alterar o comportamento de funções core da linguagem e por aí vai.

No entanto, em 2015, juntamente do ECMAScript 5, uma nova diretiva foi adicionada ao JavaScript, com uma série de regras que tem o objetivo de evitar erros de semântica silenciosos no JavaScript. Essa diretiva é o `use strict`, que é usado por padrão em transpiladores como Typescript e Babel, e é algo importante para evitar erros em produção de forma inesperada.

Ao adicionar essa *string* no começo de cada arquivo JavaScript, o compilador vai validar essas regras, evitando, por exemplo, que você adicione valores a uma variável inexistente, crie variáveis com palavras chave reservada ou até que force a remoção de instâncias em memória.

As principais vantagens de usar o [[Strict Mode]] são:

- **Evita variáveis globais acidentais**:
  No JavaScript normal, se você atribuir um valor para uma variável que não havia sido definida anteriormente, é criada uma variável global. Caso o [[Strict Mode]] esteja ativo, um erro será gerado no momento em que essa atribuição de valor acontece.
  
```js
'use strict';

/**
* O código abaixo vai lançar um erro porque `x` não foi declarado.
*/
x = 10;
```

- **Elimina erros silenciosos**:
  No JavaScript normal, algumas operações podem falhar de forma silenciosa, como, por exemplo, quando tentamos atribuir um valor à uma propriedade que não permite escrita. Com o [[Strict Mode]], esse tipo de falha acaba gerando erros, que facilitam a identificação por parte do desenvolvedor.

```js
'use strict';

Object.defineProperty(this, "PI", { value: 3.14159, writable: false });

/**
* O código abaixo vai lançar um erro porque `PI` é uma propriedade que não permite escrita.
*/
PI = 3.14
``` 

- **Impede a utilização de parâmetros duplicados**:
  Usando o [[Strict Mode]], não é permitido usar o mesmo nome para multiplos parâmetros em uma mesma função.

```js
'use strict';

/**
* O código abaixo vai lançar um erro porque dois parâmetros são definidos como `a`.
*/
function sum(a, a, c) {
	return a + a + c;
}

```

- **Impede o `this` de referenciar um objeto global**:
  Em funções normais do JavaScript, a palavra chave `this` vai, por padrão, fazer referência a um objeto global, como o `window` nos navegadores. No entanto, quando o [[Strict Mode]] está sendo usado, esse comportamento é alterado para retornar `undefined`, aumentando a segurança e evitando efeitos colaterais não desejados.

```js
'use strict';

function showThis() {
	/**
	* O código abaixo vai printar `undefined`, ao invés do objeto global.
	*/
	console.log(this);
}

showThis()
```

- **Impede a deleção de propriedades que não podem ser deletadas**:
  No JavaScript normal, deletar uma propriedade não deletável não tem efeito. Já com o [[Strict Mode]], será lançado um erro;

```js
'use strict';

/**
* O código abaixo vai lançar um erro porque não é permitido apagar a propriedade `prototype` do `Object`.
*/
delete Object.prototype;
```

---

O JavaScript é uma linguagem que é convertida para binário no motor do [[Node.js]]. Por conta disso, existe um processo de otimização que verifica seu código a todo momento, analisando se consegue gerar uma nova classe otimizada, se consegue encurtar caminhos e por aí vai. Quanto mais otimizado nosso código for, mais fácil e rápido será o processo de compilação para a linguagem intermediária.

---
```js
'use strict';

/**
* Now, we can assign a value to an undefined varaible.
* In this case, it will thrown an `not defined` error;
*/
x = 3.14;
x = { p1: 10, p2: 20 };

/**
* Deleting a function or a variable is also not allowed
*/
const y = 3.14;
function z(p1, p2) { };

delete z;
delete y;

/**
* Duplicating a parameter name is not allowed
*/
function x(p1, p1) {};

/**
* Escape characters are not allowed
*/
let obj = {};
Object.defineProperty(obj, "x", { value: 0, writable: false });
obj.x = 3.14;
```