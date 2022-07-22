# DB 設計

## profiles テーブル

| Column             | Type                | Options                   |
|--------------------|---------------------|---------------------------|
| title              | string              | null: false               |
| profile            | text                | null: false               |

### Association

* has_many : menus
* has_many : reservations

## menus テーブル

| Column         | Type             | Options                        |
|----------------|------------------|--------------------------------|
| course         | string           | null: false                    |
| writing        | text             | null: false                    |

### Association

- belongs_to : profile
- has_many : reservation

## reservations テーブル

| Column            | Type       | Options                        |
|-------------------|------------|--------------------------------|
| name              | string     | null: false                    |
| email             | string     | null: false, unique: true      |
| telephone_number  | string     | null: false                    |
| month_id          | integer    | null: false                    |
| time_id           | integer    | null: false                    |
| course            | string     | null: false                    |
| note              | text       | null: false                    |

### Association

- belongs_to : profile
- belongs_to : menu