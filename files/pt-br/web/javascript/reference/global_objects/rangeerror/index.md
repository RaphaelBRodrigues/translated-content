---
title: RangeError
slug: Web/JavaScript/Reference/Global_Objects/RangeError
---

{{JSRef}}

O objeto **`RangeError`** indica um erro quando um determinado valor está fora dos limites permitidos.

## Descrição

Um `RangeError` é lançado quando se tenta passar um valor como argumento para uma função que não aceita aquele valor, pois o mesmo não se encontra no intervalo aceito

Esse erro pode ocorrer quando

- passa um valor que não é uma das strings permitidas para {{jsxref("String.prototype.normalize()")}}, ou
- quando tenta criar um array com um tamanho inválido usando o construtor {{jsxref("Array")}}, ou 
- quando passa valores inválidos para métodos numéricos {{jsxref("Number.prototype.toExponential()")}}, {{jsxref("Number.prototype.toFixed()")}} ou {{jsxref("Number.prototype.toPrecision()")}}.

## Construtor

- {{jsxref("RangeError/RangeError", "RangeError()")}}
  - : Cria um novo objeto `RangeError`.

## Propriedades da instância

- {{jsxref("Error.prototype.message", "RangeError.prototype.message")}}
  - : Mensagem do erro. Herdado de {{jsxref("Error")}}.
- {{jsxref("Error.prototype.name", "RangeError.prototype.name")}}
  - : Nome do erro. Herdado de {{jsxref("Error")}}.
- {{jsxref("Error.prototype.cause", "RangeError.prototype.cause")}}
  - : Motivo do erro. Herdado de {{jsxref("Error")}}.
- {{jsxref("Error.prototype.fileName", "RangeError.prototype.fileName")}} {{non-standard_inline}}
  - : Caminho do arquivo onde o erro foi lançado. Herdado de {{jsxref("Error")}}.
- {{jsxref("Error.prototype.lineNumber", "RangeError.prototype.lineNumber")}} {{non-standard_inline}}
  - : Linha do arquivo onde o erro foi lançado. Herdado de {{jsxref("Error")}}.
- {{jsxref("Error.prototype.columnNumber", "RangeError.prototype.columnNumber")}} {{non-standard_inline}}
  - : Coluna da linha onde o erro foi lançado. Herdado de {{jsxref("Error")}}.
- {{jsxref("Error.prototype.stack", "RangeError.prototype.stack")}} {{non-standard_inline}}
  - : Stack trace. Herdado de {{jsxref("Error")}}.

## Exemplos

### Usando o RangeError (para valores numéricos)

```js
function check(n) {
  if (!(n >= -500 && n <= 500)) {
    throw new RangeError("O argumento deve ser um valor entre -500 y 500.");
  }
}

try {
  check(2000);
} catch (error) {
  if (error instanceof RangeError) {
    // Tratar o erro
  }
}
```

### Usando o RangeError (para valor não numéricos)

```js
function check(value) {
  if (["apple", "banana", "carrot"].includes(value) === false) {
    throw new RangeError(
      'O argumento deve ser "apple", "banana" ou "carrot"'
    );
  }
}

try {
  check("cabbage");
} catch (error) {
  if (error instanceof RangeError) {
    // Tratar o erro
  }
}
```

## Especificações

{{Specifications}}

## Compatibilidade com navegadores

{{Compat}}

## Veja também

- {{jsxref("Error")}}
- {{jsxref("Array")}}
- {{jsxref("Number.toExponential()")}}
- {{jsxref("Number.toFixed()")}}
- {{jsxref("Number.toPrecision()")}}
- {{jsxref("String.prototype.normalize()")}}
