# aws-architecture-guide
🏗️ AWS アーキテクチャ設計ガイド

質問に答えるだけで、AWSの最適な構成・構成図・コスト概算・IaCコードが生成されるインタラクティブなガイドツールです。

## 📸 スクリーンショット

| システム種別の選択 | 設計の質問 | 結果サマリー |
|:-:|:-:|:-:|
| システムの特性を6種別から選択 | 選択肢ごとに適切なケースとトレードオフを表示 | 構成図・コスト・IaCをタブで確認 |

## ✨ 機能

### 🧭 ステップ式設計フロー
- **Phase 0** — システム種別を選択（Web / API / データ基盤 / バッチ / マイクロサービス / IoT）
- **Phase 1** — 共通基盤の設計（リージョン・AZ構成）
- **Phase 2** — 種別固有コンポーネントの設計（コンピューティング・DB・ストレージ等）
- **Phase 3** — 横断的設計（セキュリティ・CI/CD・可観測性）

各選択肢には「✓ 適切な場合」と「⚠ トレードオフ」が明示されているため、根拠を持って選択できます。

### 📐 アーキテクチャ構成図（自動生成）
選択した内容をもとにSVG構成図をリアルタイム生成。6種別すべてに対応しています。

### 💰 コスト概算
東京リージョン・中規模トラフィックを想定した月額コストのレンジ（円）をカテゴリ別に表示。Reserved Instances活用などのコスト削減ヒントも提示します。

### ✅ 設計チェックリスト
可用性・DR、セキュリティ、パフォーマンス、運用・監視、コンプライアンスの5カテゴリ・24項目のチェックリスト。進捗バーで完了状況を可視化します。

### 🏗 IaC スニペット生成
選択構成に対応したスターターコードを自動生成。**Terraform (HCL)** と **AWS CDK (TypeScript)** に対応し、ワンクリックでコピーできます。

### 🔗 URLシェア
設計内容をURLハッシュに保存し、チームへの共有や後からの再開が可能です。

## 🚀 使い方

### ブラウザで直接開く（推奨）

```bash
git clone https://github.com/your-username/aws-architecture-guide.git
cd aws-architecture-guide
```

`aws-architecture-guide.html` をブラウザで開くだけで動作します。Node.jsやサーバーは不要です。

> **初回のみインターネット接続が必要です。**  
> React・Babelをcdnjsから読み込むため、初回アクセス時にネットワークが必要です。  
> 以降はブラウザキャッシュで動作します。

### 完全オフライン環境での使用

以下の3ファイルをダウンロードして `libs/` フォルダに配置し、HTMLファイル内のCDNリンクをローカルパスに書き換えてください。

| ライブラリ | 取得元 |
|---|---|
| `react.production.min.js` | https://unpkg.com/react@18/umd/react.production.min.js |
| `react-dom.production.min.js` | https://unpkg.com/react-dom@18/umd/react-dom.production.min.js |
| `babel.min.js` | https://unpkg.com/@babel/standalone/babel.min.js |

HTMLファイル内の以下の部分を書き換えます。

```html
<!-- 変更前 -->
<script src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
<script src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
<script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>

<!-- 変更後 -->
<script src="libs/react.production.min.js"></script>
<script src="libs/react-dom.production.min.js"></script>
<script src="libs/babel.min.js"></script>
```

## 🌐 対応ブラウザ

| ブラウザ | バージョン |
|---|---|
| Google Chrome | 90以上 |
| Microsoft Edge | 90以上 |
| Mozilla Firefox | 88以上 |
| Safari | 14以上 |

## 📁 ファイル構成

```
aws-architecture-guide/
├── aws-architecture-guide.html   # メインファイル（これ1つで動作）
├── aws-architecture-guide.jsx    # Reactソースコード
└── README.md
```

## 🗺️ 対応システム種別

| 種別 | 主な設計項目 |
|---|---|
| 🌐 Webアプリケーション | フロントエンド配信・コンピューティング・DB・セキュリティ・CI/CD |
| ⚡ API バックエンド | API実行環境・データストア・認証・デプロイ戦略 |
| 📊 データ基盤 / 分析 | データ収集・ストレージ・ETL変換・BI可視化 |
| ⚙️ バッチ処理 | 実行環境・オーケストレーション・セキュリティ |
| 🔀 マイクロサービス | 実行基盤・サービスメッシュ・データ管理・可観測性 |
| 📡 IoT / ストリーミング | デバイス接続・ストリーム処理・時系列DB・セキュリティ |

## ⚠️ 注意事項

- コスト概算は参考値です。実際の費用は [AWS Pricing Calculator](https://calculator.aws/pricing/2/home) でご確認ください。
- IaCスニペットはスターター用の骨格コードです。実際のデプロイ前に必ずセキュリティレビューを実施してください。
- 構成図は概略図です。実際の構成はより詳細な設計が必要です。

## 📄 ライセンス

MIT License
