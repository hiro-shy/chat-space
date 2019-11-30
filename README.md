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

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|integer|null: false|
|email|integer|null: false|
|password|integer|null: false|

### Association
- has_many :message
- has_many :groups_users
- has_many :groups, through: groups_users

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|group_name|integer|null: false|
|user_id|integer|null: false|

### Association
- has_many :message
- has_many :groups_users
- has_many :users, through: groups_users
- belongs_to :user

## messageテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string|null: false|
|group_id|integer|null: false|
|user_id|integer|null: false|

### Association
- belongs_to :group
- belongs_to :user

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
