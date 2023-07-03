---
sidebar_position: 1
---

# API共通仕様
## プロトコル
HTTPS
## メディアタイプ
application/json
## 文字コード
UTF-8
## 認証
APIトークン認証を行います。  
HTTPヘッダーの「Auth-Api-Token」に生成されたAPIトークンを設定してください。
## リクエストヘッダ
## エラーレスポンス
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
