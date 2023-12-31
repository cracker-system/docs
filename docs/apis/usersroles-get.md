---
sidebar_position: 23
---

# ユーザー所持ロール取得
ユーザー情報の取得を行います。

## 基本仕様
- エンドポイント : /usersroles/{user_id}
- メソッド : GET

## リクエストヘッダー
APIキーなどの共通の設定は「Cracker API概要」を参照してください。

## パスパラメータ

|パラメータ名|タイプ|必須|説明|
|----|----|----|----|
|user_id|文字列|必須|ロールを取得する対象ユーザーIDを指定します。|

## クエリパラメータ
なし

## リクエストボディ
なし

## レスポンスボディ
配列で返します。

|パラメータ名|タイプ|説明|
|----|----|----|
|user_id|文字列|ユーザーID|
|role_id|文字列|ロールID|

レスポンスボディサンプル
```
[
  {
    "user_id": "admin",
    "role_id": "bdae310f-2eee-4f01-97ec-6ffb6779e7aa"
  }
]
```
