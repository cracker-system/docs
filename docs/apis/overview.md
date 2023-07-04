---
sidebar_position: 1
---

# Cracker API概要
Crackerではデータベースとフロントエンドとの接続にREST APIを用いています。  
REST APIを使用することでデータベースの各種操作が行なえます。

## APIの共通仕様
### プロトコル
HTTPS
### メディアタイプ
application/json
### 文字コード
UTF-8
### 認証
APIトークン認証を行います。  
HTTPヘッダーの「Auth-Api-Token」に生成されたAPIトークンを設定してください。
### リクエストヘッダー
REST APIをリクエストする場合、以下のリクエストヘッダーが共通で必要です。

|Header Name|Description|
|----|----|
|Auth-Api-Token|APIトークン|

### エラーレスポンス
APIの使用で正常に動作が行われない場合、以下のエラー応答情報を返却します。

|Property name|Type|Description|
|----|----|----|
|code|文字列|エラーコード|
|message|文字列|エラーメッセージ|

例)
```
{
  "code" : "500" ,
  "messages" : [ "エラーメッセージ" ]
}
```
## リソース一覧
提供するREST APIの一覧

|Method|Endpoint|Description|
|----|----|----|
|GET|/users|ユーザーIDの一覧を取得します|
|POST|/users|新規ユーザーの登録をします|
|DELETE|/users|既存ユーザーの削除をします|
|GET|/guests|ゲストIDの一覧を取得します|
|POST|/guests|新規ゲストの登録をします|
|PUT|/guests|既存ゲストの情報を更新します|
|DELETE|/guests|既存ゲストの削除をします|
|GET|/exhibits|展示IDの一覧を取得します|
|POST|/exhibits|新規展示の登録をします|
|PUT|/exhibits|既存展示の情報を更新します|
|DELETE|/exhibits|既存展示の削除をします|
|GET|/activities|アクティビティIDの一覧を取得します|
|POST|/activities|新規アクティビティの登録をします|
|GET|/invitations|招待コードの一覧を取得します|
|POST|/invitations|新規招待コードを登録します|
|DELETE|/invitations|既存招待コードを削除します|
