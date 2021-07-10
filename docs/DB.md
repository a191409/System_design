# システム設計最終課題DB設計図

## 改版履歴
|日付|編集者|版数|変更履歴|
|---|-----|---|-------|
|2021.07.10|木村華|初版|初版作成|


## データベース名　DB
### users
|カラム名|項目名|概要|データ型|NULLを許容|PRI|DEFAULT|備考|
|-------|-----|---|-------|--------|---|--------|---|
|id|ユーザー識別ID|登録した順に自動的に入力される番号|INT|NO|○|NULL|auto_increment|
|names|ユーザー名|半角20文字まで|VARCHAR(20)|NO||NULL|データベースに登録されている他のユーザー名と同一を認めない。|
|passes|パスワード|半角20文字まで|VARCHAR(20)|NO||NULL||
|created_at|作成日|半角20文字まで|VARCHAR(20)|NO||NULL||
|updated_at|更新日|半角20文字まで|VARCHAR(20)|NO||NULL||

### matches
|カラム名|項目名|概要|データ型|NULLを許容|PRI|DEFAULT|備考|
|-------|-----|---|-------|--------|---|--------|---|
|id|大会名識別ID|登録した順に自動的に入力される番号|INT|NO|○|NULL|auto_increment|
|names|ユーザー名|半角20文字まで|VARCHAR(20)|NO||NULL|データベースに登録されている他の大会名と同一を認めない。|

### scores
|カラム名|項目名|概要|データ型|NULLを許容|PRI|DEFAULT|備考|
|-------|-----|---|-------|--------|---|--------|---|
|id|スコア識別ID|登録した順に自動的に入力される番号|INT|NO|○|NULL|auto_increment|
|score|スコア|スコアの値|INT|NO||NULL||
|users_id|ユーザー識別ID|登録した順に自動的に入力される番号|INT|NO|○|NULL|usersテーブルのid|
|results_id|対戦結果識別ID|登録した順に自動的に入力される番号|INT|NO|○|NULL|resultsテーブルのid|


### results
|カラム名|項目名|概要|データ型|NULLを許容|PRI|DEFAULT|備考|
|-------|-----|---|-------|--------|---|--------|---|
|id|対戦結果識別ID|登録した順に自動的に入力される番号|INT|NO|○|NULL|auto_increment|
|rounds|大会の段階識別|大会の何回戦目を記録する|INT|NO|○|NULL||
|scores_id_1|入力者の対戦のスコアを管理しているID|スコアを登録した順に自動的に入力された番号|INT|NO||NULL|scoresテーブルのid|
|scores_id_2|入力者の対戦のスコアを管理しているID|スコアを登録した順に自動的に入力された番号|INT|NO||NULL|scoresテーブルのid|
|matches_id|大会名を管理しているID|大会名を登録した順に自動的に入力された番号|INT|NO||NULL|matchesテーブルのid|
