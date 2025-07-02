---
title: "<aside>: 余談要素 - HTML | MDN"
source: https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/aside
author:
  - "[[MDN Web Docs]]"
published: 2025-04-30
created: 2025-07-01
description: <aside> は HTML の要素で、文書のメインコンテンツと間接的な関係しか持っていない文書の部分を表現します。サイドバーやコールアウトボックスなどを表現するためによく使われます。
tags:
  - clippings
  - "#html"
---
- [Skip to search](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/#top-nav-search-input)
- [Skip to select language](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/#languages-switcher-button)

[このページはコミュニティーの尽力で英語から翻訳されました。MDN Web Docs コミュニティーについてもっと知り、仲間になるにはこちらから。](https://developer.mozilla.org/ja/docs/MDN/Community/Contributing/Translated_content#%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%96%E3%81%AA%E3%83%AD%E3%82%B1%E3%83%BC%E3%83%AB)

**`<aside>`** は [HTML](https://developer.mozilla.org/ja/docs/Web/HTML) の要素で、文書のメインコンテンツと間接的な関係しか持っていない文書の部分を表現します。サイドバーやコールアウトボックスなどを表現するためによく使われます。

## 試してみましょう

```html
<p>
  イモリは、幼体も成体も短い足と尾を持つ、トカゲのような外観を持つ両生類のグループです。
</p>

<aside>
  <p>サメハダイモリは、致命的な神経毒で身を守ります。</p>
</aside>

<p>
  太平洋岸北西部の温帯雨林には、エンサティナ、ノースウェスタンサラマンダー、サメハダイモリなど、数種類のイモリが生息しています。ほとんどのイモリは夜行性で、昆虫やミミズ、その他の小動物を餌としています。
</p>
```

```html
aside {
  width: 40%;
  padding-left: 0.5rem;
  margin-left: 0.5rem;
  float: right;
  box-shadow: inset 5px 0 5px -5px #29627e;
  font-style: italic;
  color: #29627e;
}

aside > p {
  margin: 0.5rem;
}
```

## 属性

この要素には [グローバル属性](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Global_attributes) のみがあります。

## 使用上の注意

- 文章中の括弧書きについては、文章の主要な流れに属するものであるといえますので、これをタグ付けするために `<aside>` 要素を使用しないでください。

## 例

### <aside> の使用

この例は `<aside>` を使用して記事の中のある段落をマークアップします。この段落は記事の主要な内容と間接的な関係しかありません。

```html
<article>
  <p>
    ディズニー映画「<cite>リトル・マーメイド</cite>」は、 1989 年に最初に劇場公開されました。
  </p>
  <aside>
    <p>この映画は、公開当初の興行収入は 8,700 万ドルに達しました。</p>
  </aside>
  <p>この映画の詳細情報…</p>
</article>
```

#### 結果

## 仕様書

| Specification |
| --- |
| [HTML   \# the-aside-element](https://html.spec.whatwg.org/multipage/sections.html#the-aside-element) |

## ブラウザーの互換性

[![GitLab](https://developer.mozilla.org/pimg/aHR0cHM6Ly9zdGF0aWM0LmJ1eXNlbGxhZHMubmV0L3V1LzIvMTYyMTgwLzE3NDA1MjE5NTMtMTQ1NngxODBfQV8zXy5wbmc%3D.rfCNnwtuwRy46G5kArFAK94O%2Ffwrsk84UU8qvTRwoYU%3D)](https://developer.mozilla.org/pong/click?code=aHR0cHM6Ly9zcnYuYnV5c2VsbGFkcy5jb20vYWRzL2NsaWNrL3gvR1RORDQyN01DNjdJNks3TkM2N0xZS1FVQ1dZSUVLN0VDWVlENFozSkNBQkk0MjdMQ1lTSUMySktGVEJES0szSkNXQUQ0SzdNQ1RTRDQ1UVlDWUJEVjUzS0M2U0lQS1FJQ0FCREVLM0VISk5DTFNJWg%3D%3D.XaLo6Algc32ybr9OfU2lDwojUwtGTD70We7Rg2dPFuI%3D&version=2) [Ad](https://developer.mozilla.org/en-US/advertising)