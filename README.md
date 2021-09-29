# question-app

## テーブル設計
| users |
|:-----------|
| id: integer |
| image_id: integer |
| name: string |
| email: string |
| password: string |
| password_confirm: string |
| admin (T/F): boolean(default: False) |
| created_at: datetime |
| updated_at: datetime |

| posts |
|:-----------|
| id: integer |
| user_id: integer |
| title: string |
| body: text |
| solved (T/F): boolean(default: False) |
| created_at: datetime |
| updated_at: datetime |

| comments |
|:-----------|
| id: integer |
| post_id: integer |
| user_id: integer |
| body: text |
| created_at: datetime |
| updated_at: datetime |

## エンドポイント・コントローラ設計

| やりたいこと               | HTTPメソッド | エンドポイント | コントローラー#アクション |
|:-----------                |:-----------  |:-----------    |:---------------|
| ユーザー登録画面を表示する |	GET        	|'/users/new'    |	users#new     |
| ユーザー登録をする	       | POST         | '/users' 		   | users#create   |
| ログイン画面を表示する		 | GET	        | '/login'       | sessions#new   |
| ログインする               | POST         |'/login'        | sessions#create|
|質問一覧を表示する（全て）	 | GET          |'/posts'        | posts#index    |
|質問一覧を表示する（未解決）| GET          |'/posts/solving'| posts#solving  |			
|質問一覧を表示する（解決済み）|GET         |'/posts/solved' | posts#solved   |			
|質問投稿ページを表示する		 | GET          |'/posts/new'    | posts#new      |	
|質問投稿をする			         | POST         | '/posts'       | posts#create   |
|質問詳細を表示する			     |GET           | '/posts/:id'   | posts#show     |
|質問編集ページを表示する    |GET        | '/posts/:id/edit' | posts#edit     |			
|質問を削除する              |DELETE        | '/posts/:id'    | posts#destroy  |			
|回答する			               |POST          | '/posts/:id/answers'| answers#create|
|ユーザー一覧を表示する			 |GET           | '/users'       | users#index    |
|管理画面用のログインページを表示する|GET   | '/admin/users' | admin/users#new|			
|（管理画面）質問一覧ページを表示する|GET   | '/admin/posts' | admin/posts#index| 			
|（管理画面）質問を削除する	 |DELETE        | '/admin/posts:id'| admin/posts#destroy|	
|（管理画面）ユーザー一覧ページを表示する|GET| '/admin/users' | admin/users#index|		
|（管理画面）ユーザーを削除する	| DELETE    | '/admin/users/:id'| admin/users#destroy|