---
title: "全プロジェクトで重宝されるイケてるREADMEを作成しよう！"
source: "https://qiita.com/shun198/items/c983c713452c041ef787"
author:
  - "[[shun198]]"
published: 2023-07-02
created: 2025-06-25
description: "READMEとは READMEはアプリケーションの 概要 環境構築手順 など、プロジェクトに必要な情報を一通り記載しているファイルです 今回はGitHubなどで記載されているわかりやすいREADMEの書き方について解説していきます READMEを書く目的とは プロジ..."
tags:
  - "clippings"
---
![](https://relay-dsp.ad-m.asia/dmp/sync/bizmatrix?pid=c3ed207b574cf11376&d=x18o8hduaj&uid=3993509)

## READMEとは

READMEはアプリケーションの

- 概要
- 環境構築手順

など、プロジェクトに必要な情報を一通り記載しているファイルです  
今回はGitHubなどで記載されているわかりやすいREADMEの書き方について解説していきます

## READMEを書く目的とは

プロジェクト内に新しいメンバーが入った時にプロジェクトの概要や必要なドキュメントのリンクをREADMEを書くことでプロジェクトへの理解が容易になる上に不要なコミュニケーションコストの削減につながります  
また、環境構築の手順も記載することで個々人の技術レベルに依存せずに誰でも開発構築ができるようになるのでぜひ書いてほしいですね

## READMEに書いておきたい項目

あくまで一例ですが私が普段READMEに記載しているのは以下の通りです

- 使用している主な技術
- プロジェクトの概要
- 必要な環境変数やコマンド一覧
- ディレクトリ構成
- 開発環境の構築方法
- トラブルシューティング

では、一つずつ見ていきましょう

### 使用している主な技術

どんな技術を使っているかはディレクトリ構成やファイルなどでなんとなくわかりますが  
プロジェクトで使用している技術に疎い人が見ると見づらいのでは？と感じたので私はSheildを冒頭につけています

[![スクリーンショット 2023-07-02 18.06.52.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/625980/74dbd4b6-b540-6b5c-fa19-44eb091dde49.png)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F625980%2F74dbd4b6-b540-6b5c-fa19-44eb091dde49.png?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=e4097898cc3a05626a604d11d28ce101)

#### Sheidとは

SheildはREADMEなどのマークダウンに貼ることができるいわゆるバッチみたいなものです

詳細は以下のサイトを参照してくささい

img srcタグを使って作成する。以下の構成になっています

```html
<img src="https://img.shields.io/badge/-{言語、フレームワーク名など}-{シールドのカラーコード}.svg?logo=next.js&style={バッチのスタイル}&logoColor={ロゴのカラーコード}">
```

プロジェクトによって使用する技術は違うので下記から選んで貼ってみてください

#### フロントエンドフレームワーク

[![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Node.js-000000.svg%3Flogo%3Dnode.js%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=58a7faca7c79608cc0f2f1dd1e56645c)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Node.js-000000.svg%3Flogo%3Dnode.js%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=58a7faca7c79608cc0f2f1dd1e56645c) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Next.js-000000.svg%3Flogo%3Dnext.js%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=35cd13428275432d41a74d49b1f3af9d)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Next.js-000000.svg%3Flogo%3Dnext.js%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=35cd13428275432d41a74d49b1f3af9d) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-TailwindCSS-000000.svg%3Flogo%3Dtailwindcss%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=c5f403335d5eaf1c0b1b5198a6719402)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-TailwindCSS-000000.svg%3Flogo%3Dtailwindcss%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=c5f403335d5eaf1c0b1b5198a6719402) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-React-20232A%3Fstyle%3Dfor-the-badge%26logo%3Dreact%26logoColor%3D61DAFB?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=a4f4b17fec4b64ce16a3cd0eeb3e7bff)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-React-20232A%3Fstyle%3Dfor-the-badge%26logo%3Dreact%26logoColor%3D61DAFB?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=a4f4b17fec4b64ce16a3cd0eeb3e7bff) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-React%2520Native-000000.svg%3Flogo%3Dreact%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=a677159be2985fc39c82a7d7b9348ace)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-React%2520Native-000000.svg%3Flogo%3Dreact%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=a677159be2985fc39c82a7d7b9348ace) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Expo-000000.svg%3Flogo%3Dexpo%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=5d1e7472b19cbdec64248085b5fa46f6)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Expo-000000.svg%3Flogo%3Dexpo%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=5d1e7472b19cbdec64248085b5fa46f6)

