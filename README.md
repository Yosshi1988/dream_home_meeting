# テーブル設計

## users テーブル

| Column             | Type   | Options                    |
| ------------------ | ------ | -------------------------- |
| last_name          | string  | null: false               |
| first_name         | string  | null: false               |
| email              | string  | null: false, unique: true |
| encrypted_password | string  | null: false               |
| role               | string  | null: false               |

### Association

- has_many :drawings
- has_many :drawing_confirmations
- has_many :drawing_decisions
- has_many :electricals
- has_many :electrical_confirmations
- has_many :electrical_decisions
- has_many :housing_equipments
- has_many :housing_equipment_confirmations
- has_many :housing_equipment_decisions
- has_many :exteriors
- has_many :exterior_confirmations
- has_many :exterior_decisions
- has_many :interiors
- has_many :interior_confirmations
- has_many :interior_decisions
- has_many :others
- has_many :other_confirmations
- has_many :other_decisions

## drawings テーブル

| Column             | type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| meeting_day        | date       | null: false                    |
| comment            | text       | null: false                    |
| user               | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- has_one :drawing_confirmation
- has_one :drawing_decision

## electricals テーブル

| Column             | type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| meeting_day        | date       | null: false                    |
| comment            | text       | null: false                    |
| user               | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- has_one :electrical_confirmation
- has_one :electrical_decision

## housing_equipments  テーブル

| Column         | Type       | Options                        |
| -------------- | ---------- | ------------------------------ |
| meeting_day    | date       | null: false                    |
| comment        | text       | null: false                    |
| user           | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- has_one :housing_equipment_confirmation
- has_one :housing_equipment_decision

## exteriors  テーブル

| Column             | type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| meeting_day        | date       | null: false                    |
| comment            | text       | null: false                    |
| user               | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- has_one :exterior_confirmation
- has_one :exterior_decision

## interiors  テーブル

| Column             | type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| meeting_day        | date       | null: false                    |
| comment            | text       | null: false                    |
| user               | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- has_one :interior_confirmation
- has_one :interior_decision

## others   テーブル

| Column             | type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| meeting_day        | date       | null: false                    |
| comment            | text       | null: false                    |
| user               | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- has_one :other_confirmation
- has_one :other_decision

## drawing_confirmations  テーブル

| Column             | type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| confirmation_day   | date       | null: false                    |
| user               | references | null: false, foreign_key: true |
| drawing            | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :drawing

## drawing_decisions  テーブル

| Column             | type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| decision_day       | date       | null: false                    |
| user               | references | null: false, foreign_key: true |
| drawing            | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :drawing

## electrical_confirmations  テーブル

| Column             | type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| confirmation_day   | date       | null: false                    |
| user               | references | null: false, foreign_key: true |
| electrical         | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :electrical

## electrical_decisions  テーブル

| Column             | type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| decision_day       | date       | null: false                    |
| user               | references | null: false, foreign_key: true |
| electrical         | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :electrical

## housing_equipment_confirmations  テーブル

| Column             | type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| confirmation_day   | date       | null: false                    |
| user               | references | null: false, foreign_key: true |
| housing_equipment  | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :housing_equipment

## housing_equipment_decisions   テーブル

| Column             | type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| decision_day       | date       | null: false                    |
| user               | references | null: false, foreign_key: true |
| housing_equipment  | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :housing_equipment

## exteriors_confirmations  テーブル

| Column             | type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| confirmation_day   | date       | null: false                    |
| user               | references | null: false, foreign_key: true |
| exterior           | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :exterior

## exteriors_decisions  テーブル

| Column             | type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| decision_day       | date       | null: false                    |
| user               | references | null: false, foreign_key: true |
| exterior           | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :exterior

## interiors_confirmations  テーブル

| Column             | type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| confirmation_day   | date       | null: false                    |
| user               | references | null: false, foreign_key: true |
| interior           | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :interior

## interiors_decisions  テーブル

| Column             | type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| decision_day       | date       | null: false                    |
| user               | references | null: false, foreign_key: true |
| interior           | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :interior

## others_confirmations  テーブル

| Column             | type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| confirmation_day   | date       | null: false                    |
| user               | references | null: false, foreign_key: true |
| other              | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :other

## others_decisions  テ-ブル

| Column             | type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| decision_day       | date       | null: false                    |
| user               | references | null: false, foreign_key: true |
| other              | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :other