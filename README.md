# アプリ名
Grow Up

# 概要
達成したい目標を立て、達成することを人と約束して遂行するアプリです。

# 制作背景(意図)
自分で立てた目標を達成することで、自己肯定感を高められるようにすることが目的です。
目標達成は、人と約束して、達成せざるを得ない環境を作ることが有効的だと考えました。
前職で、部下が目標を立てても、怠惰な面に負けたり、目標設定が曖昧であったり、様々な要因で中々最後まで遂行できることができなかったことがありました。しかし、人と約束させて、進捗管理を共に行うことで無事達成できたという結果があります。このことから約束するのは有効的だと考えております。

# DEMO
トップページ(マイページ、ログアウト、目標投稿、約束ページへ遷移)

https://gyazo.com/1cb3af81a1a5b8d43ba9e4f53ada467d
https://i.gyazo.com/1cb3af81a1a5b8d43ba9e4f53ada467d.gif

# 実装予定の内容
-目標投稿への約束コメント機能
-約束達成画面


# DB設計

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
| memo           | text     | null: false |

### Association

- belongs_to :users
- belongs_to :achivements