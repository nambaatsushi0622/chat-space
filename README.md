#README
## Messagesテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|foreign_key: true|
|text|string||
|image|string||
|group_id|integer|foreign_key: true|


## Usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|VARCHAR(25)|index: true,null: false, unique: true|
|Email|VARCHAR(25)|null: false, unique: true|
|password|VARCHAR(25)|null: false|


## Group_Usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|index: true, foreign_key: true|
|group_id|integer|index: true, foreign_key: true|


## Groupsテーブル
|Column|Type|Options|
|------|----|-------|
|group_id|integer|index: true, foreign_key: true|
|group_name|integer|index: true|



## Association(Messages)
- belongs_to :User
- belongs_to :group

## Association(Users)
- has_many:Messages
- has_many:Group_users
- has_many :Groups, through: :Group_users

## Association(Group_Users)
- belongs_to :User
- belongs_to :group

## Association(Group)
- has_many:Messages
- has_many:Users
- has_many :Users, through: :Group_users

