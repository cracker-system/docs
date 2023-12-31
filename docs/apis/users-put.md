---
sidebar_position: 4
---

# ユーザー更新
既存ユーザーの情報の更新を行います。

## 基本仕様
- エンドポイント : /users/{user_id}
- メソッド : PUT

## リクエストヘッダー
APIキーなどの共通の設定は「Cracker API概要」を参照してください。

## パスパラメータ

|パラメータ名|タイプ|必須|説明|
|----|----|----|----|
|user_id|文字列|必須|情報の更新を行うユーザーIDを指定します。|

## クエリパラメータ
なし

## リクエストボディ

|パラメータ名|タイプ|必須|説明|
|----|----|----|----|
|user_name|文字列|必須|ユーザー名を指定します。|
|exhibit_id|文字列|必須|ユーザーの所属展示の展示IDを指定します。|
|password|文字列|必須|「セキュリティ/パスワード保管」に基づき、パスワードを指定します。|

リクエストボディサンプル
```
{
    "user_name": "3-1 縁日",
    "exhibit_id": "31",
    "password": "9a584b1ab14c784933959ecffa8c3925de5426132554c8ae0f55184c428da0b9"
}
```

## レスポンスボディ

|パラメータ名|タイプ|説明|
|----|----|----|
|user_id|文字列|ユーザーID|
|user_name|文字列|ユーザー名|
|exhibit_id|文字列|ユーザーの所属展示|

レスポンスボディサンプル
```
{
    "user_id": "31ennichi",
    "user_name": "3-1 縁日",
    "exhibit_id": "31"
}
```
