---
title: "概要"
source: "https://docs.anthropic.com/ja/api/overview#type-script"
author:
  - "[[Anthropic]]"
published:
created: 2025-06-20
description:
tags:
  - "clippings"
---
## APIへのアクセス

APIは当社のウェブ [コンソール](https://console.anthropic.com/) を通じて利用可能です。 [ワークベンチ](https://console.anthropic.com/workbench/3b57d80a-99f2-4760-8316-d3bb14fbfb1e) を使用してブラウザでAPIを試し、 [アカウント設定](https://console.anthropic.com/account/keys) でAPIキーを生成できます。 [ワークスペース](https://console.anthropic.com/settings/workspaces) を使用してAPIキーを分割し、ユースケースごとに [支出を管理](https://docs.anthropic.com/ja/api/rate-limits) できます。

## 認証

Anthropic APIへのすべてのリクエストには、APIキーを含む `x-api-key` ヘッダーを含める必要があります。クライアントSDKを使用している場合は、クライアントを構築する際にAPIを設定し、SDKがリクエストごとにヘッダーを代わりに送信します。APIと直接統合する場合は、このヘッダーを自分で送信する必要があります。

## コンテンツタイプ

Anthropic APIは常にリクエスト本文でJSONを受け入れ、レスポンス本文でJSONを返します。リクエストでは `content-type: application/json` ヘッダーを送信する必要があります。クライアントSDKを使用している場合、これは自動的に処理されます。

## レスポンスヘッダー

Anthropic APIはすべてのレスポンスに以下のヘッダーを含めます：

- `request-id` ：リクエストのグローバルに一意の識別子。
- `anthropic-organization-id` ：リクエストで使用されるAPIキーに関連付けられた組織ID。

## 例

npmを通じてインストール：

TypeScript

概要 - Anthropic