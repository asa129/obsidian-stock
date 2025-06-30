
https://ja.react.dev/learn/manipulating-the-dom-with-refs#example-scrolling-to-an-element

```

DOMの最初に
定義
const cardListRef = useRef<HTMLDivElement>(null);

操作後の最後に
const handleSearch = () => {

  // 検索処理

  // ...

  // スクロール

  cardListRef.current?.scrollIntoView({ behavior: "smooth" });
};

// JSX
return (

  <>

    {/* 検索フォーム */}

    <button onClick={handleSearch}>検索</button>

    {/* カード一覧 */}

    <div ref={cardListRef}>

      {/* カードたち */}

    </div>

  </>

);
```