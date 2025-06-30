---
title: Map<K, V> | TypeScript入門『サバイバルTypeScript』
source: https://typescriptbook.jp/reference/builtin-api/map
author: 
published: 
created: 2025-06-29
description: MapはJavaScriptの組み込みAPIのひとつで、キーと値のペアを取り扱うためのオブジェクトです。Mapにはひとつのキーについてはひとつの値のみを格納できます。
tags:
  - clippings
  - Map
  - TypeSctipt
  - length
---
`Map` はJavaScriptの組み込みAPIのひとつで、キーと値のペアを取り扱うためのオブジェクトです。 `Map` にはひとつのキーについてはひとつの値のみを格納できます。

## Mapオブジェクトの作り方

`Map` オブジェクトを作るには `Map` クラスを `new` します。たとえば、キーが `string` 、値が `number` の `Map<string, number>` は次のように作ります。

```markdown
tsconst map = new Map<string, number>();
map.set("a", 1);
console.log(map.get("a"));
1
```

```markdown
tsconst map = new Map<string, number>();
map.set("a", 1);
console.log(map.get("a"));
1
```

コンストラクタにキーと値の\[タプル型\] `[K, V]` の配列 `[K, V][]` を渡すと `Map<K, V>` オブジェクトが作られます。

📄️ タプル

TypeScriptの関数は1値のみ返却できます。ですが実際は複数の値を返したくなる時もあります。そんな時は配列に返したいすべての値を入れて返すことがあります。

