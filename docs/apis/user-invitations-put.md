---
sidebar_position: 18.5
---

# 招待コード更新
既存招待コードの情報の更新を行います。

## 基本仕様
- エンドポイント : /user-invitations/{invitation_code}
- メソッド : PUT

## リクエストヘッダー
APIキーなどの共通の設定は「Cracker API概要」を参照してください。

## パスパラメータ

|パラメータ名|タイプ|必須|説明|
|----|----|----|----|
|invitation_code|文字列|必須|情報の更新を行う招待コードを指定します。|

## クエリパラメータ
なし

## リクエストボディ

|パラメータ名|タイプ|必須|説明|
|----|----|----|----|
|count_limit|数値|必須|残登録可能数|
|usage_count|数値|必須|使用回数|

リクエストボディサンプル
```
{
    "count_limit": 17,
    "usage_count": 3
}
```

## レスポンスボディ

|パラメータ名|タイプ|説明|
|----|----|----|
|invitation_code|文字列|招待コード|
|usage_count|数値|使用回数|
|count_limit|数値|残登録可能数|
|time_limit|タイムスタンプ|登録可能制限時間 ``yyyy-MM-dd HH:mm:ss``|

レスポンスボディサンプル
```
{
    "invitation_code": "gBji8VYr",
    "usage_count": 3,
    "count_limit": 17,
    "time_limit": "2024-04-21 20:12:48"
}
```
