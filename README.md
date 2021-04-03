# 目次
1.アプリケーション概要<br>
2.制作背景<br>
3.接続方法<br>
4.実装機能<br>
5.テーブル設計<br>

# 1.アプリケーション概要
  ## 1-1.アプリケーション名
  Travellers
  ## 1-2.概要説明
  自分が実際に行った旅先を投稿形式でレビューできるアプリです。  
  ユーザーを登録すると投稿できるようになります。  
  自身の投稿に対しては、編集と削除をすることができます。  
  他のユーザーの投稿に対してはコメントのみできます。  

# 2.制作背景
  旅先をwebページで探すとき、mapアプリや観光連盟公式サイト等を見ることがある。
  その際に、おすすめや口コミを参照することがあるが、評価や意見をどのような人が記載しているのかわからない。
  また、実際に行った人がどのような評価、感想を持っているのかわからない。

  そこで実際に行った人が投稿した評価のみに絞った、webページを作成をすることにした。

  実際に行った人のみが投稿できるようにするため、写真投稿を必須としました。

# 3.接続方法
  ## 3-1.URL
  https://travellers-34434.herokuapp.com/

  ## 3-2.テスト用アカウント
  テストID：test1@test1<br>
  テストPASS：xxx111111


# 4.実装機能
## 4-1.一覧表示機能（トップページ）
![94cddd0feb6235538e40a40e10300541](https://user-images.githubusercontent.com/78333577/113398645-e5f29a00-93d9-11eb-8229-09e30429eb03.gif)
## 4-2.ユーザー管理機能
### 4-2-1.新規登録
![15b32b5f505abb0ef22516026a9e3fbf](https://user-images.githubusercontent.com/78333577/113399164-b5f7c680-93da-11eb-9c93-4b9bc0eb1260.gif)
### 4-2-2.ログイン
![d2b079b81179c6d87bbaa6d98e594f7b](https://user-images.githubusercontent.com/78333577/113400324-92358000-93dc-11eb-8fbf-24817a8d4ba2.gif)
### 4-2-3.ログアウト
![aede1ea6ca1e7017202a2c6c9aeeb176](https://user-images.githubusercontent.com/78333577/113400451-c90b9600-93dc-11eb-9b7a-2928f81c33c0.gif)
## 4-3.投稿機能
![6590289308f9698afef8a630ee0b2a69](https://user-images.githubusercontent.com/78333577/113465111-85606d00-946c-11eb-8af8-f03b1329f533.gif)
## 4-3.詳細表示
![2bec50278354df2c0e5c9debef00b3fe](https://user-images.githubusercontent.com/78333577/113465210-3e26ac00-946d-11eb-8a32-57278040f59d.gif)
### 4-3-1.投稿編集

### 4-3-2.投稿削除
![8a7fde6c55601d7eee7218b2a32e9d04](https://user-images.githubusercontent.com/78333577/113465251-8e057300-946d-11eb-885a-8af04206cf90.gif)
### 4-3-3.コメント
![18a2840b6b7966eedeab07978eed3744](https://user-images.githubusercontent.com/78333577/113465319-0ff59c00-946e-11eb-8bdd-8d41e787605d.gif)
## 4-4.検索機能


# 実装予定の機能


# テーブル設計
（ER図貼り付け方法が不明）


## users テーブル

| Column             | Type   | Options                   |
| ------------------ | ------ | ------------------------- |
| email              | string | null: false, unique: true |
| encrypted_password | string | null: false               |
| nickname           | string | null: false               |

### Association

- has_many :posts
- has_many :comments

## posts テーブル

| Column  | Type       | Options     |
| ------- | ---------- | ----------- |
| title   | string     | null: false |
| text    | text       | null: false |
| area_id | integer    | null: false |
| score   | integer    | null: false |
| user    | references |             |

### Association

- has_many :comments
- belongs_to :user

## comments テーブル

| Column  | Type       | Options     |
| ------- | ---------- | ----------- |
| text    | text       | null: false |
| user    | references |             |
| post    | references |             |

### Association

- belongs_to :user
- belongs_to :post

# 要件定義（Googleスプレッドシート）
https://docs.google.com/spreadsheets/d/1OKEdCtfZPbojakxj23h31DbT7OkT__Vz9R6gUdOKmLg/edit#gid=0

# 開発環境
- Ruby on Rails
- MySQL
- Github
- AWS
- Visual Studio Code

# 工夫した点
エラーメッセージ日本語化
テキスト表示形式（段落反映）
星評価機能のjsファイルに、コメント記入（読み返してわかりやすくするため）

