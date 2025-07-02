
ルーティング

index() ホームディレクトリ
route(”パス”, ファイル)ルーティング

layout("パス", レイアウトのパス)

<Outlet />でできる
layout元に設定する

prefixでURLを作れるよ
```
...prefix("v1", [routes("ping", "routes/ping.tsx")])
```
v1/ping → ping.tsxをレンダリング

=  route("v1/ping", "routes/ping.tsx")

{params}: Route.ClientLoaderArgs
/aaaa/user/1 の1をとりたいときに使える

Route.ComponentProps
これだけで取得できる



#Remix #React #Routing　#React-router