#### フロントエンド言語

[![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-TypeScript-000000.svg%3Fstyle%3Dfor-the-badge%26logo%3Dtypescript%26logoColor%3D61DAFB?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=3d6b6ebf764fd6121cd442338fb6a4ec)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-TypeScript-000000.svg%3Fstyle%3Dfor-the-badge%26logo%3Dtypescript%26logoColor%3D61DAFB?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=3d6b6ebf764fd6121cd442338fb6a4ec) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-JavaScript-000000.svg%3Fstyle%3Dfor-the-badge%26logo%3DJavaScript%26logoColor%3DF7DF1E?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=7a90e0e66d0f873de7b7fe04977968ba)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-JavaScript-000000.svg%3Fstyle%3Dfor-the-badge%26logo%3DJavaScript%26logoColor%3DF7DF1E?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=7a90e0e66d0f873de7b7fe04977968ba)

#### バックエンドフレームワーク

[![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Django-092E20.svg%3Flogo%3Ddjango%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=8e893eb1e18849898af16fa81c0b9642)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Django-092E20.svg%3Flogo%3Ddjango%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=8e893eb1e18849898af16fa81c0b9642) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-fastapi-009688.svg%3Flogo%3DFastAPI%26style%3Dfor-the-badge%26logoColor%3Dblack?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=8dd66665fcc23dfcdeb481e9f1e62dc4)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-fastapi-009688.svg%3Flogo%3DFastAPI%26style%3Dfor-the-badge%26logoColor%3Dblack?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=8dd66665fcc23dfcdeb481e9f1e62dc4) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Rails-CC0000.svg%3Fstyle%3Dfor-the-badge%26logo%3Drails%26logoColor%3Dwhite?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=364c32f5399c14802bb1f93ef6813687)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Rails-CC0000.svg%3Fstyle%3Dfor-the-badge%26logo%3Drails%26logoColor%3Dwhite?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=364c32f5399c14802bb1f93ef6813687) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Cakephp-F33C43.svg%3Flogo%3Dcakephp%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=5cc6c3b1d8341d3bcf174601bf594ae5)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Cakephp-F33C43.svg%3Flogo%3Dcakephp%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=5cc6c3b1d8341d3bcf174601bf594ae5)

#### バックエンド言語

[![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Python-F2C63C.svg%3Flogo%3Dpython%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=c17144ccc12f9c19e9dbba2eec5c7980)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Python-F2C63C.svg%3Flogo%3Dpython%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=c17144ccc12f9c19e9dbba2eec5c7980) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Ruby-CC342D.svg%3Flogo%3Druby%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=6d2cbe3e62777f5b914c7e609d60ddb8)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Ruby-CC342D.svg%3Flogo%3Druby%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=6d2cbe3e62777f5b914c7e609d60ddb8) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Rust-000000.svg%3Flogo%3Drust%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=3b95050df3b1804ebaa801fb8bff0d65)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Rust-000000.svg%3Flogo%3Drust%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=3b95050df3b1804ebaa801fb8bff0d65) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Go-76E1FE.svg%3Flogo%3Dgo%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=3d2db7f8dc7415bae9d36c63a06ffba0)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Go-76E1FE.svg%3Flogo%3Dgo%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=3d2db7f8dc7415bae9d36c63a06ffba0) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Php-777BB4.svg%3Flogo%3Dphp%26style%3Dfor-the-badge%26logoColor%3Dwhite?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=5d58a113c666929bd6e51d1dd4efb231)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Php-777BB4.svg%3Flogo%3Dphp%26style%3Dfor-the-badge%26logoColor%3Dwhite?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=5d58a113c666929bd6e51d1dd4efb231) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Java-007396.svg%3Flogo%3Djava%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=a90efdef766a4cd1c5b6a824007e2f68)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Java-007396.svg%3Flogo%3Djava%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=a90efdef766a4cd1c5b6a824007e2f68)

