---
sidebar_position: 8
---

# ゲスト更新
既存ゲストの情報の更新を行います。

## 基本仕様
- エンドポイント : /guests/{group_id}
- メソッド : PUT

## リクエストヘッダー
APIキーなどの共通の設定は「Cracker API概要」を参照してください。

## パスパラメータ

|パラメータ名|タイプ|必須|説明|
|----|----|----|----|
|group_id|文字列|必須|情報の更新を行うゲストIDを指定します。|

## クエリパラメータ
なし

## リクエストボディ

|パラメータ名|タイプ|必須|説明|
|----|----|----|----|
|guests|配列|必須|来場者の続柄と名前を指定します。|
|st_name|文字列|`guest_type`がfamilyの場合必須|生徒名|
|st_belong|文字列|`guest_type`がfamilyの場合必須|生徒所属|
|st_grade|文字列|`guest_type`がfamilyの場合必須|生徒学年, `n年`表記|
|st_class|文字列|`guest_type`がfamilyの場合必須|生徒クラス, `n組`表記(クラスなしの場合は`なし`)|
|state|文字列|必須|ゲストの入退場状況を指定します。|
|mail|文字列|必須|ゲストのメールアドレス指定します。|
|parking|数値|必須|駐車券の必要有無 (1:必要, 0:不要)|

`guest_type`が`other`の場合、生徒関係の情報は必要ありません。

リクエストボディサンプル
```
{
    "guests": [
        [
            "佐藤恵",
            "母"
        ],
        [
            "佐藤健一",
            "兄"
        ],[
            "佐藤次郎",
            "弟"
        ]
    ],
    "guest_type":"family",
    "st_name":"佐藤花子",
    "st_belong":"普通科",
    "st_grade":"3年",
    "st_class":"1組",
    "state": "entered",
    "mail": "satou@example.com",
    "parking": 1
}
```

## レスポンスボディ

|パラメータ名|タイプ|説明|
|----|----|----|
|group_id|文字列|ゲストID|
|guests|配列|来場者の続柄と名前|
|guest_type|文字列|family/other|
|st_name|文字列|生徒名|
|st_belong|文字列|生徒所属|
|st_grade|文字列|生徒学年, `n年`表記|
|st_class|文字列|生徒クラス, `n組`表記(クラスなしの場合は`なし`)|
|state|文字列|ゲストの入退場状況|
|mail|文字列|ゲストのメールアドレス|
|parking|数値|駐車券の必要有無 (1:必要, 0:不要)|

`guest_type`が`other`の場合、生徒情報は空白でレスポンスされます。

レスポンスボディサンプル
```
{
  "group_id": "99b0c89c-b00c-48cb-9831-04cf536644bd",
  "guests": [
    [
      "佐藤恵",
      "母"
    ],
    [
      "佐藤健一",
      "兄"
    ],
    [
      "佐藤次郎",
      "弟"
    ]
  ],
  "guest_type": "family",
  "st_name": "佐藤花子",
  "st_belong": "普通科",
  "st_grade": "3年",
  "st_class": "1組",
  "state": "entered",
  "mail": "satou@example.com",
  "parking": 1
}
```
