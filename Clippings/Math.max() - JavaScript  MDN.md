---
title: "Math.max() - JavaScript | MDN"
source: "https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Math/max"
author:
  - "[[MDN Web Docs]]"
published: 2025-02-18
created: 2025-06-26
description: "Math.max() 関数は、入力引数として与えられた 0 個以上の数値のうち最大の数を返します。引数がなかった場合は -Infinity を返します。"
tags:
  - "clippings"
---
- [Skip to search](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Math/#top-nav-search-input)
- [Skip to select language](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Math/#languages-switcher-button)

[このページはコミュニティーの尽力で英語から翻訳されました。MDN Web Docs コミュニティーについてもっと知り、仲間になるにはこちらから。](https://developer.mozilla.org/ja/docs/MDN/Community/Contributing/Translated_content#%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%96%E3%81%AA%E3%83%AD%E3%82%B1%E3%83%BC%E3%83%AB)

**`Math.max()`** 関数は、入力引数として与えられた 0 個以上の数値のうち最大の数を返します。引数がなかった場合は - [`Infinity`](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Infinity) を返します。

## 試してみましょう

```js
console.log(Math.max(1, 3, 2));
// Expected output: 3

console.log(Math.max(-1, -3, -2));
// Expected output: -1

const array1 = [1, 3, 2];

console.log(Math.max(...array1));
// Expected output: 3
```

## 構文

```js
Math.max()
Math.max(value0)
Math.max(value0, value1)
Math.max(value0, value1, /* … ,*/ valueN)
```

### 引数

[`value1`, `value2`, …, `valueN`](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Math/#value1)

最大値を選択して返すための、 0 個以上の数値です。

### 返値

与えられた数のうちの最大の値です。何れかの引数が [`NaN`](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/NaN) であるか、それに変換された場合は `NaN` を返します。引数が与えられなかった場合は - [`Infinity`](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Infinity) を返します。

## 解説

`max()` は `Math` の静的メソッドですので、生成した `Math` オブジェクトのメソッドとしてではなく、常に `Math.max()` として使用してください（ `Math` はコンストラクターではありません）。

[`Math.max.length`](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Function/length) は 2 であり、最低でも 2 つの引数を処理するよう設計されていることを示唆しています。

## 例

### Math.max() の使用

```js
Math.max(10, 20); // 20
Math.max(-10, -20); // -10
Math.max(-10, 20); // 20
```

### 配列の最大値の取得

[`Array.prototype.reduce()`](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce) を使用して、数値の配列の中にある最大値の要素を、それぞれの値を比較して探し出すことができます。

```js
const arr = [1, 2, 3];
const max = arr.reduce((a, b) => Math.max(a, b), -Infinity);
```

次の関数では [`Function.prototype.apply()`](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Function/apply) を使用して配列の最大値を取得します。 `getMaxOfArray([1, 2, 3])` は `Math.max(1, 2, 3)` と同等ですが、 `getMaxOfArray()` はプログラム的に構築された配列に使用することができます。これは比較的要素が少ない配列に対して使用してください。

```js
function getMaxOfArray(numArray) {
  return Math.max.apply(null, numArray);
}
```

新しい [スプレッド構文](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Operators/Spread_syntax) で、 `apply` によって配列の最大値を得る方法をより短く書くことができます。

```js
const arr = [1, 2, 3];
const max = Math.max(...arr);
```

しかし、スプレッド構文の (`...`) と `apply` のどちらも、配列に膨大な要素があった場合は、配列の要素を関数の引数として渡そうとするため、失敗したり、誤った結果を返したりすることがあります。詳しくは [apply を組み込み関数と共に利用する](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Function/apply#apply_%E3%82%92%E3%83%93%E3%83%AB%E3%83%88%E3%82%A4%E3%83%B3%E9%96%A2%E6%95%B0%E3%81%A8%E5%85%B1%E3%81%AB%E5%88%A9%E7%94%A8%E3%81%99%E3%82%8B) を参照してください。 `reduce` の方法はこの問題が発生しません。

## 仕様書

| Specification |
| --- |
| [ECMAScript® 2026 Language Specification   \# sec-math.max](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.max) |

## ブラウザーの互換性

[![MongoDB Atlas](https://developer.mozilla.org/pimg/aHR0cHM6Ly9zdGF0aWM0LmJ1eXNlbGxhZHMubmV0L3V1LzIvMTYyNjkwLzE3NDg0NDU4MjItTUROXy1fQUlSZXZvbHV0aW9uLUxpZ2h0LTE0NTZ4MTgwLnBuZw%3D%3D.dwndz6s%2Bmvo8de68%2FVZ7dD6i%2FW0hw6UM0vS9FtvHIMU%3D)](https://developer.mozilla.org/pong/click?code=aHR0cHM6Ly9zcnYuYnV5c2VsbGFkcy5jb20vYWRzL2NsaWNrL3gvR1RORDQyN01DVEFESzJKN0NUQUxZS1FVQ1dZREMyM1VDVzdENVozSkNBQklUMjNVQ0tBRDRLSktGVEJES0szSkNXQUQ0SzdNQ1RTRDQ1UVVDRVNJQ0szS0M2U0lQSzM3QzZCRFRLM0VISk5DTFNJWg%3D%3D.%2FQWR1464SmcV5hqPK6SlZSEz41cNZISi9%2FF5hELFc54%3D&version=2) [Ad](https://developer.mozilla.org/en-US/advertising)