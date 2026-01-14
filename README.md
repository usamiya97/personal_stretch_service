# 🧘‍♂️ Stretch Trainer Platform
> 友人のパーソナルストレッチトレーナー独立支援のための、LPサイト・顧客管理システム

## 📖 プロジェクト概要
友人がストレッチトレーナーとして独立するにあたり、「新規顧客の獲得」と「既存顧客の管理」が課題となっていました。
これらを低コストかつ効率的に解決するため、**集客用LP**と**顧客管理システム**を設計・開発しました。

### 解決した課題
1. **集客:** ターゲット層に響くデザインとSEOを意識したLPによる認知拡大。
2. **予約・管理:** LINEやDMでの煩雑なやり取りを減らすための顧客一元管理。

---

## 🏗 システム構成・リポジトリ
本プロジェクトは、フロントエンド（LP）とバックエンド（管理システム）の2つのリポジトリで構成されています。

| サービス名 | 役割 | リポジトリURL | 技術スタック |
| --- | --- | --- | --- |
| **集客用LP** | 一般ユーザー向けWebサイト<br>トレーナー紹介、予約導線 | [🔗 GitHub Link](https://github.com/usatai/personal_stretch) | TypeScript, Next.js, Vercel, TailwindCSS |
| **顧客管理システム** | トレーナー専用管理画面<br>顧客情報、予約状況の管理 | [🔗 GitHub Link（フロントエンド）](https://github.com/usatai/personal_stretch_management_system) 
[🔗 GitHub Link（バックエンド）](https://github.com/usatai/personal_stretch_backend) | TypeScript, Next.js, Java, Spring Boot, AWS (EC2/RDS) |

---

## 🛠 技術選定の理由

### 1. 集客用LP (Frontend)
* **Next.js (App Router):** SEO対策とページ表示速度のパフォーマンスを最大化するため採用。
* **Vercel:** デプロイの手軽さと、Next.jsとの親和性の高さから選定。

### 2. 顧客管理システム (Backend / Infra)
* **Java (Spring Boot):** 堅牢な型安全性と、将来的な機能拡張（決済機能など）を見据えた保守性を重視。
* **AWS:** インフラ構築の学習および、スケーラビリティを考慮して選定。

---

## 📐 アーキテクチャ / 設計
*(もし可能であれば、ここにdraw.ioなどで作成した構成図の画像を貼ると非常に評価が高いです)*

### データフロー
1. ユーザーが **LP** から問い合わせ/予約
2. データが **API** を通じて管理システムへ送信
3. トレーナーが **管理画面** で予約を確認・ステータス更新

---

## 🚀 今後の展望 (Roadmap)
* LINE公式アカウントとのAPI連携（予約通知の自動化）
* オンライン決済機能（Stripe）の導入
* 売上分析ダッシュボードの実装

---

## 👤 Author
* **Name:** [あなたの名前/ハンドルネーム]
* **Role:** Full Stack Developer
* **Contact:** [Twitterやメールなど]
