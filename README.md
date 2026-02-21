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
| **顧客管理システム** | トレーナー専用管理画面<br>顧客情報、予約状況の管理 | [🔗 GitHub Link（フロントエンド）](https://github.com/usatai/personal_stretch_management_system)<br>[🔗 GitHub Link（バックエンド）](https://github.com/usatai/personal_stretch_backend) | TypeScript, Next.js, Java, Spring Boot, AWS (EC2), Supabase |

---

## 🛠 技術選定の理由

### 1. 集客用LP (Frontend)
* **Next.js (App Router):** SEO対策とページ表示速度のパフォーマンスを最大化、Vercelへのデプロイパイプラインの容易さ、Reactのエコシステム（Tailwind CSS等）との親和性の観点から採用。
* **Vercel:** デプロイの手軽さと、Next.jsとの親和性の高さから選定。

### 2. 顧客管理システム (Backend / Infra)
* **Java (Spring Boot):** 堅牢なトランザクション管理が求められる顧客・予約管理ドメインにおいて、静的型付け言語とSpring Security等のエコシステムによる高い信頼性を担保するため。また、自身のコアスキルを活用することで、初期リリースまでのタイムトゥマーケット（開発速度）を最速化できると判断しました。
* **AWS:** 将来的なユーザー増を見据えたスケーラビリティの確保と、グローバルスタンダードなIaaS環境でのベストプラクティス（VPC分割、ALB等の活用）を設計に落とし込むため。
* **Supabase:** 本番運用（スケーリング）を想定してAWS RDSでの構成もTerraformでコード化していますが、個人開発のコスト制約上、現在はSupabaseで稼働させています。
---

## 📐 アーキテクチャ / 設計(理想の構成)
<img width="881" height="357" alt="スクリーンショット 0008-02-16 21 58 01" src="https://github.com/user-attachments/assets/4a6c0327-c632-481f-b0a1-320bb7baacbf" />

* 構成: ALB + NAT Gateway + Private ECS
* 本来あるべき商用環境の構成です。可用性とセキュリティを最大化しています。

## 📐 アーキテクチャ / 設計(現実の構成)
<img width="910" height="340" alt="スクリーンショット 0008-02-16 20 48 23" src="https://github.com/user-attachments/assets/93542eab-f410-4dd2-8272-ddf9536a4e71" />

* 構成: API Gateway + Lambda + Public ECS
* コスト最適化アーキテクチャ（予算制約下でのトレードオフ）：ランニングコストゼロという厳しい非機能要件を満たすため、API Gateway + Lambdaによるサーバーレスプロキシ構成を意図的に採用した

## データモデリング（ER図）
<img width="516" height="690" alt="スクリーンショット 0008-02-21 22 05 13" src="https://github.com/user-attachments/assets/159e3329-0420-4d1c-af83-e907547c6bf4" />


## 運用・保守・セキュリティ
テストテストテストテストテストテストテストテストテストテストテストテストテストテスト
  
## データフロー
1. ユーザーが **LP**もしくはトレーナーが**顧客管理システム（フロントエンド）** から問い合わせ/予約
2. データが **API Gateway**もしくは**ALB** を通じて顧客管理システムへ送信
3. トレーナーが **顧客管理システム（バックエンド）** で予約を確認・ステータス更新

---

## 🚀 今後の展望 (Roadmap)
* LINE公式アカウントとのAPI連携（予約通知の自動化）
* オンライン決済機能（Stripe）の導入
* 売上分析ダッシュボードの実装

---
