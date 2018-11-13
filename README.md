#README

##Tweeetsテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|foreign_key: true|
|text|string||
|image|integer||
|group_id|integer|foreign_key: true|
|timestamps|integer|

##Usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|vVARCHAR(25)|null: false, unique: true|
|Email|VARCHAR(25)|null: false, unique: true|
|password|VARCHAR(25)|null: false, foreign_key: true|
|timestamps|integer|

##Group_Usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|index: true, foreign_key: true|
|group_id|integer|index: true, foreign_key: true|
|timestamps|integer|

##Groupテーブル
|Column|Type|Options|
|------|----|-------|
|group_id|integer|index: true, foreign_key: true|
|group_name|integer|index: true, foreign_key: true|
|timestamps|integer|


##Association(Tweets)
・belongs_to :Users
・belongs_to :group

##Association(Users)
・has_many:Tweets
・has_many:Group_users
・has_many :Group, through: :Group_users

##Association(Group_Users)
・belongs_to :Users
・belongs_to :group

##Association(Group)
・has_many:Tweets
・has_many:Users
・has_many :Users, through: :Group_users

