---
sidebar_position: 2
---

# データベース構成と規則
データベースの構成と内部データの規則
- user  

|key|type|description|
|----|----|----|
|user_id|VARCHAR(20)|primary key|
|user_name|VARCHAR(40)|ユーザー名|
|exhibit_id|VARCHAR(20)|所属展示ID|
|password|VARCHAR(256)|「セキュリティ/パスワード保管」に基づく|

- guest

|key|type|description|
|----|----|----|
|guest_id|VARCHAR(128)|primary key, uuid|
|guests|longtext|[["続柄","氏名"]]|
|st_name|VARCHAR(400)|生徒氏名|
|st_belong|VARCHAR(400)|生徒所属|
|st_grade|VARCHAR(400)|生徒学年|
|st_class|VARCHAR(400)|生徒クラス|
|state|VARCHAR(20)|not_entered/entered/disable|
|mail|VARCHAR(400)||

stateについて
- not_entered : 未入場
- entered : 入場済み
- disable : ゲスト情報無効化済み

not_entered/enteredの切り替えは文化祭入場口で処理した場合のみ行います。  
各展示会場での処理では変更しません。  
disableとなったゲストは入場が許可されません。

- activity

|key|type|description|
|----|----|----|
|activity_id|VARCHAR(128)|primary key, uuid|
|guest_id|VARCHAR(128)|対象ゲストID|
|user_id|VARCHAR(20)|処理を行ったユーザーID|
|exhibit_id|VARCHAR(20)|処理が行われた展示ID|
|activity_type|VARCHAR(5)|enter/exit|
|timestamp|timestamp|処理時刻|

activity_typeについて
- enter : 入場処理が行われた際のタイプ
- exit : 退場処理が行われた際のタイプ

- exhibit
 
|key|type|description|
|----|----|----|
|exhibit_id|VARCHAR(20)|primary key|
|exhibit_name|VARCHAR(60)|展示名|

- invitation

|key|type|description|
|----|----|----|
|invitation_code|VARCHAR(8)|primary key|
|usage_count|INT(4)|使用回数|
|count_limit|INT(4)|残登録可能数|
|time_limit|timestamp|登録可能制限時間|
|creater|VARCHAR(20)|コード制作ユーザーID|

- role

|key|type|description|
|----|----|----|
|role_id|VARCHAR(128)|primary key, uuid|
|role_name|VARCHAR(60)|ロール名|
|authority|VARCHAR(60)|ex)``A000000000000000000000000000000``|

authorityについて  
`A`で始める。  
各桁に権限の有無を記す。  
`0`は権限なし、`1`は権限あり

- usersrole

|key|type|description|
|----|----|----|
|user_id|VARCHAR(20)||
|role_id|VARCHAR(128)||
