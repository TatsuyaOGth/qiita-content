---
title: Macでバッチ（command）ファイルを作る方法
tags:
  - Mac
  - command
  - Terminal
private: false
updated_at: '2014-05-25T20:31:35+09:00'
id: f15bfa9aeb68d8ecfc67
organization_url_name: null
slide: false
ignorePublish: false
---

ときどき必要だけどいつも忘れちゃうのでメモ。
Macではシェルスクリプト作ってターミナルから実行するという手がありますが、手間がかかるのでダブルクリックで実行できるようにしたい。

そんなときは普通にシェルスクリプトを作成して「.command」という拡張子に変えてあげればできます。

```shell
mv xxx.sh xxx.command
```

でもこれだけだと実行権限がないのでアクセス権を変更します.

```shell
chmod u+x xxx.command
``` 

これでFinderからダブルクリックするだけで実行されます。

##補足

###カレントディレクトリをファイルのある場所にする方法
.commandファイルを実行したときはカレントディレクトリがrootになってるので、以下のおまじないを入れてあげると、そのファイルがある場所がカレントディレクトリになります.

```shell
cd `dirname $0`
```

###実行を途中で止める方法（Enterキー入力まち状態にする）

これとかでいけます. （ a はなんでも可）

```shell
read a
```
