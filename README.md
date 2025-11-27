# THE PLAYER - 運命の攻略

AIによる運命ガイドアプリ

## 概要

THE PLAYERは、AI（Google Gemini）を使用した占いアプリケーションです。
13種類のアバターシステムとゲーミフィケーション要素を組み合わせ、
ユーザーの人生をRPGのように捉えながら運命のガイダンスを提供します。

## 機能

- 🎮 13種類のアバター（ジョブ）システム
- 📊 経験値とレベルアップシステム
- 🎯 デイリークエストとボーナス報酬
- 🔮 AI（Google Gemini）による運命ガイダンス
- 💾 Supabaseによるユーザーデータ管理

## 技術スタック

- **フロントエンド**: Streamlit
- **AI**: Google Gemini API
- **データベース**: Supabase
- **言語**: Python 3.9+

## セットアップ

### 必要な環境変数

Streamlit Community Cloudの設定で以下のシークレットを設定してください：

```toml
GEMINI_API_KEY = "your-gemini-api-key"
SUPABASE_URL = "your-supabase-url"
SUPABASE_KEY = "your-supabase-key"
```

## ライセンス

MIT License
