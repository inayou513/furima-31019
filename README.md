# README

## users テーブル

| Column          | Type    | Options     |
| --------------- | ------- | ----------- |
| nickname        | string  | null: false |
| email           | string  | null: false |
| password        | string  | null: false |
| first_name      | string  | null: false |
| last_name       | string  | null: false |
| first_name_kana | string  | null: false |
| last_name_kana  | string  | null: false |
| birth_year      | integer | null: false |
| birth_month     | integer | null: false |
| birth_day       | integer | null: false |

### Association
- has_many :items
- has_many :buys


## items テーブル

| Column      | Type       | Options           |
| ----------- | ---------- | ----------------- |
| image       |            | null: false       |
| title       | string     | null: false       |
| description | text       | null: false       |
| category    | string     | null: false       |
| delivery    | string     | null: false       |
| ship_form   | string     | null: false       |
| ship_date   | string     | null: false       |
| value       | integer    | null: false       |
| user        | references | foreign_key: true |

### Association 
- belongs_to :user
- has_one :buy


##  buy テーブル

| Column  | Type       | Options           |
| ------- | ---------- | ----------------- |
| user    | references | foreign_key: true |
| item    | references | foreign_key: true |
| buy_day | integer    | null: false       |

### Association 
- belongs_to :user
- belongs_to :item
- has_one :buy


| Column      | Type       | Options           |
| ----------- | ---------- | ----------------- |
| postcode    | string     | null: false       |
| prefectures | string     | null: false       |
| city        | string     | null: false       |
| house_num   | string     | null: false       |
| building    | string     |                   |
| tell        | integer    | null: false       |
| buy         | references | foreign_key: true |

### Association 
- belongs_to :buy