# README

## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| nickname           | string | null: false |
| email              | string | null: false |
| encrypted_password | string | null: false |
| first_name         | string | null: false |
| last_name          | string | null: false |
| first_name_kana    | string | null: false |
| last_name_kana     | string | null: false |
| birthday           | date   | null: false |

### Association
- has_many :items
- has_many :buys


## items テーブル 

| Column       | Type       | Options           |
| ------------ | ---------- | ----------------- |
| title        | string     | null: false       |
| description  | text       | null: false       |
| category_id  | integer    | null: false       |
| status_id    | integer    | null: false       |
| delivery_id  | integer    | null: false       |
| ship_form_id | integer    | null: false       |
| ship_date_id | integer    | null: false       |
| value        | integer    | null: false       |
| user         | references | foreign_key: true |

### Association 
- belongs_to :user
- has_one :buy


##  buys テーブル

| Column  | Type       | Options           |
| ------- | ---------- | ----------------- |
| user    | references | foreign_key: true |
| item    | references | foreign_key: true |

### Association 
- belongs_to :user
- belongs_to :item
- has_one :address


### address テーブル

| Column         | Type       | Options                   |
| -------------- | ---------- | ------------------------- |
| postcode       | string     | null: false               |
| prefectures_id | integer    | null: false               |
| city           | string     | null: false               |
| house_num      | string     | null: false               |
| building       | string     |                           |
| tell           | string     | null: false, unique: true |
| buy            | references | foreign_key: true         |

### Association 
- belongs_to :buy