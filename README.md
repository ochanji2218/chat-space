### usersテーブル
Column|Type|Options|
|------|----|-------|
### Association
  has_many :messageas
  has_many :group_users
  has_many :groups, through: :group_users
end

### messagesテーブル
|Column  |Type      |Options|
|id      |integer   ||
|body    |text      ||
|image   |string    ||
|user_id |references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|

### Association
  belongs_to : user
  belongs_to : group
end

## groupsテーブル
|Column    |Type   |Options|
|id        |integer||
|group_name|string |null: false, foreign_key: true|

### Association
  has_many :messages
  has_many :group_users
  has_many :users, through: :group_users
end

## group_usersテーブル
|Column  |Type      |Options|
|id      |integer   ||
|user_id |references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|

### Association
  belongs_to : user
  belongs_to : group
end