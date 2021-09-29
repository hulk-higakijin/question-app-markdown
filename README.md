# question-app

テーブル設計
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