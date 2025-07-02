---
title: "<nav>: ナビゲーションセクション要素 - HTML | MDN"
source: https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/nav
author:
  - "[[MDN Web Docs]]"
published: 2025-04-19
created: 2025-07-01
description: <nav> は HTML の要素で、現在の文書内の他の部分や他の文書へのナビゲーションリンクを提供するためのセクションを表します。ナビゲーションセクションの一般的な例としてメニュー、目次、索引などがあります。
tags:
  - clippings
  - html
---
- [Skip to search](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/#top-nav-search-input)
- [Skip to select language](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/#languages-switcher-button)

[このページはコミュニティーの尽力で英語から翻訳されました。MDN Web Docs コミュニティーについてもっと知り、仲間になるにはこちらから。](https://developer.mozilla.org/ja/docs/MDN/Community/Contributing/Translated_content#%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%96%E3%81%AA%E3%83%AD%E3%82%B1%E3%83%BC%E3%83%AB)

**`<nav>`** は [HTML](https://developer.mozilla.org/ja/docs/Web/HTML) の要素で、現在の文書内の他の部分や他の文書へのナビゲーションリンクを提供するためのセクションを表します。ナビゲーションセクションの一般的な例としてメニュー、目次、索引などがあります。

## 属性

この要素には [グローバル属性](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Global_attributes) のみがあります。

## 例

この例では、 `<nav>` ブロックを使用して、リンクの番号なしリスト ([`<ul>`](https://developer.mozilla.org/ja/docs/Web/HTML/Reference/Elements/ul)) を囲んでいます。適切な CSS によってサイドバー、ナビゲーションバー、あるいはドロップダウンメニューにすることができます。

`nav` 要素の意味づけはリンクを提供することです。しかし、 `nav` 要素はリストを格納する必要はなく、他の種類のコンテンツを格納することもできます。このナビゲーションブロックでは、リンクは散文で指定されています。

```html
<nav>
  <h2>Navigation</h2>
  <p>
    You are on my home page. To the north lies <a href="/blog">my blog</a>, from
    whence the sounds of battle can be heard. To the east you can see a large
    mountain, upon which many <a href="/school">school papers</a> are littered.
    Far up this mountain you can spy a little figure who appears to be me,
    desperately scribbling a <a href="/school/thesis">thesis</a>.
  </p>
  <p>
    To the west are several exits. One fun-looking exit is labeled
    <a href="https://games.example.com/">"games"</a>. Another more
    boring-looking exit is labeled <a href="https://isp.example.net/">ISP™</a>.
  </p>
  <p>
    To the south lies a dark and dank <a href="/about">contacts page</a>.
    Cobwebs cover its disused entrance, and at one point you see a rat run
    quickly out of the page.
  </p>
</nav>
```

### 結果

## 仕様書

| Specification |
| --- |
| [HTML   \# the-nav-element](https://html.spec.whatwg.org/multipage/sections.html#the-nav-element) |

## ブラウザーの互換性

[![GitLab](https://developer.mozilla.org/pimg/aHR0cHM6Ly9zdGF0aWM0LmJ1eXNlbGxhZHMubmV0L3V1LzIvMTYyMTgwLzE3NDA1MjE5NTMtMTQ1NngxODBfQV8zXy5wbmc%3D.rfCNnwtuwRy46G5kArFAK94O%2Ffwrsk84UU8qvTRwoYU%3D)](https://developer.mozilla.org/pong/click?code=aHR0cHM6Ly9zcnYuYnV5c2VsbGFkcy5jb20vYWRzL2NsaWNrL3gvR1RORDQyN01DNjdJNks3TkM2N0xZS1FVQ1dZSUVLN0VDWVlENFozSkNBQkk0MjdMQ1lTSUMySktGVEJES0szSkNXQUQ0SzdNQ1RTRDQ1UVlDS0FENEtRS0M2U0lQS1FJQ0FCREVLM0VISk5DTFNJWg%3D%3D.qox4Lqzndfl59TJrKDYD3zqteggKTlf0UjJK94ZlfpE%3D&version=2) [Ad](https://developer.mozilla.org/en-US/advertising)