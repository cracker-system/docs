---
sidebar_position: 16
---

# アクティビティ登録
新規アクティビティの登録を行います。

## 基本仕様
- エンドポイント : /activities
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
|guest_id|文字列|必須|ゲストID|
|user_id|配列|必須|処理を行ったユーザーID|
|exhibit_id|文字列|必須|入退場を行った展示ID|
|activity_type|文字列|必須|enter/exit|

リクエストボディサンプル
```
{
    "guest_id": "9a680c1d-a109-93b0-c875-5a99377c75b4",
    "user_id": "31ennichi",
    "exhibit_id": "31",
    "activity_type": "enter"
}
```

## レスポンスボディ

|パラメータ名|タイプ|説明|
|----|----|----|
|activity_id|文字列|アクティビティID、自動生成のUUID|
|guest_id|文字列|ゲストID|
|user_id|配列|処理を行ったユーザーID|
|exhibit_id|文字列|入退場を行った展示ID|
|activity_type|文字列|enter/exit|
|timestamp|タイムスタンプ|処理時刻|

activity_typeについて
- enter : 入場処理が行われた際のタイプ
- exit : 退場処理が行われた際のタイプ

レスポンスボディサンプル
```
[
    {
        "activity_id": "ce6a4d1c-cd6b-1f1e-ac79-71dd423cfd9a",
        "guest_id": "9a680c1d-a109-93b0-c875-5a99377c75b4",
        "user_id": "31ennichi",
        "exhibit_id": "31",
        "activity_type": "enter",
        "timestamp": "2023-05-21 11:38:48"
    }
]
```
