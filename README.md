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