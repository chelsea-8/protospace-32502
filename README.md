＃ テーブル設計

## users テーブル

| Column     | Type   | Options   |
| --------   | ------ | ----------|
| email      | string | not: nill |
| password   | string | not: nill |
| name       | string | not: nill |
| profile    | text   | not: nill |
| occupation | text   | not: nill |
| position   | text   | not: nill |

### Association 

- has_many :comments
- has_many :prototype

## prototype テーブル

| Column     | Type       | Options    |
| --------   | ------     | ---------- |
| title      | string     | not: false |
| catch_copy | text       | not: false |
| concept    | text       | not: false |
| user       | references | not: nill  |

### Association 

- has_many :comments
- belongs_to :user


## comments テーブル

| Column     | Type       | Options           |
| --------   | ---------- | ----------------- |
| text       | text       | nill: false       |
| user       | references | foreign_key: true |
| prototype  | references | foreign_key: true |

### Association 

- belongs_to :user
- belongs_to :prototype
