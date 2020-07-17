# chat-space

## \:love_letter: 概要
LINEのようなメッセージ送信機能付きアプリ  
・メッセージ送信  
・ユーザー登録  
・グループ登録  

## \:love_letter: 本番環境
http://18.180.140.15/ 

テスト用ユーザー  
メールアドレス：test@test.test  
パスワード：testtest  

## \:love_letter: DEMO
https://gyazo.com/e0342f8907c3fc1e018e8fdc2b419a3e
https://gyazo.com/ca8831825b4ec0a7b00a1e67f8b4b60b

## \:love_letter: 開発環境
・VSCode（Visual Studio Code）  
・Ruby on Rails  
・MySQL  
・Github  
・AWS  
・JavaScript  


## \:love_letter:DB設計

# chat-space DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|nickname|string|null: false|
### Association
- has_many :groups, through: :groups_users
- has_many :messages
- has_many :groups_users

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text||
|image|text||
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key:ture|
### Association
- belongs_to :user
- belongs_to :group

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
- has_many :messages
- has_many :users, through: :groups_users
- has_many :groups_users

## groups_users中間テーブル
|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user







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

