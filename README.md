# README
# テーブル設計

## users テーブル

| Column             | Type   | Options                  |
| ------------------ | ------ | ------------------------ |
| email              | string | null: false ,unique: true|
| encrypted_password | string | null: false              |
| profile            | text   | null: false              |
| occupation         | text   | null: false              |
| position           | text   | null: false              |



### Association

- has_many :prototypes
- has_many :comments

## comments テーブル

| Column    | Type       | Options                       |
| ------    | ---------- | ----------------------------- |
| content   | text       | null: false                   |
| phototype | references | null: false, foreign_key: true|
| user      | references | null: false, foreign_key: true|

### Association

- has_many :room_users
- has_many :users, through: :room_users
- has_many :messages

## prototypes テーブル

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| title   | string | null: false |
| catch_copy   | text | null: false |
| concept   | text | null: false |
| user   | references | null: false, references|

### Association

- belongs_to :room
- belongs_to :user


