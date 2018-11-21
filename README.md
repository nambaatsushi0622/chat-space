#README
## Messagesテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|references|foreign_key: true|
|text|string||
|image|string||
|group_id|references|foreign_key: true|


## Usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|VARCHAR(25)|index: true,null: false, unique: true|
|Email|VARCHAR(25)|null: false, unique: true|


## Group_Usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|references|index: true, foreign_key: true|
|group_id|references|index: true, foreign_key: true|


## Groupsテーブル
|Column|Type|Options|
|------|----|-------|
|group_id|integer|index: true|
|name|integer|index: true|



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


