# 🚀 クイックスタートガイド

## たった3ステップでアプリを公開！

```
📦 GitHub (倉庫)        →    🌐 Streamlit Cloud (店舗)    →    ✨ 公開完了！
プログラムを保存           Webアプリとして公開             URLで誰でもアクセス
```

---

## ステップ1️⃣: GitHub（倉庫）を準備

### やること
GitHubにプログラムをアップロードする

### 手順
1. **GitHubアカウント作成**
   - https://github.com
   - 無料で作成できます

2. **新しいリポジトリ作成**
   ```
   Repository name: cosmic-guidance
   Public を選択
   ```

3. **ファイルをアップロード**
   - `app_with_rag.py` ← メインプログラム
   - `avatar_rag_data.py` ← データファイル
   - `requirements.txt` ← 必要なライブラリ
   - `README.md` ← 説明書
   - `.gitignore` ← 除外設定

### 所要時間
⏰ 約5分

---

## ステップ2️⃣: Streamlit Cloud（店舗）で公開

### やること
GitHubのコードをWebアプリとして公開

### 手順
1. **Streamlit Cloudにログイン**
   - https://streamlit.io/cloud
   - GitHubアカウントで連携

2. **New app をクリック**
   ```
   Repository: あなたのユーザー名/cosmic-guidance
   Branch: main
   Main file: app_with_rag.py
   ```

3. **Deploy! をクリック**

### 所要時間
⏰ 約2分（デプロイ待機時間含む）

---

## ステップ3️⃣: シークレット（秘密の鍵）を設定

### やること
APIキーなどの秘密情報を設定

### 手順
1. **Settings → Secrets をクリック**

2. **以下を入力**
   ```toml
   GEMINI_API_KEY = "あなたのGemini APIキー"
   SUPABASE_URL = "あなたのSupabase URL"
   SUPABASE_KEY = "あなたのSupabase Key"
   ```

3. **Save をクリック**

### 所要時間
⏰ 約1分

---

## 🎉 完成！

```
https://あなたのアプリ名.streamlit.app
```

このURLで世界中からアクセスできます！

---

## 📝 必要なもの

| 項目 | 取得方法 | 無料/有料 |
|------|---------|----------|
| GitHubアカウント | https://github.com | 🆓 無料 |
| Streamlit Cloudアカウント | https://streamlit.io/cloud | 🆓 無料 |
| Gemini API Key | https://makersuite.google.com/app/apikey | 🆓 無料枠あり |
| Supabase | https://supabase.com | 🆓 無料枠あり |

---

## 🔄 コードを更新したいとき

```
GitHub でファイルを編集
    ↓
自動的にStreamlitが再デプロイ
    ↓
完了！（待つだけ）
```

---

## 💡 よくある質問

### Q: プログラミング経験がなくても大丈夫？
A: はい！このガイド通りに進めれば、コピー＆ペーストだけでOKです。

### Q: お金はかかりますか？
A: 基本的に無料です。ただし、大量のアクセスがある場合は有料プランが必要になることがあります。

### Q: アプリが動かない...
A: DEPLOYMENT.md の「トラブルシューティング」セクションを確認してください。

### Q: セキュリティは大丈夫？
A: APIキーは必ず「Secrets」で設定し、GitHubのコードには書かないでください。

---

## 📚 もっと詳しく知りたい

- **完全なデプロイ手順**: `DEPLOYMENT.md` を参照
- **Streamlit公式ドキュメント**: https://docs.streamlit.io/
- **GitHub使い方**: https://docs.github.com/ja

---

## 🆘 困ったときは

1. エラーメッセージをコピー
2. Streamlit Cloudの「Logs」を確認
3. ChatGPTやClaudeに質問

頑張ってください！ 🚀