#### ミドルウェア

[![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Nginx-269539.svg%3Flogo%3Dnginx%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=3fd95b04ba4987dde181146b5285d5c9)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Nginx-269539.svg%3Flogo%3Dnginx%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=3fd95b04ba4987dde181146b5285d5c9) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Postgresql-336791.svg%3Flogo%3Dpostgresql%26style%3Dfor-the-badge%26logoColor%3Dwhite?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=e90f8a887993df744cb9ccf61231f07c)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Postgresql-336791.svg%3Flogo%3Dpostgresql%26style%3Dfor-the-badge%26logoColor%3Dwhite?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=e90f8a887993df744cb9ccf61231f07c) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-MySQL-4479A1.svg%3Flogo%3Dmysql%26style%3Dfor-the-badge%26logoColor%3Dwhite?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=4d494b1e1970d495620c420e66467c57)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-MySQL-4479A1.svg%3Flogo%3Dmysql%26style%3Dfor-the-badge%26logoColor%3Dwhite?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=4d494b1e1970d495620c420e66467c57) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Redis-DC382D.svg%3Flogo%3Dredis%26style%3Dfor-the-badge%26logoColor%3Dwhite?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=92c8b6e84a22bdc0dd0560e7b4eebf9e)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Redis-DC382D.svg%3Flogo%3Dredis%26style%3Dfor-the-badge%26logoColor%3Dwhite?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=92c8b6e84a22bdc0dd0560e7b4eebf9e) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Gunicorn-199848.svg%3Flogo%3Dgunicorn%26style%3Dfor-the-badge%26logoColor%3Dwhite?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=740e8bb7eb7d677627ee3f56c708cbe3)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Gunicorn-199848.svg%3Flogo%3Dgunicorn%26style%3Dfor-the-badge%26logoColor%3Dwhite?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=740e8bb7eb7d677627ee3f56c708cbe3) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Mongodb-47A248.svg%3Flogo%3Dmongodb%26style%3Dfor-the-badge%26logoColor%3Dwhite?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=9512a72758dcdc5ae0c1fff5ef5426c4)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Mongodb-47A248.svg%3Flogo%3Dmongodb%26style%3Dfor-the-badge%26logoColor%3Dwhite?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=9512a72758dcdc5ae0c1fff5ef5426c4)

#### インフラ

[![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Docker-1488C6.svg%3Flogo%3Ddocker%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=14a6094ef3229a37e7d5126c6cb6ac7a)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Docker-1488C6.svg%3Flogo%3Ddocker%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=14a6094ef3229a37e7d5126c6cb6ac7a) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-githubactions-FFFFFF.svg%3Flogo%3Dgithub-actions%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=2476e16acd4c54fb4bf78852e6390101)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-githubactions-FFFFFF.svg%3Flogo%3Dgithub-actions%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=2476e16acd4c54fb4bf78852e6390101) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Amazon%2520aws-232F3E.svg%3Flogo%3Damazon-aws%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=43f20d79eca53cf2985eed6a2169447c)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Amazon%2520aws-232F3E.svg%3Flogo%3Damazon-aws%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=43f20d79eca53cf2985eed6a2169447c) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-AWS%2520lambda-232F3E.svg%3Flogo%3Daws-lambda%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=83d4ef9f8f1d3e8d31af3c5e282b627a)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-AWS%2520lambda-232F3E.svg%3Flogo%3Daws-lambda%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=83d4ef9f8f1d3e8d31af3c5e282b627a) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-AWS%2520fargate-232F3E.svg%3Flogo%3Daws-fargate%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=a2a1fb4b8fcc05e1bed888c7564866a7)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-AWS%2520fargate-232F3E.svg%3Flogo%3Daws-fargate%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=a2a1fb4b8fcc05e1bed888c7564866a7) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Amazon%2520ec2-232F3E.svg%3Flogo%3Damazon-ec2%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=15e6cf809a433f143c770a5f6227ec61)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Amazon%2520ec2-232F3E.svg%3Flogo%3Damazon-ec2%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=15e6cf809a433f143c770a5f6227ec61) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-terraform-20232A%3Fstyle%3Dfor-the-badge%26logo%3Dterraform%26logoColor%3D844EBA?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=7c06c9eb64797f5d40199d3c8a6fdbf8)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-terraform-20232A%3Fstyle%3Dfor-the-badge%26logo%3Dterraform%26logoColor%3D844EBA?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=7c06c9eb64797f5d40199d3c8a6fdbf8) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-vagrant-20232A%3Fstyle%3Dfor-the-badge%26logo%3Dvagrant%26logoColor%3D0750C5?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=0d9fc3066bdb003c69309b351851a5b0)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-vagrant-20232A%3Fstyle%3Dfor-the-badge%26logo%3Dvagrant%26logoColor%3D0750C5?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=0d9fc3066bdb003c69309b351851a5b0)

