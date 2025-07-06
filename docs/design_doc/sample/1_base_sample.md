# 基本設計サンプル

## 機能ID: F001

### 機能名：ユーザー登録機能

### 入力チェック

- 各項目ごとに個別バリデーション
- メールは正規表現 `^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+$`
- パスワードは `英数混在 8文字以上`

### 処理フロー

1. フロントエンドで初期バリデーション
2. サーバーにPOST（JSON）
3. バックエンドで以下を実行：
   - ユーザー情報のバリデーション（`UserValidator`）
   - メール重複チェック（`UserRepository.exists(email)`）
   - パスワードハッシュ化（`PasswordHasher`）
   - ユーザー保存（`UserRepository.save(user)`）
   - レスポンス送信

### シーケンス図

- UserController → UserService → UserRepository
- UserService → PasswordHasher / UserValidator
