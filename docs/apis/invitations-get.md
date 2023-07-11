---
sidebar_position: 17
---

# 招待コード取得
招待コード情報の取得を行います。

## 基本仕様
- エンドポイント : /invitations/{invitation_code}
- メソッド : GET

なおエンドポイントの{invitation_code}は省略可能です。省略した場合招待コード一覧が取得できます。

## リクエストヘッダー
APIキーなどの共通の設定は「Cracker API概要」を参照してください。

## パスパラメータ

|パラメータ名|タイプ|必須|説明|
|----|----|----|----|
|invitation_code|文字列||特定の招待コード情報を取得する場合、招待コードを指定します。|

## クエリパラメータ
なし

## リクエストボディ
なし

## レスポンスボディ

|パラメータ名|タイプ|説明|
|----|----|----|
|invitation_code|文字列|招待コード|
|usage_count|文字列|使用回数|
|count_limit|配列|残登録可能数|
|time_limit|文字列|登録可能制限時間 ``yyyy-MM-dd HH:mm:ss``|
|creater|文字列|コード作成ユーザーID|

レスポンスボディサンプル
```
[
    {
        "invitation_code": "EhaO8C5X",
        "usage_count": 3,
        "count_limit": 17,
        "time_limit": "2023-07-09 15:30:42",
        "creater": "admin"
    }
]
```