#### その他

[![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Ansible-000000.svg%3Flogo%3Dansible%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=a634c7df84b9ad46d67503bceafa112d)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Ansible-000000.svg%3Flogo%3Dansible%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=a634c7df84b9ad46d67503bceafa112d) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Xcode-1575F9.svg%3Flogo%3Dxcode%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=c9e6b97aa6072cf661720dc9678422ad)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Xcode-1575F9.svg%3Flogo%3Dxcode%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=c9e6b97aa6072cf661720dc9678422ad) [![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Android%2520Studio-A4C639.svg%3Flogo%3Dandroid%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=42ed59025996b14fb153b5d6b138dbbd)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fimg.shields.io%2Fbadge%2F-Android%2520Studio-A4C639.svg%3Flogo%3Dandroid%26style%3Dfor-the-badge?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=42ed59025996b14fb153b5d6b138dbbd)

こちらに記載していないバッチは以下のサイトから作成できます

## プロジェクトの概要

こちらに

- プロジェクト名
- プロジェクトの概要
- プロジェクトの詳細が記載された資料のリンク

などを記載します  
READMEはあくまでプロジェクトの概要と開発環境の構築方法を知るための資料の位置付けなので  
プロジェクトの詳細を知りたい場合はBacklogなどのプロジェクト管理ツールを参照するように運用しています

### 必要な環境変数やコマンド一覧

環境変数やコマンド一覧は一部の人しか知らずブラックボックス化しやすいため一覧を記載します

#### 環境変数

以下が私がよく使うDjangoのプロジェクトで使用する環境変数の記載例です  
自身が使用するフレームワークに応じて自由に記載してください

