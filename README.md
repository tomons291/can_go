# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

＃ テーブル設計

## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| name               | string | null: false |
| email              | string | null: false |
| encrypted_password | string | null: false |

### Association

- has_many :room_users
- has_many :rooms, through: :test_users
- has_many :tests

## tests テーブル

| Column                  | Type   | Options     |
| ----------------------- | ------ | ----------- |
| test_kai                | string | null: false |
| test_problem            | string | null: false |
| test_Choice_1           | string | null: false |
| test_Choice_2           | string | null: false |
| test_Choice_3           | string | null: false |
| test_Choice_4           | string | null: false |
| test_Choice_5           | string | null: false |

### Association

- has_many :room_users
- has_many :users, through: :test_users

## users_test テーブル

| Column   | Type       | Options                        |
| -------- | ---------- | ------------------------------ |
| user     | references | null: false, foreign_key: true |
| test     | references | null: false, foreign_key: true |
| anser    | string     | null: false                    |
| result   | string     | null: false                    |

### Association

- belongs_to :test
- belongs_to :user