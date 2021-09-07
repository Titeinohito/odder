
## usersテーブル

| Column              | Type       | Options           |
| ------------------- | ---------- | ----------------- |
| nickname            | string     | null: false       |
| password            | string     | null: false       |

### Association

- has_many :moneys
- has_many :stakes_management

## moneysテーブル

| Column              | Type       | Options           |
| ------------------- | ---------- | ----------------- |
| title               | string     | null: false       |
| have_money          | integer    | null: false       |
| user                | references | foreign_key: true |

### Association

- belongs_to :user
- has_many :bet
- has_many :money_log

## betsテーブル

| Column              | Type       | Options           |
| ------------------- | ---------- | ----------------- |
| bet_money           | integer    | null: false       |
| money               | references | foreign_key: true |
| stakes              | references | foreign_key: true |

### Association

- belongs_to :money
- belongs_to :stake

## money_logテーブル

| Column              | Type       | Options           |
| ------------------- | ---------- | ----------------- |
| have_money_log      | integer    | null: false       |
| money_expenditure   | integer    | null: false       |
| expenditure_type    | string     | null: false       |
| money               | references | foreign_key: true |

### Association

belongs_to :money

## stakes_managementsテーブル

| Column              | Type       | Options           |
| ------------------- | ---------- | ----------------- |
| title               | string     | null: false       |
| stakes_title        | string     | null: false       |
| tax                 | integer    | null: false       |
| win_stakes          | integer    | null: false       |
| user                | references | foreign_key: true |

### Association

belongs_to :user
has_many :stakes

## stakesテーブル

| Column              | Type       | Options           |
| ------------------- | ---------- | ----------------- |
| stakes_name         | string     | null: false       |
| stakes_management   | references | foreign_key: true |

### Association

belongs_to :staked_management
has_many :bet
