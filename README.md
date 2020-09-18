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

# テーブル設計

## users テーブル

| Column          | Type   | Options     |
| --------------- | ------ | ----------- |
| nickname        | string | null: false |
| email           | string | null: false |
| password1       | string | null: false |
| password2       | string | null: false |
| firstname       | string | null: false |
| firstname_kana  | string | null: false |
| familyname      | string | null: false |
| familyname_kana | string | null: false |
| date            | date   | null: false |

### Association

- has_many :tweets
- has_many :comments
- has_one_attached :image


## tweets テーブル

| Column       | Type       | Options                        |
| ------------ | ---------- | ------------------------------ |
| name         | string     | null: false                    |
| price        | string     | null: false                    |
| discount     | string     | null: false                    |
| user         | references | null: false, foreign_key: true |
| age_id       | integer    | null: false                    |
| area_id      | integer    | null: false                    |
| day_id       | integer    | null: false                    |
| crowd_id     | integer    | null: false                    |
| title        | string     | null: false                    |
| text         | text       | null: false                    |

### Association

- belongs_to :user
- has_many :comments
- belongs_to_active_hash :age
- belongs_to_active_hash :crowd
- belongs_to_active_hash :area
- belongs_to_active_hash :day
- has_one_attached :image


## comments テーブル

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| user   | references | null: false, foreign_key: true |
| tweet  | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :tweet




