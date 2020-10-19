# テーブル設計

## users テーブル

| Column      | Type   | Options     |
| ----------- | ------ | ----------- |
| name        | string | null: false |
| email       | string | null: false |
| password    | string | null: false |
| profile     | text   | null: false |
| occupation  | text   | null: false |
| position    | text   | null: false |

### Association
- has_many :user
- has_many :comments


## prototype テーブル

| Column    | Type       | Options     |
| --------- | ---------- | ----------- |
| title     | string     | null: false |
|catch_copy | text       | null: false |
|concept    | text       | null: false |
|image      |            |             |
|user       | references |             |

### Association

- belongs_to :user
- has_many :comments

## comments テーブル

| Column      | Type       | Options                        |
| ----------- | ---------- | ------------------------------ |
| text        | text       | null: false                    |
| user        | references |                                |
| prototype   | references |                                |

### Association

- belongs_to :prototype
- belongs_to :user