[View original](https://typescriptbook.jp/reference/values-types-variables/tuple)

```markdown
tsconst map = new Map<string, number>([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
console.log(map);
Map (3) {"a" => 1, "b" => 2, "c" => 3}
```

```markdown
tsconst map = new Map<string, number>([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
console.log(map);
Map (3) {"a" => 1, "b" => 2, "c" => 3}
```

`Map` の型変数を省略した場合、TypeScriptはコンストラクタ引数から `Map<K, V>` の型を推論します。

```markdown
tsconst map = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
map;
const map: Map<string, number>
```
```markdown
tsconst map = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
map;
const map: Map<string, number>
```

コンストラクタ引数を省略した場合、空の `Map` が作られます。

```markdown
tsconst map = new Map<string, number>();
console.log(map);
Map(0) {}
```

```markdown
tsconst map = new Map<string, number>();
console.log(map);
Map(0) {}
```

型引数とコンストラクタ引数の両方を省略した場合、 `Map<any, any>` 型になります。

```markdown
tsconst map = new Map();
      const map: Map<any, any>
```
```markdown
tsconst map = new Map();
      const map: Map<any, any>
```

## Mapの型注釈

TypeScriptでMapの型注釈をする場合は、 `Map<string, number>` のようにMap要素の型を型変数に指定します。

```markdown
tsfunction doSomething(map: Map<string, number>) {}
```
```markdown
tsfunction doSomething(map: Map<string, number>) {}
```

## Mapのキーは厳密等価で判定される

`Map` のキーが同じかどうかは厳密等価(`===`)で判定します。等価(`==`)ではありません。

たとえば、 `null` と `undefined` は等価ですが、厳密等価では等しくありません。

```markdown
tsconsole.log(null == undefined);
true
console.log(null === undefined);
false
```

```markdown
tsconsole.log(null == undefined);
true
console.log(null === undefined);
false
```

そのため、 `Map` は `null` と `undefined` を異なるキーとみなします。

```markdown
tsconst map = new Map<any, any>([[null, 1]]);
console.log(map.has(null));
true
console.log(map.has(undefined));
false
```

```markdown
tsconst map = new Map<any, any>([[null, 1]]);
console.log(map.has(null));
true
console.log(map.has(undefined));
false
```

`NaN` 同士は厳密等価ではありませんが、例外的に同じキーとみなされます。

```markdown
js// JavaScript
 
console.log(NaN === NaN);
false
```

```markdown
js// JavaScript
 
console.log(NaN === NaN);
false
```

```markdown
tsconst map = new Map<number, number>();
map.set(NaN, 1);
map.set(NaN, 2);
console.log(map);
Map (1) {NaN => 2}
```

```markdown
tsconst map = new Map<number, number>();
map.set(NaN, 1);
map.set(NaN, 2);
console.log(map);
Map (1) {NaN => 2}
```

オブジェクトは等価でも厳密等価でもないため、別のキーとみなされます。

```markdown
js// JavaScript
 
console.log({} == {});
false
console.log({} === {});
false
```

```markdown
js// JavaScript
 
console.log({} == {});
false
console.log({} === {});
false
```

```markdown
tsconst map = new Map<object, number>();
map.set({}, 1);
map.set({}, 2);
console.log(map);
Map (2) {{} => 1, {} => 2}
```

```markdown
tsconst map = new Map<object, number>();
map.set({}, 1);
map.set({}, 2);
console.log(map);
Map (2) {{} => 1, {} => 2}
```

## Mapの操作

### 要素をセットする - Map.prototype.set()

`Map` にキーと値のペアを追加するには `set` メソッドを使います。

```markdown
tsconst map = new Map<string, number>();
map.set("a", 1);
console.log(map);
Map (1) {"a" => 1}
```

```markdown
tsconst map = new Map<string, number>();
map.set("a", 1);
console.log(map);
Map (1) {"a" => 1}
```

すでにキーがある場合は、値を上書きします。

```markdown
tsconst map = new Map([["a", 1]]);
map.set("a", 5);
console.log(map);
Map (1) {"a" => 5}
```

```markdown
tsconst map = new Map([["a", 1]]);
map.set("a", 5);
console.log(map);
Map (1) {"a" => 5}
```

### 値を取得する - Map.prototype.get()

`Map` からキーをもとに要素を取得するには `get` メソッドを使います。

```markdown
tsconst map = new Map([["a", 1]]);
console.log(map.get("a"));
1
```

```markdown
tsconst map = new Map([["a", 1]]);
console.log(map.get("a"));
1
```

`get` メソッドは、キーが存在しない場合、 `undefined` を返します。

```markdown
tsconst map = new Map([["a", 1]]);
console.log(map.get("b"));
undefined
```

```markdown
tsconst map = new Map([["a", 1]]);
console.log(map.get("b"));
undefined
```

Null合体演算子と組み合わせることによって `get` メソッドで値を取得できなかったときにデフォルトの値を代入することができます。

```markdown
tsconst map = new Map([["a", 1]]);
console.log(map.get("b") ?? 2);
2
```

```markdown
tsconst map = new Map([["a", 1]]);
console.log(map.get("b") ?? 2);
2
```

### 特定の要素を削除する - Map.prototype.delete()

`Map` からキーを指定して要素を削除するには `delete` メソッドを使います。

```markdown
tsconst map = new Map([
  ["a", 1],
  ["b", 2],
]);
map.delete("a");
console.log(map);
Map (1) {"b" => 2}
```

```markdown
tsconst map = new Map([
  ["a", 1],
  ["b", 2],
]);
map.delete("a");
console.log(map);
Map (1) {"b" => 2}
```

`delete` の戻り値は、キーが存在した場合 `true` 、そうでない場合 `false` になります。

```markdown
tsconst map = new Map([["a", 1]]);
console.log(map.delete("a"));
true
console.log(map.delete("b"));
false
```

```markdown
tsconst map = new Map([["a", 1]]);
console.log(map.delete("a"));
true
console.log(map.delete("b"));
false
```

### キーの有無を確認する - Map.prototype.has()

`Map` にキーが存在するかどうかを調べるには `has` メソッドを使います。

```markdown
tsconst map = new Map([["a", 1]]);
console.log(map.has("a"));
true
console.log(map.has("b"));
false
```

```markdown
tsconst map = new Map([["a", 1]]);
console.log(map.has("a"));
true
console.log(map.has("b"));
false
```

### 要素の個数を取得する - Map.prototype.size()

`Map` に登録されている要素数を調べるには `size` フィールドの値を見ます。

```markdown
tsconst map = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
console.log(map.size);
3
```

```markdown
tsconst map = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
console.log(map.size);
3
```

### 全要素を削除する - Map.prototype.clear()

`Map` に登録されている要素をすべて削除するには `clear` メソッドを使います。

```markdown
tsconst map = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
console.log(map.size);
3
map.clear();
console.log(map.size);
0
```

```markdown
tsconst map = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
console.log(map.size);
3
map.clear();
console.log(map.size);
0
```

### キーを列挙する - Map.prototype.keys()

`keys` メソッドはキーの反復可能オブジェクトを返します。

```markdown
tsconst map = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
const keys = [...map.keys()];
console.log(keys);
["a", "b", "c"]
```

```markdown
tsconst map = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
const keys = [...map.keys()];
console.log(keys);
["a", "b", "c"]
```

### 値を列挙する - Map.prototype.values()

`values` メソッドは値の反復可能オブジェクトを返します。

```markdown
tsconst map = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
const values = [...map.values()];
console.log(values);
[1, 2, 3]
```

```markdown
tsconst map = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
const values = [...map.values()];
console.log(values);
[1, 2, 3]
```

### キーと値のペアを列挙する - Map.prototype.entries()

`entries` メソッドはキーと値の反復可能オブジェクトを返します。

```markdown
tsconst map = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
const keyValues = [...map.entries()];
console.log(keyValues);
[["a", 1], ["b", 2], ["c", 3]]
```

```markdown
tsconst map = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
const keyValues = [...map.entries()];
console.log(keyValues);
[["a", 1], ["b", 2], ["c", 3]]
```

### キーと値のペアを反復する

`Map` は `for...of` で反復できます。反復の順序は登録された順です。

```markdown
tsconst map = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
 
for (const [key, value] of map) {
  console.log(key, value);
  // "a", 1
  // "b", 2
  // "c", 3 の順で出力される
}
```
```markdown
tsconst map = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
 
for (const [key, value] of map) {
  console.log(key, value);
  // "a", 1
  // "b", 2
  // "c", 3 の順で出力される
}
```

### 複製する

`Map` オブジェクトを複製(シャローコピー)するには、MapオブジェクトをMapコンストラクタに渡します。

```markdown
tsconst map1 = new Map([["a", 1]]);
const map2 = new Map(map1);
console.log(map2);
Map (1) {"a" => 1}
```

```markdown
tsconst map1 = new Map([["a", 1]]);
const map2 = new Map(map1);
console.log(map2);
Map (1) {"a" => 1}
```

## Mapは直接JSONにできない

`Map` オブジェクトはJSON.stringifyにかけても、登録されている要素はJSONになりません。

```markdown
tsconst map = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
console.log(JSON.stringify(map));
"{}"
```

```markdown
tsconst map = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
console.log(JSON.stringify(map));
"{}"
```

`Map` をJSON化する場合は、一度オブジェクトにする必要があります。

```markdown
tsconst map = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
const obj = Object.fromEntries(map);
console.log(JSON.stringify(obj));
"{"a":1,"b":2,"c":3}"
```

```markdown
tsconst map = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
const obj = Object.fromEntries(map);
console.log(JSON.stringify(obj));
"{"a":1,"b":2,"c":3}"
```

## 他の型との相互運用

### Mapを配列にする

`Map<K, V>` にスプレッド構文を使うと、タプル型配列 `[K, V][]` が得られます。

```markdown
tsconst map = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
const keyValues = [...map];
console.log(keyValues);
[["a", 1], ["b", 2], ["c", 3]]
```

```markdown
tsconst map = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
const keyValues = [...map];
console.log(keyValues);
[["a", 1], ["b", 2], ["c", 3]]
```

### オブジェクトをMapにする

オブジェクトを `Map` に変換するには、 `Object.entries` の戻り値をMapコンストラクタに渡します。

```markdown
tsconst obj = { a: 1, b: 2, c: 3 };
const map = new Map(Object.entries(obj));
console.log(map);
Map (3) {"a" => 1, "b" => 2, "c" => 3}
```

```markdown
tsconst obj = { a: 1, b: 2, c: 3 };
const map = new Map(Object.entries(obj));
console.log(map);
Map (3) {"a" => 1, "b" => 2, "c" => 3}
```

### Mapをオブジェクトにする

Mapをオブジェクトにするには、 `Object.fromEntries` にMapオブジェクトを渡します。

```markdown
tsconst map = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
const obj = Object.fromEntries(map);
console.log(obj);
{ "a": 1, "b": 2, "c": 3 }
```

```markdown
tsconst map = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
const obj = Object.fromEntries(map);
console.log(obj);
{ "a": 1, "b": 2, "c": 3 }
```

## Mapとオブジェクトの違い

キーと値のペアが表現ができるという点で、 `Map` とオブジェクトは似ていますが、次の違いがあります。

| 違い | `Map` | オブジェクト |
| --- | --- | --- |
| プロトタイプキーの上書き | 起きない | 起こりうる |
| キーに使える型 | 任意の型 | `string` か `symbol` |
| 反復の順序 | 挿入順 | 複雑なロジック |
| JSON化 | 直接できない | 直接できる |

### プロトタイプキーの上書き

オブジェクトはプロトタイプのキーを上書きする可能性があります。

```markdown
jsconst obj = {};
console.log(obj.toString);
function toString() { [native code] }
obj.toString = 1;
console.log(obj.toString);
1
```

```markdown
jsconst obj = {};
console.log(obj.toString);
function toString() { [native code] }
obj.toString = 1;
console.log(obj.toString);
1
```

`Map` は要素をセットしてもプロトタイプのキーを上書きする心配がありません。要素とプロトタイプは別の領域にあるためです。

```markdown
tsconst map = new Map<string, any>();
console.log(map.toString);
function toString() { [native code] }
map.set("toString", 1);
console.log(map.toString);
function toString() { [native code] }
```

```markdown
tsconst map = new Map<string, any>();
console.log(map.toString);
function toString() { [native code] }
map.set("toString", 1);
console.log(map.toString);
function toString() { [native code] }
```

### キーに使える型

オブジェクトのキーに使える型は `string` 型か `symbol` 型のどちらです。 `Map` は任意の型をキーにできます。

### 反復の順序

オブジェクトのプロパティの反復順序は、書いた順や追加した順ではなく、複雑なロジックになっています。

📄️ オブジェクトをループする方法

JavaScript・TypeScriptでオブジェクトのプロパティをループする方法を説明します。

[View original](https://typescriptbook.jp/reference/values-types-variables/object/how-to-loop-an-object)

`Map` の要素の反復順序は要素を追加した順であることが保証されています。

### JSON化

オブジェクトはそのまま `JSON.stringify` でJSON化できます。 `Map` は `JSON.stringify` しても要素はJSONになりません。一度 `Map` をオブジェクトに変換する必要があります。

### Mapとオブジェクトの書き方比較

`Map` とオブジェクトは似た操作ができます。次がその対応表です。

|  | `Map` | オブジェクト |
| --- | --- | --- |
| 型注釈の書き方 | `Map<K, V>` | `Record<K, V>` |
| 初期化 | `new Map([["a", 1]])` | `{ a: 1 }` |
| 要素のセット | `map.set(key, value)` | `obj[key] = value` |
| 値の取得 | `map.get(key)` | `obj[key]` |
| 要素の削除 | `map.delete(key)` | `delete obj.key` |
| キーの有無確認 | `map.has(key)` | `key in obj` |
| 要素数の取得 | `map.size` | `Object.keys(obj).length` |
| 全要素削除 | `map.clear()` | \- |
| キーの列挙 | `map.keys()` | `Object.keys(obj)` |
| 値の列挙 | `map.values()` | `Object.values(obj)` |
| 要素の列挙 | `map.entries()` | `Object.entries(obj)` |
| 複製 | `new Map(map)` | `{ ...obj }` |

📄️ Record<Keys, Type>

キー・バリューからオブジェクト型を作る

[View original](https://typescriptbook.jp/reference/type-reuse/utility-types/record)