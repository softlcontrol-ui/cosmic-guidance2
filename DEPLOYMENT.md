# デプロイ手順ガイド

## 📦 ステップ1: GitHubに保存（倉庫を作る）

### 1-1. GitHubアカウントを作成
- https://github.com にアクセス
- 「Sign up」をクリックして無料アカウントを作成

### 1-2. 新しいリポジトリを作成
1. GitHubにログイン後、右上の「+」→「New repository」をクリック
2. 以下を入力：
   - **Repository name**: `cosmic-guidance`（または好きな名前）
   - **Description**: `AIによる運命ガイドアプリ`
   - **Public** を選択（無料でデプロイするため）
   - **Add a README file** にチェック
3. 「Create repository」をクリック

### 1-3. ファイルをアップロード
#### 方法A: Web UIから直接アップロード（初心者向け）
1. リポジトリページで「Add file」→「Upload files」をクリック
2. 以下のファイルをドラッグ&ドロップ：
   - `app_with_rag.py`
   - `avatar_rag_data.py`
   - `requirements.txt`
   - `README.md`
   - `.gitignore`
   - `.streamlit/secrets.toml.example`
3. 「Commit changes」をクリック

#### 方法B: Git Bashを使う（推奨）
```bash
# リポジトリをクローン
git clone https://github.com/あなたのユーザー名/cosmic-guidance.git
cd cosmic-guidance

# ファイルをコピー
# （app_with_rag.pyなどをこのフォルダにコピーする）

# Gitに追加
git add .
git commit -m "Initial commit: THE PLAYER app"
git push origin main
```

---

## 🌐 ステップ2: Streamlit Community Cloudでデプロイ（店舗を開く）

### 2-1. Streamlit Community Cloudアカウントを作成
1. https://streamlit.io/cloud にアクセス
2. 「Sign up」をクリック
3. **GitHubアカウントでログイン**（重要！）
4. Streamlit Cloudに必要な権限を許可

### 2-2. アプリをデプロイ
1. ダッシュボードで「New app」をクリック
2. 以下を設定：
   - **Repository**: `あなたのユーザー名/cosmic-guidance`
   - **Branch**: `main`
   - **Main file path**: `app_with_rag.py`
3. 「Deploy!」をクリック

### 2-3. シークレット（環境変数）を設定
1. デプロイ中またはデプロイ後、「Settings」→「Secrets」をクリック
2. 以下のように入力：

```toml
GEMINI_API_KEY = "あなたのGemini APIキー"
SUPABASE_URL = "あなたのSupabase URL"
SUPABASE_KEY = "あなたのSupabase Anon Key"
```

3. 「Save」をクリック

### 2-4. 完了！
- 数分待つとアプリが起動します
- URLは `https://あなたのアプリ名.streamlit.app` のようになります

---

## 🔄 更新方法（コードを修正したとき）

### GitHubのファイルを更新
1. GitHubのリポジトリページでファイルをクリック
2. 鉛筆アイコン（Edit）をクリック
3. コードを編集
4. 「Commit changes」をクリック

### Streamlit Cloudが自動更新
- GitHubにpushすると、Streamlit Cloudが**自動的に**再デプロイします
- 待つだけでOK！

---

## 🔑 必要なAPIキーの取得方法

### Gemini API Key
1. https://makersuite.google.com/app/apikey にアクセス
2. Googleアカウントでログイン
3. 「Create API key」をクリック
4. 生成されたキーをコピー

### Supabase
1. https://supabase.com にアクセス
2. 「Start your project」でプロジェクトを作成
3. Project Settings → API で以下を取得：
   - **URL**: `Project URL`
   - **Key**: `anon public`キー

---

## ⚠️ 注意事項

1. **secrets.toml はGitHubにアップロードしない**
   - `.gitignore`に含まれているため自動的に除外されます
   - Streamlit Cloudの設定画面で直接設定します

2. **APIキーは公開しない**
   - GitHubのコードにAPIキーを直接書かないこと
   - 必ずsecretsまたは環境変数を使用すること

3. **無料枠の制限**
   - Streamlit Community Cloudは無料で使えますが、リソース制限があります
   - 大量アクセスがある場合は有料プランを検討

---

## 🆘 トラブルシューティング

### アプリが起動しない
- Logsを確認して、エラーメッセージを読む
- requirements.txtのバージョンを確認
- Secretsが正しく設定されているか確認

### 「ModuleNotFoundError」が出る
- requirements.txtに必要なパッケージが含まれているか確認
- requirements.txtがGitHubにアップロードされているか確認

### データベースに接続できない
- Supabase URLとKeyが正しいか確認
- Supabaseのプロジェクトが有効か確認

---

## 📚 参考リンク

- [Streamlit Documentation](https://docs.streamlit.io/)
- [Streamlit Community Cloud](https://streamlit.io/cloud)
- [GitHub Documentation](https://docs.github.com/)
- [Supabase Documentation](https://supabase.com/docs)
