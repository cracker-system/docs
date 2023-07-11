---
sidebar_position: 15
---

# アクティビティ取得
アクティビティ情報の取得を行います。

## 基本仕様
- エンドポイント : /activities/{guest_id}
- メソッド : GET

なおエンドポイントの{guest_id}は省略可能です。省略した場合アクティビティ一覧が取得できます。

## リクエストヘッダー
APIキーなどの共通の設定は「Cracker API概要」を参照してください。

## パスパラメータ

|パラメータ名|タイプ|必須|説明|
|----|----|----|----|
|guest_id|文字列||特定のゲストのアクティビティ情報を取得する場合、ゲストIDを指定します。|

## クエリパラメータ
なし

## リクエストボディ
なし

## レスポンスボディ

|パラメータ名|タイプ|説明|
|----|----|----|
|activity_id|文字列|アクティビティID、自動生成のUUID|
|guest_id|文字列|ゲストID|
|user_id|配列|処理を行ったユーザーID|
|exhibit_id|文字列|入退場を行った展示ID|
|activity_type|文字列|enter/exit|
|timestamp|文字列|処理時刻|

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
