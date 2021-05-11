# テーブル設計

## users テーブル
| Column        | Type   | Options     |
| --------------| ------ | ----------- |
| nickname      | string | null: false |
| email         | string | null: false |
| password      | string | null: false |

### Association
- has_many :achivements
- has_many :promises




## achivements テーブル
| Column    | Type    | Options     |
| --------- | ------- | ----------- |
| goal_name | string  | null: false |
| memo      | text    | null: false |

### Association
- belongs_to :user
- has_many :promises





## promises テーブル
| Column         | Type     | Options     |
| -------------- | -------- | ----------- |
| user_id        | integer  | null: false |
| achivement_id  | integer  | null: false |

### Association

- belongs_to :users
- belongs_to :achivements