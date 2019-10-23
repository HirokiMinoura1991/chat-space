usersテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|
|email|string|
|password|string|
|username|string|

### Association
- has_many :group
- has_many :message


messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|
|image|integer|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user


groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
- has_many :message
- has_many :user

groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user