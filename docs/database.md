---
sidebar_position: 2
---

# データベース構成と規則
データベースの構成と内部データの規則
- user  

|key|type|description|
|----|----|----|
|user_id|VARCHAR(20)|primary key|
|name|VARCHAR(40)|ユーザー名|
|roles|longtext|["role1","role2"]|
|exhibit_id|VARCHAR(20)|所属展示ID|
|password|VARCHAR(256)|「セキュリティ/パスワード保管」に基づく|

- guest

|key|type|description|
|----|----|----|
|guest_id|VARCHAR(128)|primary key, uuid|
|guests|longtext|[["続柄","氏名"]]|
|student_info|longtext|["生徒氏名","生徒所属","生徒学年","生徒クラス"]|
|state|VARCHAR(20)|not_entered/entered/deleted|
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
