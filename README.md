# AYCC Website

**AYCC - AI YASUDA CREATIVE & CONSULTING**  
愛とAIで、あなたの変革を支援します

---

## 🎯 プロジェクト概要

AYCCのコーポレートサイト。  
Creative(音楽・芸術) × Consulting(IT・AI) の融合を表現したシンプルなウェブサイト。

---

## 📁 ファイル構成

```
aycc-website/
├── index.html              # メインHTML
├── images/
│   └── logo.png           # AYCCロゴ
├── README.md              # このファイル
└── AYCC_Website_Handover.md  # 完全引継ぎ資料
```

---

## 🚀 クイックスタート

### 1. ローカルで確認

```bash
# プロジェクトディレクトリに移動
cd aycc-website

# ブラウザでindex.htmlを開く
open index.html  # Mac
start index.html # Windows
```

### 2. ロゴファイルの配置

```bash
# imagesフォルダ作成
mkdir images

# ロゴファイルをコピー
cp Adobe_Express_-_file.png images/logo.png
```

### 3. GitHubにプッシュ

```bash
# Git初期化
git init
git add .
git commit -m "Initial commit: AYCC website"

# GitHubリポジトリと接続
git remote add origin https://github.com/Toshiki-Yasuda/aycc-website.git
git branch -M main
git push -u origin main
```

### 4. Cloudflare Pagesでデプロイ

1. [Cloudflare Pages](https://pages.cloudflare.com/)にログイン
2. "Create a project" → "Connect to Git"
3. リポジトリ選択: `aycc-website`
4. プロジェクト名: `aycc`
5. Build settings:
   - Framework: None
   - Build command: (空欄)
   - Output directory: `/`
6. "Save and Deploy"

**完成URL**: https://aycc.pages.dev

---

## 🎨 デザインコンセプト

### カラーパレット

```
ピンク系(Creative)  → グラデーション → ブルー系(Consulting)
    #FF69B4       →   #9B59B6    →     #4A90E2
    
    愛(Ai)             融合              としき
  マリンバ           音楽教室          IT/AI
```

### ロゴの意味

```
   A  ♥  CC
   │  │  ││
   │  │  │└── Consulting
   │  │  └─── Creative
   │  └────── ハート(愛・融合)
   └───────── AYCC
```

**トリプルミーニング**:
1. **愛** - 代表・安田愛さん
2. **AI** - 人工知能技術
3. **愛を持って** - 人間味のある支援

---

## 📄 ページ構成

- **ヒーロー**: ロゴ・キャッチコピー・CTA
- **サービス**: Creative | 融合 | Consulting の3カラム
- **実績**: 概要のみ(クライアント名伏せ)
- **会社概要**: 基本情報・代表プロフィール
- **お問い合わせ**: Google Forms(予定)

---

## 🛠️ 技術スタック

- **HTML/CSS/JavaScript** - シンプル構成
- **Tailwind CSS** - スタイリング(CDN)
- **Cloudflare Pages** - ホスティング(無料)
- **Google Forms** - お問い合わせ(予定)

---

## 📝 TODO

- [ ] ロゴファイル配置(`images/logo.png`)
- [ ] 会社情報の最終確認(住所・連絡先)
- [ ] Google Formsの埋め込み
- [ ] GitHubプッシュ
- [ ] Cloudflare Pagesデプロイ
- [ ] 独自ドメイン取得検討

---

## 📚 ドキュメント

詳細な仕様・デザイン・コンテンツは **[AYCC_Website_Handover.md](AYCC_Website_Handover.md)** を参照してください。

---

## 📞 サポート

質問・相談はClaudeまでお気軽に!

---

**2026年1月27日 作成**
