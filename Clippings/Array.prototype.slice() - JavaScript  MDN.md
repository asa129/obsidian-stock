---
title: "Array.prototype.slice() - JavaScript | MDN"
source: "https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Array/slice"
author:
  - "[[MDN Web Docs]]"
published: 2025-02-18
created: 2025-06-29
description: "slice() は Array インスタンスのメソッドで、配列の一部を start から end （end は含まれない）までの範囲で、選択した新しい配列オブジェクトにシャローコピーして返します。ここで start と end はその配列に含まれる項目のインデックスを表します。元の配列は変更されません。"
tags:
  - "clippings"
---
[このページはコミュニティーの尽力で英語から翻訳されました。MDN Web Docs コミュニティーについてもっと知り、仲間になるにはこちらから。](https://developer.mozilla.org/ja/docs/MDN/Community/Contributing/Translated_content#%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%96%E3%81%AA%E3%83%AD%E3%82%B1%E3%83%BC%E3%83%AB)

**`slice()`** は [`Array`](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Array) インスタンスのメソッドで、配列の一部を `start` から `end` （ `end` は含まれない）までの範囲で、選択した新しい配列オブジェクトに [シャローコピー](https://developer.mozilla.org/ja/docs/Glossary/Shallow_copy) して返します。 ここで `start` と `end` はその配列に含まれる項目のインデックスを表します。元の配列は変更されません。

## 試してみましょう

```js
const animals = ["ant", "bison", "camel", "duck", "elephant"];

console.log(animals.slice(2));
// Expected output: Array ["camel", "duck", "elephant"]

console.log(animals.slice(2, 4));
// Expected output: Array ["camel", "duck"]

console.log(animals.slice(1, 5));
// Expected output: Array ["bison", "camel", "duck", "elephant"]

console.log(animals.slice(-2));
// Expected output: Array ["duck", "elephant"]

console.log(animals.slice(2, -1));
// Expected output: Array ["camel", "duck"]

console.log(animals.slice());
// Expected output: Array ["ant", "bison", "camel", "duck", "elephant"]
```

## 構文

```js
slice()
slice(start)
slice(start, end)
```

### 引数

[`start` 省略可](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Array/#start)

抽出を始める位置のゼロから始まるインデックスで、 [整数に変換されます](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Number#%E6%95%B4%E6%95%B0%E3%81%B8%E3%81%AE%E5%A4%89%E6%8F%9B) 。

- インデックスが負の場合、配列の末尾からさかのぼって数えます。 `start < 0` の場合、 `start + array.length` が使用されます。
- `start < -array.length` または `start` が省略された場合は `0` が使用されます。
- `start >= array.length` の場合、何も抽出されません。

[`end` 省略可](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Array/#end)

抽出し終える位置のゼロから始まるインデックスで、 [整数に変換されます](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Number#%E6%95%B4%E6%95%B0%E3%81%B8%E3%81%AE%E5%A4%89%E6%8F%9B) 。 `slice()` は `end` を含まず、その直前までを抽出します。

- インデックスが負の場合、配列の末尾からさかのぼって数えます。 `end < 0` の場合、 `end + array.length` が使用されます。
- `end < -array.length` の場合は `0` が使用されます。
- `end >= array.length` または `end` が省略された場合は `array.length` が使用され、最後まですべての要素が抽出されます。
- 正規化後に `end` が `start` より前か同じ位置になった場合、何も抽出されません。

### 返値

取り出された要素を含む新しい配列です。

## 解説

`slice()` メソッドは [コピーメソッド](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Array#copying_methods_and_mutating_methods) です。これは `this` を変更するのではなく、元の配列と同じ要素を格納した [シャローコピー](https://developer.mozilla.org/ja/docs/Glossary/Shallow_copy) を返します。

`slice()` メソッドは空のスロットを保持します。スライスされた部分が [疎配列](https://developer.mozilla.org/ja/docs/Web/JavaScript/Guide/Indexed_collections#%E7%96%8E%E9%85%8D%E5%88%97) の場合、返す配列も疎配列になります。

`slice()` メソッドは [汎用的](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Array#%E6%B1%8E%E7%94%A8%E7%9A%84%E3%81%AA%E9%85%8D%E5%88%97%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89) です。これは `this` 値に `length` プロパティと整数キーのプロパティがあることだけを期待します。

## 例

### 既存の配列の一部を返す

```js
const fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
const citrus = fruits.slice(1, 3);

// fruits には ['Banana', 'Orange', 'Lemon', 'Apple', 'Mango'] が含まれる
// citrus には ['Orange','Lemon'] が含まれる
```

### slice の使用

以下の例で、 `slice` は新しい配列 `newCar` を `myCar` から生成します。両者ともオブジェクト `myHonda` への参照を含んでいます。 `myHonda` の色が purple に変更されると、両方の要素がその変更を反映します。

```js
// slice を使って、myCar から newCar を生成する。
const myHonda = {
  color: "red",
  wheels: 4,
  engine: { cylinders: 4, size: 2.2 },
};
const myCar = [myHonda, 2, "cherry condition", "purchased 1997"];
const newCar = myCar.slice(0, 2);

console.log("myCar =", myCar);
console.log("newCar =", newCar);
console.log("myCar[0].color =", myCar[0].color);
console.log("newCar[0].color =", newCar[0].color);

// myHonda の色を変える。
myHonda.color = "purple";
console.log("The new color of my Honda is", myHonda.color);

console.log("myCar[0].color =", myCar[0].color);
console.log("newCar[0].color =", newCar[0].color);
```

このスクリプトの出力は次の様になります。

```
myCar = [
  { color: 'red', wheels: 4, engine: { cylinders: 4, size: 2.2 } },
  2,
  'cherry condition',
  'purchased 1997'
]
newCar = [ { color: 'red', wheels: 4, engine: { cylinders: 4, size: 2.2 } }, 2 ]
myCar[0].color = red
newCar[0].color = red
The new color of my Honda is purple
myCar[0].color = purple
newCar[0].color = purple
```

### 配列以外のオブジェクトに対する slice() の呼び出し

`slice()` メソッドは `this` の `length` プロパティを読み込みます。そして、 `start` から `end` までの整数キーのプロパティを読み込み、新しく作成した配列に定義します。

```js
const arrayLike = {
  length: 3,
  0: 2,
  1: 3,
  2: 4,
  3: 33, // length が 3 であるので slice() から無視される
};
console.log(Array.prototype.slice.call(arrayLike, 1, 3));
// [ 3, 4 ]
```

### slice() を用いて配列風オブジェクトを配列に変換

`slice()` メソッドは [`bind()`](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Function/bind) や [`call()`](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Function/call) と共に、配列風オブジェクトを配列に変換するユーティリティメソッドを作成するためによく使われます。

```js
// slice() は第 1 引数として \`this\` が渡されて呼び出される
const slice = Function.prototype.call.bind(Array.prototype.slice);

function list() {
  return slice(arguments);
}

const list1 = list(1, 2, 3); // [1, 2, 3]
```

### 疎配列に対する slice() の使用

`slice()` から返される配列は、元の配列が疎配列であれば疎配列になります。

```js
console.log([1, 2, , 4, 5].slice(1, 4)); // [2, empty, 4]
```

## 仕様書

| Specification |
| --- |
| [ECMAScript® 2026 Language Specification   \# sec-array.prototype.slice](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.prototype.slice) |

## ブラウザーの互換性

[![MongoDB Atlas](https://developer.mozilla.org/pimg/aHR0cHM6Ly9zdGF0aWM0LmJ1eXNlbGxhZHMubmV0L3V1LzIvMTYyNjkwLzE3NDg0NDU4MjItTUROXy1fQUlSZXZvbHV0aW9uLUxpZ2h0LTE0NTZ4MTgwLnBuZw%3D%3D.dwndz6s%2Bmvo8de68%2FVZ7dD6i%2FW0hw6UM0vS9FtvHIMU%3D)](https://developer.mozilla.org/pong/click?code=aHR0cHM6Ly9zcnYuYnV5c2VsbGFkcy5jb20vYWRzL2NsaWNrL3gvR1RORDQyN01DNllJQ0s3SUNUQUxZS1FVQ1dZSUsyUUxDV1lJTFozSkNBQkk0MjdZRlRCSUNLSktGVEJES0szSkNXQUQ0SzdNQ1RTRDQ1UVVDS0JENjUzS0M2U0lQS1FKRlRZRFZLM0VISk5DTFNJWg%3D%3D.2Zyq6xsyTRy9k8uIVn6kmGP7O0wbwE8twNcpapj3eOQ%3D&version=2) [Ad](https://developer.mozilla.org/en-US/advertising)