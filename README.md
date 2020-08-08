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

# jeng DB設計
## profilesテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|password|string|null: false|
|confirm_password|string|null: false|
### Association
- belongs_to :japanese
- belongs_to :english

## japanesesテーブル
|Column|Type|Options|
|------|----|-------|
|image|string|null: false|
|nickname|string|null: false|
|sex|string|null: false|
|how_old|string|null: false|
|prefecture|string|null: false|
|explain|string|null: false|
### Association
- has_one :profile
- has_many :chats

## englishesテーブル
|Column|Type|Options|
|------|----|-------|
|image|string|null: false|
|nickname|string|null: false|
|sex|string|null: false|
|how_old|string|null: false|
|prefecture|string|null: false|
|explain|string|null: false|
### Association
- has_one :profile
- has_many :chats

## chatsテーブル
|Column|Type|Options|
|------|----|-------|
|content|text||
|image|string|null: false|
|japanese_id|integer|null: false|
|english_id|integer|null: false|
### Association
- has_one :japanese
- has_one :english

