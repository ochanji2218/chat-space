### usersテーブル
Column|Type|Options|
|------|----|-------|
add_column :name, :author, :references
### Association
  has_many :messageas
  has_many :groups, through: :group_users
  has_many :group_users
end

### messagesテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|

add_column :text, :author, :text
add_column :image, :author, :string

### Association
  belongs_to : user
  belongs_to : group
end

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
add_column :name, :author, :references

### Association
  has_many :messages
  has_many :users, through: :group_users
  has_many :group_users
end

## group_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|

### Association
  belongs_to : user
  belongs_to : group
end