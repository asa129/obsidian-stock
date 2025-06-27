---
title: "useState – React"
source: "https://ja.react.dev/reference/react/useState#ive-updated-the-state-but-logging-gives-me-the-old-value"
author:
  - "[[@reactjs]]"
published:
created: 2025-06-07
description: "The library for web and native user interfaces"
tags:
  - "clippings"
---
[API Reference](https://ja.react.dev/reference/react)

[フック](https://ja.react.dev/reference/react/hooks)

## useState

`useState` は、コンポーネントに [state 変数](https://ja.react.dev/learn/state-a-components-memory) を追加するための React フックです。

- [リファレンス](https://ja.react.dev/reference/react/#reference)
	- [`useState(initialState)`](https://ja.react.dev/reference/react/#usestate)
	- [`setSomething(nextState)` のように利用する `set` 関数](https://ja.react.dev/reference/react/#setstate)
- [使用法](https://ja.react.dev/reference/react/#usage)
	- [state をコンポーネントに追加する](https://ja.react.dev/reference/react/#adding-state-to-a-component)
	- [直前の state に応じて更新する](https://ja.react.dev/reference/react/#updating-state-based-on-the-previous-state)
	- [オブジェクトや配列の state を更新する](https://ja.react.dev/reference/react/#updating-objects-and-arrays-in-state)
	- [初期 state が再生成されることを防ぐ](https://ja.react.dev/reference/react/#avoiding-recreating-the-initial-state)
	- [key を利用して state をリセットする](https://ja.react.dev/reference/react/#resetting-state-with-a-key)
	- [直前のレンダーの情報を保存する](https://ja.react.dev/reference/react/#storing-information-from-previous-renders)
- [トラブルシューティング](https://ja.react.dev/reference/react/#troubleshooting)
	- [state を更新したのに古い値がログに表示される](https://ja.react.dev/reference/react/#ive-updated-the-state-but-logging-gives-me-the-old-value)
	- [state を更新したのに画面が更新されない](https://ja.react.dev/reference/react/#ive-updated-the-state-but-the-screen-doesnt-update)
	- [“Too many re-renders” というエラーが出る](https://ja.react.dev/reference/react/#im-getting-an-error-too-many-re-renders)
	- [初期化関数や更新用関数が 2 度呼ばれる](https://ja.react.dev/reference/react/#my-initializer-or-updater-function-runs-twice)
	- [関数を state にセットしようとすると、その関数が呼び出されてしまう](https://ja.react.dev/reference/react/#im-trying-to-set-state-to-a-function-but-it-gets-called-instead)

---

## リファレンス

### useState(initialState)

コンポーネントのトップレベルで `useState` を呼び出して、 [state 変数](https://ja.react.dev/learn/state-a-components-memory) を宣言します。

state 変数は慣習として、 [分割代入](https://javascript.info/destructuring-assignment) を利用して `[something, setSomething]` のように命名します。

[さらに例を見る](https://ja.react.dev/reference/react/#usage)

#### 引数

- `initialState`: state の初期値です。どんな型の値でも渡すことができますが、関数を渡した場合は特別な振る舞いをします。この引数は初回レンダー後は無視されます。
	- `initialState` に関数を渡した場合、その関数は *初期化関数 (initializer function)* として扱われます。初期化関数は、純粋で、引数を取らず、何らかの型の値を返す必要があります。React はコンポーネントを初期化するときに初期化関数を呼び出し、その返り値を初期 state として保存します。 [例を見る](https://ja.react.dev/reference/react/#avoiding-recreating-the-initial-state)

#### 返り値

`useState` は以下の 2 つの値を持つ配列を返します。

1. 現在の state。初回レンダー中では、 `initialState` と同じ値になります。
2. state を別の値に更新し、再レンダーをトリガする [`set` 関数](https://ja.react.dev/reference/react/#setstate) 。

#### 注意点

- `useState` はフックであるため、 **コンポーネントのトップレベル** またはカスタムフック内でのみ呼び出すことができます。ループや条件文の中で呼び出すことはできません。これが必要な場合は、新しいコンポーネントを抽出し、state を移動させてください。
- Strict Mode では、 [純粋でない関数を見つけやすくするために](https://ja.react.dev/reference/react/#my-initializer-or-updater-function-runs-twice) 、 **初期化関数が 2 回呼び出されます** 。これは開発時のみの振る舞いであり、本番には影響しません。初期化関数が純粋であれば（そうであるべきです）、2 回呼び出されてもコードに影響はありません。2 回の呼び出しのうち 1 回の呼び出し結果は無視されます。

---

### setSomething(nextState) のように利用する set 関数

`useState` が返す `set` 関数を利用して、state を別の値に更新し、再レンダーをトリガすることができます。直接次の state を渡すか、前の state から次の state を導出する関数を渡します。

#### 引数

- `nextState`: 次に state にセットしたい値です。どんな型の値でも渡すことができますが、関数を渡した場合は特別な振る舞いをします。
	- `nextState` に関数を渡した場合、その関数は *更新用関数 (updater function)* として扱われます。更新用関数は、純粋で、処理中の state の値を唯一の引数として受け取り、次の state を返す必要があります。React は更新用関数をキューに入れ、コンポーネントを再レンダーします。次のレンダーで、React はキューに入れられたすべての更新用関数を前の state に対して適用し、次の state を導出します。 [例を見る](https://ja.react.dev/reference/react/#updating-state-based-on-the-previous-state)

#### 返り値

`set` 関数は返り値を持ちません。

#### 注意点

- `set` 関数は ***次の* レンダーのための state 変数のみを更新** します。 `set` 関数を呼び出した後に state 変数を読み取っても、呼び出し前の画面に表示されていた [古い値が返されます](https://ja.react.dev/reference/react/#ive-updated-the-state-but-logging-gives-me-the-old-value) 。
- 新しい値が現在の `state` と同一の場合、React は最適化のために、 **コンポーネントとその子コンポーネントの再レンダーをスキップ** します。state の同一性の比較は、 [`Object.is`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object/is) によって行われます。一部のケースでは、React は子コンポーネントをスキップする前にコンポーネントを呼び出す必要がありますが、あなたのコードに影響を与えることはないはずです。
- React は [state の更新をまとめて行います（バッチ処理）](https://ja.react.dev/learn/queueing-a-series-of-state-updates) 。 **すべてのイベントハンドラを実行し終え** 、 `set` 関数が呼び出された後に、画面を更新します。これにより、1 つのイベント中に複数回の再レンダーが発生することはありません。まれに、早期に画面を更新する必要がある場合（例えば DOM にアクセスする場合など）がありますが、その場合は [`flushSync`](https://ja.react.dev/reference/react-dom/flushSync) を利用できます。
- `set` 関数は常に同一のものとなるため、多くの場合エフェクトの依存配列では省略されますが、依存配列に含めてもエフェクトの再実行は起こりません。依存値を削除してもリンタがエラーを出さない場合、削除しても安全です。 [エフェクトから依存値を取り除く方法](https://ja.react.dev/learn/removing-effect-dependencies#move-dynamic-objects-and-functions-inside-your-effect) を参照してください。
- レンダー中に `set` 関数を呼び出すことは、 *現在レンダー中の* コンポーネント内からのみ許されています。その場合、React はその出力を破棄し、新しい state で再レンダーを試みます。このパターンが必要になることはほとんどありませんが、 **前回のレンダーからの情報を保存** するために使用できます。 [例を見る](https://ja.react.dev/reference/react/#storing-information-from-previous-renders)
- Strict Mode では、 [純粋でない関数を見つけやすくするために](https://ja.react.dev/reference/react/#my-initializer-or-updater-function-runs-twice) **更新用関数が 2 回呼び出されます** 。これは開発時のみの振る舞いであり、本番には影響しません。更新用関数が純粋であれば（そうであるべきです）、2 回呼び出されてもコードに影響はありません。2 回の呼び出しのうち 1 回の呼び出し結果は無視されます。

---

## 使用法

### state をコンポーネントに追加する

コンポーネントのトップレベルで `useState` を呼び出し、1 つ以上の [state 変数](https://ja.react.dev/learn/state-a-components-memory) を宣言します。

state 変数は慣習として、 [分割代入](https://javascript.info/destructuring-assignment) を利用して `[something, setSomething]` のように命名します。

`useState` は、以下の 2 つの値を持つ配列を返します。

1. この state 変数の 現在の値 。最初は、 初期 state に設定されます。
2. インタラクションに応じて、state を他の値に変更するための `set` 関数 。

スクリーン上の表示を更新するには、次の state を引数として `set` 関数を呼び出します。

React は次の state を保存したあと、新しい値でコンポーネントを再レンダーし、UI を更新します。

#### useState の基本的な使用例

#### 例 1/4: カウンタ (number)

この例では、 `count` state 変数が数値 (number) を保持しています。ボタンをクリックすることで、数値が増加します。

---

### 直前の state に応じて更新する

`age` が `42` である場合を考えましょう。このハンドラは、 `setAge(age + 1)` を 3 回呼び出します。

しかし、1 回クリックしたあと、 `age` は `45` ではなく `43` になります！ これは、 `set` 関数を呼び出しても、既に実行されているコードの `age` state 変数を [更新するわけではない](https://ja.react.dev/learn/state-as-a-snapshot) ためです。そのため、 `setAge(age + 1)` の呼び出しはすべて `setAge(43)` になります。

この問題を解消するため、次の state の代わりに、 ***更新用関数* を `setAge` に渡す** ことができます。

ここで、 `a => a + 1` は更新用関数です。更新用関数は、 処理中の state の値 を受け取り、そこから 次の state を導出します。

React は更新用関数を [キュー](https://ja.react.dev/learn/queueing-a-series-of-state-updates) に入れます。そして、次のレンダー中に、同じ順番で更新用関数を呼び出します。

1. `a => a + 1` は処理中の state の値として `42` を受け取り、次の state として `43` を返します。
2. `a => a + 1` は処理中の state の値として `43` を受け取り、次の state として `44` を返します。
3. `a => a + 1` は処理中の state の値として `44` を受け取り、次の state として `45` を返します。

キューにはこれ以上の更新用関数はないので、React は最終的に `45` を現在の state として保存します。

慣習として、処理中の state の引数名には、state 変数名の頭文字 1 文字を利用することが一般的です（例えば、 `age` という state 変数に対して、 `a` という引数名）。しかし、 `prevAge` など、他の分かりやすい名前を使うこともできます。

開発時に [更新用関数が 2 回呼び出される](https://ja.react.dev/reference/react/#my-initializer-or-updater-function-runs-twice) ことがあります。これは、更新用関数が [純粋](https://ja.react.dev/learn/keeping-components-pure) であることを確認するためです。

##### さらに深く知る

#### 常に更新用関数を利用すべきか

新しくセットする値が直前の state から導出される場合、常に `setAge(a => a + 1)` という書き方をすべきだという意見があります。悪いことではありませんが、必ずしも必要なわけではありません。

ほとんどのケースでは、どちらのアプローチでも違いはありません。React は、クリックなどのユーザの意図的なアクションに対して、 `age` state 変数の更新が次のクリックの前に発生することを保証しています。すなわち、イベントハンドラの開始時に、クリックハンドラが「古い」 `age` を参照してしまうことはありません。

一方で、同じイベント内で複数回の更新を行う場合、更新用関数が役に立ちます。また、state 変数自身を参照することが難しいケースにも有用です（再レンダーの発生を最適化する際に、このケースに遭遇することがあります）。

わずかな文法の冗長性よりも一貫性を優先するのであれば、state が直前の state から導出される場合には、常に更新用関数を書くようにすることは合理的です。もし、state が、他の state 変数の直前の値から導出される場合は、それらを 1 つのオブジェクトにまとめて [リデューサ (reducer) を利用する](https://ja.react.dev/learn/extracting-state-logic-into-a-reducer) ことを検討してください。

#### 更新用関数を渡す場合と次の state を直接渡す場合の違い

#### 例 1/2: 更新用関数を渡す

この例では更新用関数を渡しているため、“+3” ボタンは想定通りに動きます。

---

### オブジェクトや配列の state を更新する

state にオブジェクトや配列をセットすることができます。ただし React では、state は読み取り専用として扱う必要があります。そのため、state を更新する場合は、 **既存のオブジェクトを直接 *書き換える (mutate)* のではなく、 *置き換える (replace)* 必要があります** 。例えば、state として `form` オブジェクトを保持している場合、以下のように書き換えを行ってはいけません。

代わりに、新しいオブジェクトを作成してオブジェクト全体を置き換えてください。

詳しくは、 [state 内のオブジェクトの更新](https://ja.react.dev/learn/updating-objects-in-state) や、 [state 内の配列の更新](https://ja.react.dev/learn/updating-arrays-in-state) を参照してください。

#### オブジェクトや配列を state にする例

#### 例 1/4: フォーム（オブジェクト）

この例では、 `form` state 変数はオブジェクトを保持しています。それぞれの input 要素は change ハンドラを持っており、新しい `form` オブジェクトを引数として `setForm` を呼び出します。 `{ ...form }` のようにスプレッド構文を用いることで、state オブジェクトを（書き換えではなく）確実に置き換えることができます。

---

### 初期 state が再生成されることを防ぐ

React は一度だけ初期 state を保存し、2 回目以降のレンダーではそれを無視します。

`createInitialTodos()` は毎レンダーで呼び出されるものの、その結果は初回レンダーでのみ利用されます。これは、 `createInitialTodos()` が巨大な配列の生成やコストの高い計算を行っている場合に、無駄が多くなります。

これを解決するため、以下のように ***初期化関数* を渡す** ことができます。

関数を呼び出した結果である `createInitialTodos()` ではなく、 `createInitialTodos` という *関数それ自体* を渡していることに注意してください。 `useState` に関数が渡された場合、React は初期化時に、関数を一度だけ呼び出します。

初期化関数が [純粋](https://ja.react.dev/learn/keeping-components-pure) であることを確認するため、開発時に [初期化関数が 2 回呼び出される](https://ja.react.dev/reference/react/#my-initializer-or-updater-function-runs-twice) ことがあります。

#### 初期化関数を渡す場合と初期値を直接渡す場合の違い

#### 例 1/2: 初期化関数を渡す

この例では、初期化関数を利用しています。そのため、 `createInitialTodos` 関数は初期化時のみ実行されます。入力フィールドに文字を入力した場合などの、コンポーネントの再レンダー時には実行されません。

---

### key を利用して state をリセットする

`key` 属性は、 [リストをレンダーする場合](https://ja.react.dev/learn/rendering-lists) によく利用します。しかし、もう 1 つの使い道があります。

**コンポーネントに異なる `key` を渡すことで、コンポーネントの state をリセットすることができます** 。この例では、 `version` state 変数を `Form` に `key` として渡しています。“Reset” ボタンをクリックすると、 `version` state 変数が変化します。 `key` が変化したとき、React は `Form` コンポーネント（と、そのすべての子コンポーネント）を一から再生成するため、 `Form` の state がリセットされます。

詳しくは、 [state の保持とリセット](https://ja.react.dev/learn/preserving-and-resetting-state) を参照してください。

---

### 直前のレンダーの情報を保存する

通常、state の更新はイベントハンドラの中で行われます。しかし、レンダーに応じて state を設定したい場合があります。例えば、prop が変化したときに state 変数を変化させたい場合です。

以下に示すように、ほとんどのケースでは不要です。

- **もし必要な値が現在の props と他の state のみから導出される場合、 [冗長な state を削除してください](https://ja.react.dev/learn/choosing-the-state-structure#avoid-redundant-state)** 。もし何度も再計算されることが気になる場合は、 [`useMemo` フック](https://ja.react.dev/reference/react/useMemo) が役に立ちます。
- もしコンポーネントツリーの state 全体をリセットしたい場合、 [コンポーネントに異なる `key` を渡してください](https://ja.react.dev/reference/react/#resetting-state-with-a-key) 。
- 可能であれば、関連するすべての state をイベントハンドラの中で更新してください。

これらがどれも適用できない稀なケースでは、コンポーネントのレンダー中に `set` 関数を呼び出し、それまでにレンダーされた値に基づいて state を更新するパターンが利用できます。

以下の例では、 `CountLabel` コンポーネントは、渡された `count` プロパティを表示しています。

直近の変更で、counter の値が *増えたのか減ったのか* を表示したいとします。 `count` プロパティだけでは知ることができないため、前回の値を保持し続ける必要があります。前回の値を保持するために、 `prevCount` state 変数を追加します。さらに、 `trend` state 変数を追加し、count が増えたのか減ったのかを保持します。 `prevCount` と `count` を比較し、もしこれらが一致しない場合に、 `prevCount` と `trend` を更新します。これで、現在の count プロパティと、 *前回のレンダーからどのように変化したのか* の両方を表示することができます。

レンダー中に `set` 関数を呼び出す場合は、 `prevCount !== count` のような条件文の中でなければならず、その中には `setPrevCount(count)` のような呼び出しが書かれなければならないことに注意してください。さもないと、再レンダーのループに陥り、コンポーネントがクラッシュします。また、例のように、 *現在レンダーしている* コンポーネントの state のみ更新することができます。レンダー中に *別の* コンポーネントの `set` 関数を呼び出すとエラーになります。最後に、 `set` 関数の呼び出しは、 [書き換えなしで state を更新](https://ja.react.dev/reference/react/#updating-objects-and-arrays-in-state) する必要があります。これは、 [純関数](https://ja.react.dev/learn/keeping-components-pure) の他のルールを破ることができないことを意味します。

このパターンは理解するのが難しいため、通常は避けるべきです。しかし、エフェクト内で state を更新するよりは良い方法です。レンダー中に `set` 関数を呼び出すと、コンポーネントが `return` 文で終了した直後、子コンポーネントをレンダーする前に再レンダーが行われます。このため、子コンポーネントが 2 回レンダーされずに済みます。コンポーネント関数の残りの部分は引き続き実行されます（結果は破棄されますが）。もし、 `set` 関数の呼び出しを含む条件分岐が、すべてのフックの呼び出しより下にある場合、早期 `return;` を追加して、再レンダーを早めることができます。

---

## トラブルシューティング

### state を更新したのに古い値がログに表示される

`set` 関数の呼び出しは、実行中のコードの state を変化 **させません** 。

これは、 [state がスナップショットのように振る舞う](https://ja.react.dev/learn/state-as-a-snapshot) ためです。state の更新は、新しい state の値での再レンダーをリクエストします。すでに実行中のイベントハンドラ内の `count` という JavaScript 変数には影響を与えません。

次の state が必要な場合は、 `set` 関数に渡す前に一度変数に保存することができます。

---

### state を更新したのに画面が更新されない

React では、 **更新の前後で state の値が変化しない場合、その変更は無視されます** 。state の値の変化は、 [`Object.is`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object/is) によって判断されます。この現象は、state のオブジェクトや配列を直接書き換えた場合によく起こります。

既存の `obj` オブジェクトを書き換えて、 `setObj` に戻したため、この更新は無視されます。修正するには、state のオブジェクトや配列を [*書き換える* のではなく、 *置き換える*](https://ja.react.dev/reference/react/#updating-objects-and-arrays-in-state) 必要があります。

---

### “Too many re-renders” というエラーが出る

`Too many re-renders. React limits the number of renders to prevent an infinite loop.` というエラーが出ることがあります。これは通常、 *レンダー中に* 無条件に `set` 関数を呼び出しているため、コンポーネントがループに入っていることを意味します。レンダー、 `set` 関数の呼び出し（レンダーを引き起こす）、レンダー、 `set` 関数の呼び出し（レンダーを引き起こす）、というように続きます。大抵の場合、これはイベントハンドラの指定を間違ったことによるものです。

このエラーの原因がわからない場合は、コンソールのエラーの横にある矢印をクリックして、JavaScript スタックを調べ、エラーの原因となる `set` 関数の呼び出しを特定してください。

---

### 初期化関数や更新用関数が 2 度呼ばれる

[Strict Mode](https://ja.react.dev/reference/react/StrictMode) では、いくつかの関数が、本来 1 回のところを 2 回呼び出されることがあります。

これは予想される動作であり、あなたのコードを壊すものではありません。

これは **開発時のみ** の挙動で、 [コンポーネントを純粋に保つ](https://ja.react.dev/learn/keeping-components-pure) ために役立ちます。React は、呼び出し結果の 1 つを利用し、もう 1 つを無視します。コンポーネント、初期化関数、更新用関数が純粋であれば、この挙動があなたのロジックに影響を与えることはありません。ただし、誤って純粋でない関数を指定した場合は、これにより間違いに気付くことができるでしょう。

例えば以下の更新用関数は、state の配列を書き換えるため純粋ではありません。

React は更新用関数を 2 回呼び出すため、todo が 2 つ追加されてしまい、間違いに気付くことができます。この例では、配列を [書き換えるのではなく、置き換える](https://ja.react.dev/reference/react/#updating-objects-and-arrays-in-state) ことで間違いを修正できます。

更新用関数が純粋になったため、複数回呼び出されても動作に影響しません。これが、2 回呼び出されることで間違いに気付くことができる理由です。 **コンポーネント、初期化関数、更新用関数のみが純粋である必要があります** 。イベントハンドラは、純粋である必要がないため、2 回呼び出されることはありません。

詳しくは、 [コンポーネントを純粋に保つ](https://ja.react.dev/learn/keeping-components-pure) を参照してください。

---

### 関数を state にセットしようとすると、その関数が呼び出されてしまう

このような形で関数を state に設定することはできません。

関数を渡すと、React は `someFunction` を [初期化関数](https://ja.react.dev/reference/react/#avoiding-recreating-the-initial-state) 、 `someOtherFunction` を [更新用関数](https://ja.react.dev/reference/react/#updating-state-based-on-the-previous-state) として扱います。そのため、それらを呼び出し、その結果を保存しようとします。関数を実行するのではなく *保存* するには、どちらの場合も `() =>` を前に付ける必要があります。こうすると、React は関数自体を保存します。[Previous useRef](https://ja.react.dev/reference/react/useRef)

[

Next useSyncExternalStore

](https://ja.react.dev/reference/react/useSyncExternalStore)

useState – React