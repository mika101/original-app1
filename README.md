# テーブル設計

## users テーブル

| Column               | Type   | Options                   |
| --------             | ------ | -----------               |
| nickname             | string | null: false               |
| email                | string | null: false ,unique: true |
| encrypted_password   | string | null: false               |
| family_name          | string | null: false               |
| first_name           | string | null: false               |
| family_name_furigana | string | null: false               |
| first_name_furigana  | string | null: false               |
| birthday             | date   | null: false               |

### Association
- has_many :items

## items テーブル

| Column                 | Type       | Options                        |
| --------               | ------     | -----------                    |
| item_name              | string     | null: false                    |
| category_id            | integer    | null: false                    |
| user                   | references | null: false, foreign_key: true |

### Association
- belongs_to :user
- has_one :item_information


## item_information テーブル

| Column                 | Type       | Options                        |
| --------               | ------     | -----------                    |
| item_name              | string     | null: false                    |
| description_of_item    | text       | null: false                    |
| category_id            | integer    | null: false                    |
| quantity_id            | integer    | null: false                    |
| price                  | integer    | null: false                    |
| store_id               | integer    | null: false                    |
| purchase_date_month_id | integer    | null: false                    |
| purchase_date_year_id  | integer    | null: false                    |
| purchase_date_day_id   | integer    | null: false                    |
| user                   | references | null: false, foreign_key: true |

### Association
- belongs_to :item