| 変数名 | 役割 | デフォルト値 | DEV 環境での値 |
| --- | --- | --- | --- |
| MYSQL\_ROOT\_PASSWORD | MySQL のルートパスワード（Docker で使用） | root |  |
| MYSQL\_DATABASE | MySQL のデータベース名（Docker で使用） | django-db |  |
| MYSQL\_USER | MySQL のユーザ名（Docker で使用） | django |  |
| MYSQL\_PASSWORD | MySQL のパスワード（Docker で使用） | django |  |
| MYSQL\_HOST | MySQL のホスト名（Docker で使用） | db |  |
| MYSQL\_PORT | MySQL のポート番号（Docker で使用） | 3306 |  |
| SECRET\_KEY | Django のシークレットキー | secretkey | 他者に推測されないランダムな値にすること |
| ALLOWED\_HOSTS | リクエストを許可するホスト名 | localhost 127.0.0.1 \[::1\] back web | フロントのホスト名 |
| DEBUG | デバッグモードの切り替え | True | False |
| TRUSTED\_ORIGINS | CORS で許可するオリジン | [http://localhost](http://localhost/) |  |
| DJANGO\_SETTINGS\_MODULE | Django アプリケーションの設定モジュール | project.settings.local | project.settings.dev |

#### コマンド一覧

私はMakefileを使ってコマンドを実行しているので

- Makeのコマンド
- 元のコマンド
- コマンドを実行する際に起こる処理

を記載するとわかりやすいかと思います

- フレームワークやツールに慣れていないエンジニア
- Dockerを使い慣れてない新人

などが参照できるように記載すると重宝します

| Make | 実行する処理 | 元のコマンド |
| --- | --- | --- |
| make prepare | node\_modules のインストール、イメージのビルド、コンテナの起動を順に行う | docker-compose run --rm front npm install   docker-compose up -d --build |
| make up | コンテナの起動 | docker-compose up -d |
| make build | イメージのビルド | docker-compose build |
| make down | コンテナの停止 | docker-compose down |
| make loaddata | テストデータの投入 | docker-compose exec app poetry run python manage.py loaddata crm.json |
| make makemigrations | マイグレーションファイルの作成 | docker-compose exec app poetry run python manage.py makemigrations |
| make migrate | マイグレーションを行う | docker-compose exec app poetry run python manage.py migrate |
| make show\_urls | エンドポイントをターミナル上で一覧表示 | docker-compose exec app poetry run python manage.py show\_urls |
| make shell | テストデータの投入 | docker-compose exec app poetry run python manage.py debugsqlshell |
| make superuser | スーパーユーザの作成 | docker-compose exec app poetry run python manage.py createsuperuser |
| make test | テストを実行 | docker-compose exec app poetry run pytest |
| make test-cov | カバレッジを表示させた上でテストを実行 | docker-compose exec app poetry run pytest --cov |
| make format | black と isort を使ってコードを整形 | docker-compose exec app poetry run black.   docker-compose exec app poetry run isort. |
| make update | Poetry 内のパッケージの更新 | docker-compose exec app poetry update |
| make app | アプリケーション のコンテナへ入る | docker exec -it app bash |
| make db | データベースのコンテナへ入る | docker exec -it db bash |
| make pdoc | pdoc ドキュメントの作成 | docker-compose exec app env CI\_MAKING\_DOCS=1 poetry run pdoc -o docs application |
| make init | Terraform の初期化 | docker-compose -f infra/docker-compose.yml run --rm terraform init |
| make fmt | Terraform の設定ファイルをフォーマット | docker-compose -f infra/docker-compose.yml run --rm terraform fmt |
| make validate | Terraform の構成ファイルが正常であることを確認 | docker-compose -f infra/docker-compose.yml run --rm terraform validate |
| make show | 現在のリソースの状態を参照 | docker-compose -f infra/docker-compose.yml run --rm terraform show |
| make apply | Terraform の内容を適用 | docker-compose -f infra/docker-compose.yml run --rm terraform apply |
| make destroy | Terraform で構成されたリソースを削除 | docker-compose -f infra/docker-compose.yml run --rm terraform destroy |

### トラブルシューティング

仮に手順通りに環境構築したつもりでもできていない場合はトラブルシューティング欄を設けています  
主にDocker関連のエラーを中心にまとめています

README.md

```gcc-machine-description
### .env: no such file or directory

.env ファイルがないので環境変数の一覧を参考に作成しましょう

### docker daemon is not running

Docker Desktop が起動できていないので起動させましょう

### Ports are not available: address already in use

別のコンテナもしくはローカル上ですでに使っているポートがある可能性があります
<br>
下記記事を参考にしてください
<br>
[コンテナ起動時に Ports are not available: address already in use が出た時の対処法について](https://qiita.com/shun198/items/ab6eca4bbe4d065abb8f)

### Module not found

make build

を実行して Docker image を更新してください
```

## テンプレート例

以下が私が使用しているREADMEのテンプレートです  
上記でお話しした項目以外に例えば

- ER図
- ディレクトリ構成

なども記載していますがこの情報は欲しいな、というものがあれば適宜追加していいと思います

README.md

```gcc-machine-description
<div id="top"></div>

## 使用技術一覧

<!-- シールド一覧 -->
<!-- 該当するプロジェクトの中から任意のものを選ぶ-->
<p style="display: inline">
  <!-- フロントエンドのフレームワーク一覧 -->
  <img src="https://img.shields.io/badge/-Node.js-000000.svg?logo=node.js&style=for-the-badge">
  <img src="https://img.shields.io/badge/-Next.js-000000.svg?logo=next.js&style=for-the-badge">
  <img src="https://img.shields.io/badge/-TailwindCSS-000000.svg?logo=tailwindcss&style=for-the-badge">
  <img src="https://img.shields.io/badge/-React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB">
  <!-- バックエンドのフレームワーク一覧 -->
  <img src="https://img.shields.io/badge/-Django-092E20.svg?logo=django&style=for-the-badge">
  <!-- バックエンドの言語一覧 -->
  <img src="https://img.shields.io/badge/-Python-F2C63C.svg?logo=python&style=for-the-badge">
  <!-- ミドルウェア一覧 -->
  <img src="https://img.shields.io/badge/-Nginx-269539.svg?logo=nginx&style=for-the-badge">
  <img src="https://img.shields.io/badge/-MySQL-4479A1.svg?logo=mysql&style=for-the-badge&logoColor=white">
  <img src="https://img.shields.io/badge/-Gunicorn-199848.svg?logo=gunicorn&style=for-the-badge&logoColor=white">
  <!-- インフラ一覧 -->
  <img src="https://img.shields.io/badge/-Docker-1488C6.svg?logo=docker&style=for-the-badge">
  <img src="https://img.shields.io/badge/-githubactions-FFFFFF.svg?logo=github-actions&style=for-the-badge">
  <img src="https://img.shields.io/badge/-Amazon%20aws-232F3E.svg?logo=amazon-aws&style=for-the-badge">
  <img src="https://img.shields.io/badge/-terraform-20232A?style=for-the-badge&logo=terraform&logoColor=844EBA">
</p>

## 目次

1. [プロジェクトについて](#プロジェクトについて)
2. [環境](#環境)
3. [ディレクトリ構成](#ディレクトリ構成)
4. [開発環境構築](#開発環境構築)
5. [トラブルシューティング](#トラブルシューティング)

<!-- READMEの作成方法のドキュメントのリンク -->
<br />
<div align="right">
    <a href="READMEの作成方法のリンク"><strong>READMEの作成方法 »</strong></a>
</div>
<br />
<!-- Dockerfileのドキュメントのリンク -->
<div align="right">
    <a href="Dockerfileの詳細リンク"><strong>Dockerfileの詳細 »</strong></a>
</div>
<br />
<!-- プロジェクト名を記載 -->

## プロジェクト名

React、DRF、Terraform のテンプレートリポジトリ

<!-- プロジェクトについて -->

## プロジェクトについて

React、DRF、Terraform を勉強する際に使用できるテンプレート

<!-- プロジェクトの概要を記載 -->

  <p align="left">
    <br />
    <!-- プロジェクト詳細にBacklogのWikiのリンク -->
    <a href="Backlogのwikiリンク"><strong>プロジェクト詳細 »</strong></a>
    <br />
    <br />

<p align="right">(<a href="#top">トップへ</a>)</p>

## 環境

<!-- 言語、フレームワーク、ミドルウェア、インフラの一覧とバージョンを記載 -->

| 言語・フレームワーク  | バージョン |
| --------------------- | ---------- |
| Python                | 3.11.4     |
| Django                | 4.2.1      |
| Django Rest Framework | 3.14.0     |
| MySQL                 | 8.0        |
| Node.js               | 16.17.0    |
| React                 | 18.2.0     |
| Next.js               | 13.4.6     |
| Terraform             | 1.3.6      |

その他のパッケージのバージョンは pyproject.toml と package.json を参照してください

<p align="right">(<a href="#top">トップへ</a>)</p>

## ディレクトリ構成

<!-- Treeコマンドを使ってディレクトリ構成を記載 -->

❯ tree -a -I "node_modules|.next|.git|.pytest_cache|static" -L 2
.
├── .devcontainer
│   └── devcontainer.json
├── .env
├── .github
│   ├── action
│   ├── release-drafter.yml
│   └── workflows
├── .gitignore
├── Makefile
├── README.md
├── backend
│   ├── .vscode
│   ├── application
│   ├── docs
│   ├── manage.py
│   ├── output
│   ├── poetry.lock
│   ├── project
│   └── pyproject.toml
├── containers
│   ├── django
│   ├── front
│   ├── mysql
│   └── nginx
├── docker-compose.yml
├── frontend
│   ├── .gitignore
│   ├── README.md
│   ├── __test__
│   ├── components
│   ├── features
│   ├── next-env.d.ts
│   ├── package-lock.json
│   ├── package.json
│   ├── pages
│   ├── postcss.config.js
│   ├── public
│   ├── styles
│   ├── tailwind.config.js
│   └── tsconfig.json
└── infra
    ├── .gitignore
    ├── docker-compose.yml
    ├── main.tf
    ├── network.tf
    └── variables.tf

<p align="right">(<a href="#top">トップへ</a>)</p>

## 開発環境構築

<!-- コンテナの作成方法、パッケージのインストール方法など、開発環境構築に必要な情報を記載 -->

### コンテナの作成と起動

.env ファイルを以下の環境変数例と[環境変数の一覧](#環境変数の一覧)を元に作成

.env
MYSQL_ROOT_PASSWORD=root
MYSQL_DATABASE=django-db
MYSQL_USER=django
MYSQL_PASSWORD=django
MYSQL_HOST=db
MYSQL_PORT=3306
SECRET_KEY=django
DJANGO_SETTINGS_MODULE=project.settings.local

.env ファイルを作成後、以下のコマンドで開発環境を構築

make prepare

### 動作確認

http://127.0.0.1:8000 にアクセスできるか確認
アクセスできたら成功

### コンテナの停止

以下のコマンドでコンテナを停止することができます

make down

### 環境変数の一覧

| 変数名                 | 役割                                      | デフォルト値                       | DEV 環境での値                           |
| ---------------------- | ----------------------------------------- | ---------------------------------- | ---------------------------------------- |
| MYSQL_ROOT_PASSWORD    | MySQL のルートパスワード（Docker で使用） | root                               |                                          |
| MYSQL_DATABASE         | MySQL のデータベース名（Docker で使用）   | django-db                          |                                          |
| MYSQL_USER             | MySQL のユーザ名（Docker で使用）         | django                             |                                          |
| MYSQL_PASSWORD         | MySQL のパスワード（Docker で使用）       | django                             |                                          |
| MYSQL_HOST             | MySQL のホスト名（Docker で使用）         | db                                 |                                          |
| MYSQL_PORT             | MySQL のポート番号（Docker で使用）       | 3306                               |                                          |
| SECRET_KEY             | Django のシークレットキー                 | secretkey                          | 他者に推測されないランダムな値にすること |
| ALLOWED_HOSTS          | リクエストを許可するホスト名              | localhost 127.0.0.1 [::1] back web | フロントのホスト名                       |
| DEBUG                  | デバッグモードの切り替え                  | True                               | False                                    |
| TRUSTED_ORIGINS        | CORS で許可するオリジン                   | http://localhost                   |                                          |
| DJANGO_SETTINGS_MODULE | Django アプリケーションの設定モジュール   | project.settings.local             | project.settings.dev                     |

### コマンド一覧

| Make                | 実行する処理                                                            | 元のコマンド                                                                               |
| ------------------- | ----------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| make prepare        | node_modules のインストール、イメージのビルド、コンテナの起動を順に行う | docker-compose run --rm front npm install<br>docker-compose up -d --build                  |
| make up             | コンテナの起動                                                          | docker-compose up -d                                                                       |
| make build          | イメージのビルド                                                        | docker-compose build                                                                       |
| make down           | コンテナの停止                                                          | docker-compose down                                                                        |
| make loaddata       | テストデータの投入                                                      | docker-compose exec app poetry run python manage.py loaddata crm.json                      |
| make makemigrations | マイグレーションファイルの作成                                          | docker-compose exec app poetry run python manage.py makemigrations                         |
| make migrate        | マイグレーションを行う                                                  | docker-compose exec app poetry run python manage.py migrate                                |
| make show_urls      | エンドポイントをターミナル上で一覧表示                                  | docker-compose exec app poetry run python manage.py show_urls                              |
| make shell          | テストデータの投入                                                      | docker-compose exec app poetry run python manage.py debugsqlshell                          |
| make superuser      | スーパーユーザの作成                                                    | docker-compose exec app poetry run python manage.py createsuperuser                        |
| make test           | テストを実行                                                            | docker-compose exec app poetry run pytest                                                  |
| make test-cov       | カバレッジを表示させた上でテストを実行                                  | docker-compose exec app poetry run pytest --cov                                            |
| make format         | black と isort を使ってコードを整形                                     | docker-compose exec app poetry run black . <br> docker-compose exec app poetry run isort . |
| make update         | Poetry 内のパッケージの更新                                             | docker-compose exec app poetry update                                                      |
| make app            | アプリケーション のコンテナへ入る                                       | docker exec -it app bash                                                                   |
| make db             | データベースのコンテナへ入る                                            | docker exec -it db bash                                                                    |
| make pdoc           | pdoc ドキュメントの作成                                                 | docker-compose exec app env CI_MAKING_DOCS=1 poetry run pdoc -o docs application           |
| make init           | Terraform の初期化                                                      | docker-compose -f infra/docker-compose.yml run --rm terraform init                         |
| make fmt            | Terraform の設定ファイルをフォーマット                                  | docker-compose -f infra/docker-compose.yml run --rm terraform fmt                          |
| make validate       | Terraform の構成ファイルが正常であることを確認                          | docker-compose -f infra/docker-compose.yml run --rm terraform validate                     |
| make show           | 現在のリソースの状態を参照                                              | docker-compose -f infra/docker-compose.yml run --rm terraform show                         |
| make apply          | Terraform の内容を適用                                                  | docker-compose -f infra/docker-compose.yml run --rm terraform apply                        |
| make destroy        | Terraform で構成されたリソースを削除                                    | docker-compose -f infra/docker-compose.yml run --rm terraform destroy                      |

### リモートデバッグの方法

リモートデバッグ を使用する際は以下の url を参考に設定してください<br>
[Django のコンテナへリモートデバッグしよう！](https://qiita.com/shun198/items/9e4fcb4479385217c323)

## トラブルシューティング

### .env: no such file or directory

.env ファイルがないので環境変数の一覧を参考に作成しましょう

### docker daemon is not running

Docker Desktop が起動できていないので起動させましょう

### Ports are not available: address already in use

別のコンテナもしくはローカル上ですでに使っているポートがある可能性があります
<br>
下記記事を参考にしてください
<br>
[コンテナ起動時に Ports are not available: address already in use が出た時の対処法について](https://qiita.com/shun198/items/ab6eca4bbe4d065abb8f)

### Module not found

make build

を実行して Docker image を更新してください

<p align="right">(<a href="#top">トップへ</a>)</p>
```

## テンプレートの設定方法

テンプレートとして他プロジェクトでも使用したいREADMEがあればSettingsから `Template repository` にチェックを入れると今後新しいリポジトリを作成する際にテンプレートを元に作成できます

[![スクリーンショット 2023-07-02 20.17.02.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/625980/40974271-8de3-78f3-f810-cdef4009172c.png)](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.ap-northeast-1.amazonaws.com%2F0%2F625980%2F40974271-8de3-78f3-f810-cdef4009172c.png?ixlib=rb-4.0.0&auto=format&gif-q=60&q=75&s=5171506a863c49b3177904cce93a60fb)

## まとめ

READMEがある、ないでは新規に参画する際の障壁や負担が全然違うのとREADMEはプロジェクトの顔でもあるのでめんどくさいけど丁寧に作っていくのはすごくいいことだと考えています  
今回投稿したテンプレートが誰かの助けになれば幸いです

[0](https://qiita.com/shun198/items/#comments)

コメント一覧へ移動

[178](https://qiita.com/shun198/items/c983c713452c041ef787/likers)

150