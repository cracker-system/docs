---
sidebar_position: 18
---

# 招待コード登録
新規ユーザーの登録を行います。

## 基本仕様
- エンドポイント : /user-invitations
- メソッド : POST

## リクエストヘッダー
APIキーなどの共通の設定は「Cracker API概要」を参照してください。

## パスパラメータ
なし

## クエリパラメータ
なし

## リクエストボディ

|パラメータ名|タイプ|必須|説明|
|----|----|----|----|
|count_limit|数値|必須|残登録可能数|
|creator|文字列|必須|コード作成ユーザーID|

リクエストボディサンプル
```
{
    "count_limit": 20,
    "creator": "admin"
}
```

## レスポンスボディ

|パラメータ名|タイプ|説明|
|----|----|----|
|invitation_code|文字列|招待コード|
|usage_count|数値|使用回数|
|count_limit|数値|残登録可能数|
|time_limit|タイムスタンプ|登録可能制限時間 ``yyyy-MM-dd HH:mm:ss``|
|creator|文字列|コード作成ユーザーID|

レスポンスボディサンプル
```
{
    "invitation_code": "EhaO8C5X",
    "usage_count": 3,
    "count_limit": 17,
    "time_limit": "2023-07-09 15:30:42",
    "creator": "admin"
}
```
