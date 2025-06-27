
https://console.anthropic.com/settings/keys

ここで管理KEYの管理できるよ

https://docs.anthropic.com/ja/api/overview#type-script
とおりすればOK

1. **既存のキーを確認**
    - 作成済みのAPIキーの一覧が表示されます
    - キー名、作成日、最終使用日などが確認できます
    - セキュリティ上、完全なキー値は表示されません（最初の数文字のみ）

**新しいAPIキーを作成する場合：**

- 「Create Key」ボタンをクリック
- キーに名前を付けて作成
- **重要：** 作成直後に表示される完全なキーをコピーして安全に保存してください（再表示されません）
バッチ処理の場合はVITE_いらない
`VITE_`プレフィックスはブラウザ環境用です。Node.js環境（バッチ処理など）では通常の環境変数を使用

```
import "dotenv/config";

import Anthropic from "@anthropic-ai/sdk";

  

export const anthropic = new Anthropic({

  apiKey: process.env.ANTHROPIC_API_KEY, // デフォルトはprocess.env["ANTHROPIC_API_KEY"]

});
```

```
ANTHROPIC_API_KEY=your_api_key
```