# AYCCホームページ開発 完全引継ぎ資料

**作成日**: 2026年1月27日  
**プロジェクト**: AYCC コーポレートサイト構築  
**目的**: ローカル環境での開発継続のための完全引継ぎ

---

## 📋 目次

1. [プロジェクト概要](#1-プロジェクト概要)
2. [ブランドコンセプト](#2-ブランドコンセプト)
3. [ロゴの意味と設計思想](#3-ロゴの意味と設計思想)
4. [サイト構成](#4-サイト構成)
5. [技術仕様](#5-技術仕様)
6. [デザイン仕様](#6-デザイン仕様)
7. [コンテンツ詳細](#7-コンテンツ詳細)
8. [開発手順](#8-開発手順)
9. [参考資料](#9-参考資料)

---

## 1. プロジェクト概要

### 1.1 プロジェクト名
**AYCC コーポレートサイト**

### 1.2 目的
- AYCCの事業内容を明確に伝える
- Creative × Consulting の融合を視覚的に表現
- 問い合わせ導線の確保
- 実績の簡潔な紹介
- 副業規定に配慮した情報開示

### 1.3 制約事項
- **としきさんの情報**: 実名・顔写真非掲載(副業規定への配慮)
- **所属表記**: 「所属コンサルタント・エンジニア」として匿名表記
- **実績**: クライアント名を伏せた概要のみ
- **予算**: 自社サイトのため初期は無料構成でスタート

### 1.4 公開目標
- **MVP公開**: 2月上旬
- **ドメイン**: まずは `aycc.pages.dev` でスタート
- **将来**: `aycc.jp` または `aycc.co.jp` への移行検討

---

## 2. ブランドコンセプト

### 2.1 企業理念
**「愛とAIで、あなたの変革を支援します」**

#### トリプルミーニング
1. **愛(あい)** - 代表・安田愛さんの名前
2. **AI** - Claude含む様々なAI技術の活用
3. **愛を持って** - 人間味のある伴走支援

### 2.2 事業の本質

```
┌────────────────────────────────┐
│                                │
│   Creative  ←→  Consulting     │
│     (愛)          (としき)      │
│                                │
│   ♥ 愛と AI で ♥               │
│                                │
│  あなたの変革を支援します        │
│                                │
└────────────────────────────────┘
```

### 2.3 事業領域の関係性

```
Creative領域 ──┐
(Aiさん中心)   │
               ├── 融合領域 ─→ 音楽教室向けサービス
               │   (両者の強みを統合)
Consulting領域 ┘
(としきさん中心)
```

**融合の意味**:
- Creative(マリンバ教室運営の実務知識) + Consulting(IT/システム開発)
- → 音楽教室向けWEB/予約管理システム
- この融合こそがAYCCの独自性

---

## 3. ロゴの意味と設計思想

### 3.1 ロゴファイル
- **ファイル名**: `Adobe_Express_-_file.png`
- **配置**: `/mnt/user-data/uploads/`
- **使用場所**: ヘッダー、ファビコン

### 3.2 ロゴの構造

```
   A  ♥  CC
   │  │  ││
   │  │  │└── Consulting (右のC)
   │  │  └─── Creative (左のC)
   │  └────── ハート(愛の象徴・2つのCの重なり)
   └───────── AYCC全体

【重要】2つのCが重なる部分 = 融合領域(音楽教室向けサービス)
```

### 3.3 色の意味

```
ピンク系(左) → グラデーション(中) → ブルー系(右)
    ↓              ↓                ↓
 愛(Aiさん)    融合・調和      としきさん
 Creative     音楽教室向け    Consulting
  温かさ      サービス         論理性
   感性                       技術力
```

### 3.4 カラーコード

```css
/* メインカラー */
--primary-pink: #FF69B4;    /* 愛・Creative */
--primary-blue: #4A90E2;    /* としき・Consulting */

/* アクセントカラー */
--accent-purple: #9B59B6;   /* 融合部分 */
--light-pink: #FFE4F0;      /* 背景・淡いピンク */
--light-blue: #E3F2FD;      /* 背景・淡いブルー */

/* グレースケール */
--dark-gray: #2D3748;       /* テキスト */
--medium-gray: #718096;     /* 補助テキスト */
--light-gray: #F7FAFC;      /* 背景 */
--border-gray: #E2E8F0;     /* ボーダー */
```

---

## 4. サイト構成

### 4.1 ページ構成(Phase 1: MVP)

```
AYCC Website
│
├── index.html (トップページ)
│   ├── ヘッダー(ロゴ・ナビゲーション)
│   ├── ヒーローセクション
│   ├── 事業内容(3カラム)
│   ├── 会社概要
│   ├── 実績紹介(簡易)
│   ├── お問い合わせ
│   └── フッター
│
└── (将来拡張)
    ├── services.html (サービス詳細)
    ├── about.html (代表プロフィール)
    └── contact.html (お問い合わせ専用)
```

### 4.2 セクション構成詳細

#### 4.2.1 ヘッダー
```
┌────────────────────────────────────────┐
│ [AYCC ロゴ]           [ホーム] [お問い合わせ] │
└────────────────────────────────────────┘
```

#### 4.2.2 ヒーローセクション
```
┌────────────────────────────────────────┐
│                                        │
│        [大きなAYCCロゴ]                 │
│                                        │
│   -AI YASUDA CREATIVE & CONSULTING-    │
│                                        │
│   愛とAIで、あなたの変革を支援します      │
│                                        │
│        [お問い合わせボタン]              │
│                                        │
└────────────────────────────────────────┘
```

#### 4.2.3 事業内容(3カラム)

```
┌──────────────┬──────────────┬──────────────┐
│              │              │              │
│  Creative    │   融合領域    │  Consulting  │
│  (ピンク系)   │ (グラデ)      │  (ブルー系)   │
│              │              │              │
├──────────────┼──────────────┼──────────────┤
│              │              │              │
│ 🎵 マリンバ  │ 🎹 音楽教室   │ 💼 IT/AI     │
│   演奏活動   │   向け       │   コンサル   │
│              │ WEB/予約管理 │              │
│ 🏫 マリンバ  │              │ 🌐 WEB制作   │
│   教室       │              │              │
│              │              │ 📱 アプリ    │
│ 🎼 貸し      │              │   開発       │
│   スタジオ   │              │              │
│              │              │ 🖥️ PC出張   │
│              │              │   サポート   │
│              │              │              │
└──────────────┴──────────────┴──────────────┘
```

**レスポンシブ(スマホ)**:
```
┌──────────────┐
│  Creative    │
│  (ピンク系)   │
├──────────────┤
│   融合領域    │
│ (グラデ)      │
├──────────────┤
│  Consulting  │
│  (ブルー系)   │
└──────────────┘
```

#### 4.2.4 会社概要
```
社名: AYCC - AI YASUDA CREATIVE & CONSULTING -
代表: 安田 愛(やすだ あい)
所在地: 札幌市豊平区
TEL: (仮)011-XXX-XXXX
Email: (仮)info@aycc.jp

【体制】
所属コンサルタント・エンジニア
- AI導入コンサルティング
- システム開発・インフラ構築
- 企業経験20年以上
```

#### 4.2.5 実績紹介(概要のみ)
```
【ウェブサイト制作実績】
✓ イベント運営会社様 - コーポレートサイト構築
✓ 音楽教室様 - 予約管理システム統合サイト開発
✓ 文化事業様 - イベント告知サイト制作

【AIコンサルティング実績】
✓ 地方自治体様 - AI活用戦略策定支援
✓ 中小企業様 - 業務効率化AI導入支援
```

---

## 5. 技術仕様

### 5.1 推奨技術スタック

#### パターンA: 超シンプル(推奨)
```
【フロントエンド】
- Pure HTML/CSS/JavaScript
- Tailwind CSS (CDN経由)
- レスポンシブ対応

【ホスティング】
- Cloudflare Pages (無料)
- URL: aycc.pages.dev

【お問い合わせ】
- Google Forms 埋め込み
- または Formspree (無料)

【費用】
完全無料
```

#### パターンB: モダン構成
```
【フロントエンド】
- Next.js 14 (App Router)
- TypeScript
- Tailwind CSS

【ホスティング】
- Vercel (無料プラン)

【お問い合わせ】
- Vercel Forms
- または外部サービス

【費用】
基本無料(独自ドメインは別途)
```

### 5.2 推奨: パターンA (理由)

1. **シンプル** - 管理が容易
2. **高速** - 静的サイトで超高速表示
3. **無料** - 完全無料で運用可能
4. **保守性** - HTMLファイル1つで完結
5. **拡張性** - 将来Next.jsに移行も可能

---

## 6. デザイン仕様

### 6.1 全体デザインコンセプト
- **キーワード**: シンプル、洗練、親しみやすさ、信頼感
- **スタイル**: ミニマル × グラデーション
- **レイアウト**: 余白を活かした見やすさ重視

### 6.2 カラーシステム

```css
:root {
  /* プライマリカラー */
  --primary-pink: #FF69B4;
  --primary-blue: #4A90E2;
  --accent-purple: #9B59B6;
  
  /* 背景カラー */
  --bg-white: #FFFFFF;
  --bg-light-pink: #FFF5F9;
  --bg-light-blue: #F0F7FF;
  --bg-gray: #F7FAFC;
  
  /* テキストカラー */
  --text-dark: #2D3748;
  --text-medium: #4A5568;
  --text-light: #718096;
  
  /* ボーダー */
  --border-light: #E2E8F0;
  --border-medium: #CBD5E0;
  
  /* グラデーション */
  --gradient-main: linear-gradient(135deg, #FF69B4 0%, #9B59B6 50%, #4A90E2 100%);
  --gradient-creative: linear-gradient(135deg, #FF69B4 0%, #FFB6D9 100%);
  --gradient-consulting: linear-gradient(135deg, #4A90E2 0%, #7BB3E8 100%);
}
```

### 6.3 タイポグラフィ

```css
/* フォントファミリー */
font-family: -apple-system, BlinkMacSystemFont, 
             "Segoe UI", "Hiragino Sans", 
             "Hiragino Kaku Gothic ProN", "Yu Gothic", 
             "Meiryo", sans-serif;

/* フォントサイズ */
--font-xs: 0.75rem;   /* 12px */
--font-sm: 0.875rem;  /* 14px */
--font-base: 1rem;    /* 16px */
--font-lg: 1.125rem;  /* 18px */
--font-xl: 1.25rem;   /* 20px */
--font-2xl: 1.5rem;   /* 24px */
--font-3xl: 1.875rem; /* 30px */
--font-4xl: 2.25rem;  /* 36px */
--font-5xl: 3rem;     /* 48px */

/* 行の高さ */
--leading-tight: 1.25;
--leading-normal: 1.5;
--leading-relaxed: 1.75;
```

### 6.4 スペーシング

```css
/* マージン・パディング */
--space-1: 0.25rem;  /* 4px */
--space-2: 0.5rem;   /* 8px */
--space-3: 0.75rem;  /* 12px */
--space-4: 1rem;     /* 16px */
--space-6: 1.5rem;   /* 24px */
--space-8: 2rem;     /* 32px */
--space-12: 3rem;    /* 48px */
--space-16: 4rem;    /* 64px */
--space-24: 6rem;    /* 96px */
```

### 6.5 ブレークポイント

```css
/* レスポンシブ */
--breakpoint-sm: 640px;   /* スマホ横 */
--breakpoint-md: 768px;   /* タブレット */
--breakpoint-lg: 1024px;  /* デスクトップ */
--breakpoint-xl: 1280px;  /* 大画面 */
```

---

## 7. コンテンツ詳細

### 7.1 ヘッダー

```html
<header>
  <nav>
    <div class="logo">
      <img src="logo.png" alt="AYCC">
    </div>
    <div class="nav-links">
      <a href="#home">ホーム</a>
      <a href="#services">サービス</a>
      <a href="#about">会社概要</a>
      <a href="#contact">お問い合わせ</a>
    </div>
  </nav>
</header>
```

**コンテンツ**:
- ロゴ画像
- ナビゲーションリンク
- スマホではハンバーガーメニュー

### 7.2 ヒーローセクション

**コピー**:
```
メインビジュアル: AYCCロゴ大

-AI YASUDA CREATIVE & CONSULTING-

愛とAIで、あなたの変革を支援します

[お問い合わせはこちら]
```

**背景**: 白 または 薄いグラデーション

### 7.3 事業内容セクション

#### Creative (左カラム)

**見出し**: Creative

**アイコン + テキスト**:
```
🎵 マリンバ演奏活動
プロマリンバ奏者による演奏活動。コンサート・イベント出演など幅広く対応いたします。

🏫 マリンバ教室
初心者から経験者まで、楽しく学べるマリンバ教室を運営しています。

🎼 貸しスタジオ
マリンバ練習用のスタジオレンタルサービスを提供しています。
```

#### 融合領域 (中央カラム)

**見出し**: Creative × Consulting

**アイコン + テキスト**:
```
🎹 音楽教室向けWEB/予約管理システム

音楽教室運営の実務経験とIT技術を融合させた、
使いやすい予約管理システムを開発・提供します。

- 生徒管理
- レッスン予約
- 振替対応
- 保護者連絡
- 月謝管理

月額0円で維持できる最新システムです。
```

#### Consulting (右カラム)

**見出し**: Consulting

**アイコン + テキスト**:
```
💼 IT/AIコンサルティング
企業・自治体のAI活用戦略策定から導入まで、伴走支援いたします。

🌐 WEB制作
月額0円で維持できるウェブサイトを制作します。最新技術で高速・安全なサイトを実現。

📱 アプリケーション開発
業務効率化のためのWebアプリケーション開発を行います。

🖥️ PC出張サポート
個人向けのパソコン設定・トラブル対応を出張サポートします。
```

### 7.4 会社概要セクション

```
【会社情報】
社名: AYCC - AI YASUDA CREATIVE & CONSULTING -
代表: 安田 愛(やすだ あい)
所在地: 〒XXX-XXXX 札幌市豊平区
TEL: 011-XXX-XXXX (仮)
Email: info@aycc.jp (仮)
設立: 20XX年X月

【代表プロフィール】
安田 愛(やすだ あい)
- マリンバ演奏家
- リズム指導講師
- 音楽教室運営

【所属コンサルタント・エンジニア】
- AI導入コンサルティング
- システム開発・インフラ構築
- Webアプリケーション開発
- 企業経験20年以上
```

### 7.5 実績紹介セクション

```
【実績紹介】

■ ウェブサイト制作
・イベント運営会社様
  コーポレートサイト構築(2026年1月)
  
・音楽教室様
  予約管理システム統合サイト開発(2026年1月)
  
・文化事業様
  イベント告知サイト制作(2025年12月)

■ AIコンサルティング
・地方自治体様
  AI活用戦略策定支援(2025年)
  
・中小企業様
  業務効率化AI導入支援(2025年)
```

### 7.6 お問い合わせセクション

```
【お問い合わせ】

お気軽にご相談ください

Google Formまたは以下の情報をご記入ください:

- お名前
- メールアドレス
- お問い合わせ内容

[送信ボタン]
```

### 7.7 フッター

```
© 2026 AYCC - AI YASUDA CREATIVE & CONSULTING
All rights reserved.

Privacy Policy | Terms of Service
```

---

## 8. 開発手順

### 8.1 環境構築

#### ステップ1: プロジェクト作成

```bash
# ディレクトリ作成
mkdir aycc-website
cd aycc-website

# 基本ファイル作成
touch index.html
touch styles.css
touch script.js
mkdir images
```

#### ステップ2: ロゴ配置

```bash
# ロゴファイルをimagesフォルダに配置
cp Adobe_Express_-_file.png images/logo.png
```

#### ステップ3: Git初期化

```bash
git init
git add .
git commit -m "Initial commit: AYCC website setup"
```

### 8.2 HTML構造(index.html)

```html
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="AYCC - 愛とAIで、あなたの変革を支援します。音楽教室運営とIT技術を融合させた新しいサービスを提供。">
    <title>AYCC - AI YASUDA CREATIVE & CONSULTING</title>
    
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Custom CSS -->
    <link rel="stylesheet" href="styles.css">
    
    <!-- ファビコン -->
    <link rel="icon" href="images/logo.png">
</head>
<body>
    <!-- ヘッダー -->
    <header>
        <!-- ナビゲーション -->
    </header>
    
    <!-- ヒーローセクション -->
    <section id="hero">
        <!-- メインビジュアル -->
    </section>
    
    <!-- 事業内容セクション -->
    <section id="services">
        <!-- 3カラムレイアウト -->
    </section>
    
    <!-- 会社概要セクション -->
    <section id="about">
        <!-- 会社情報 -->
    </section>
    
    <!-- 実績紹介セクション -->
    <section id="works">
        <!-- 実績一覧 -->
    </section>
    
    <!-- お問い合わせセクション -->
    <section id="contact">
        <!-- お問い合わせフォーム -->
    </section>
    
    <!-- フッター -->
    <footer>
        <!-- コピーライト -->
    </footer>
    
    <!-- JavaScript -->
    <script src="script.js"></script>
</body>
</html>
```

### 8.3 CSS設計(styles.css)

```css
/* ===== CSS変数 ===== */
:root {
    /* カラーパレット */
    --primary-pink: #FF69B4;
    --primary-blue: #4A90E2;
    --accent-purple: #9B59B6;
    
    /* 背景 */
    --bg-white: #FFFFFF;
    --bg-light: #F7FAFC;
    
    /* テキスト */
    --text-dark: #2D3748;
    --text-medium: #4A5568;
    
    /* グラデーション */
    --gradient-main: linear-gradient(135deg, #FF69B4 0%, #9B59B6 50%, #4A90E2 100%);
}

/* ===== リセット ===== */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    color: var(--text-dark);
    line-height: 1.6;
}

/* ===== レイアウト ===== */
.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
}

/* ===== 3カラムレイアウト ===== */
.three-column {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 40px;
}

/* レスポンシブ */
@media (max-width: 768px) {
    .three-column {
        grid-template-columns: 1fr;
    }
}
```

### 8.4 JavaScript(script.js)

```javascript
// スムーススクロール
document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', function (e) {
        e.preventDefault();
        const target = document.querySelector(this.getAttribute('href'));
        target.scrollIntoView({ behavior: 'smooth' });
    });
});

// ハンバーガーメニュー(モバイル)
const menuToggle = document.querySelector('.menu-toggle');
const navLinks = document.querySelector('.nav-links');

menuToggle?.addEventListener('click', () => {
    navLinks.classList.toggle('active');
});
```

### 8.5 Cloudflare Pages デプロイ

#### ステップ1: GitHubにプッシュ

```bash
# GitHubでリポジトリ作成後
git remote add origin https://github.com/Toshiki-Yasuda/aycc-website.git
git branch -M main
git push -u origin main
```

#### ステップ2: Cloudflare Pagesで設定

1. Cloudflare Pagesにログイン
2. "Create a project" → "Connect to Git"
3. GitHubリポジトリ選択: `aycc-website`
4. プロジェクト名: `aycc`
5. Build settings:
   - Framework preset: None (静的サイト)
   - Build command: (空欄)
   - Build output directory: `/` (ルート)
6. "Save and Deploy"

#### 完成URL
```
https://aycc.pages.dev
```

---

## 9. 参考資料

### 9.1 既存プロジェクト

#### Office Lineup案件
- **案件内容**: イベントスタッフ会社のコーポレートサイト
- **特徴**: 
  - プロフェッショナル・モダンスタイル
  - 白基調、大きな写真
  - 実績重視の構成
- **料金**: 125,000円(ロゴ・写真編集含む)

#### ピアノ教室案件
- **案件内容**: 予約管理統合システム
- **URL**: https://piano-school-two.vercel.app/
- **技術**: Next.js + Supabase + Vercel
- **特徴**: 
  - カレンダー予約システム
  - 管理画面完備
  - レスポンシブ対応

#### マリンバコンサート
- **URL**: https://marimba-yui.pages.dev/
- **ホスティング**: Cloudflare Pages
- **特徴**: 
  - イベント告知特化
  - お子様連れ歓迎の温かいデザイン
  - 完全無料構成

### 9.2 デザイン参考サイト

**コンサルティング系**:
- シンプル、洗練
- 余白を活かしたレイアウト
- 信頼感のある配色

**クリエイティブ系**:
- ビジュアル重視
- 柔らかい印象
- 温かみのある配色

**融合イメージ**:
- 両方の要素を取り入れる
- グラデーションで統一感

### 9.3 ツール・リソース

#### 画像編集
- **Photopea**: https://www.photopea.com/
- 無料のオンライン画像編集ツール

#### アイコン
- **Font Awesome**: https://fontawesome.com/
- **Google Fonts Icons**: https://fonts.google.com/icons
- 絵文字: 🎵🏫🎼💼🌐📱🖥️🎹

#### カラーパレット
- **Coolors**: https://coolors.co/
- グラデーション生成ツール

#### フォント
- **Google Fonts**: https://fonts.google.com/
- 推奨: Noto Sans JP, M PLUS Rounded 1c

---

## 10. チェックリスト

### デザイン
- [ ] ロゴの配置とサイズ確認
- [ ] 3カラムレイアウトの実装
- [ ] グラデーションの適用
- [ ] レスポンシブ対応(スマホ・タブレット)
- [ ] フォントサイズ・行間の調整

### コンテンツ
- [ ] 会社情報の正確性確認
- [ ] 実績の表現方法確認
- [ ] としきさん情報の匿名化確認
- [ ] キャッチコピーの最終確認

### 機能
- [ ] スムーススクロール動作確認
- [ ] ハンバーガーメニュー(モバイル)
- [ ] お問い合わせフォームの動作
- [ ] 各リンクの動作確認

### SEO・アクセシビリティ
- [ ] metaタグ設定
- [ ] alt属性の設定
- [ ] ページ速度の確認
- [ ] コントラスト比の確認

### デプロイ
- [ ] GitHubへのプッシュ
- [ ] Cloudflare Pagesでの設定
- [ ] デプロイ成功確認
- [ ] 本番URL動作確認

---

## 11. 今後の拡張予定

### Phase 2 (2月中旬〜)
- [ ] 独自ドメイン取得(`aycc.jp` または `aycc.co.jp`)
- [ ] ブログ機能追加(microCMS連携)
- [ ] サービス詳細ページ追加
- [ ] 代表プロフィールページ追加

### Phase 3 (3月〜)
- [ ] お客様の声セクション追加
- [ ] ポートフォリオギャラリー
- [ ] 多言語対応(英語)
- [ ] アクセス解析導入(Google Analytics)

### Phase 4 (将来)
- [ ] オンライン予約システム統合
- [ ] 会員ログイン機能
- [ ] CMS導入(コンテンツ管理)
- [ ] SEO最適化

---

## 12. 連絡先・サポート

### プロジェクト管理
- **GitHub**: https://github.com/Toshiki-Yasuda/aycc-website
- **Cloudflare Pages**: https://aycc.pages.dev

### 質問・相談
- Claude(このAI)にいつでも相談可能
- 過去のチャット履歴も参照可能

---

**このドキュメントは随時更新してください**

最終更新: 2026年1月27日
