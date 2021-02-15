## Security

### アプローチ

AWSのデータセンターやアーキテクチャはセキュリティを高く設定している

全てのユーザがその恩恵を受けられる

- 継続的改善（絶えず進化するセキュリティサービス）
- 従量課金制（より低いコストで求められるセキュリティ要件を満たす）
- 責任共有モデル（AWSのセキュリティ統制を継承できるので、管理を減らすことができる）

### 機能

ネットワークセキュリティ

- インスタンスとサブネットに対するネットワークアクセスの制限
- 組み込みファイアウォール
- 転送中の暗号化（TLS）
- プライベート接続・専用接続
- DDoSの緩和

クラウド内で保管されているデータを暗号化できる（EBS・S3など、ソリューションによる）

- 暗号化機能
- キー管理オプション（AWS Key Management Service）
- ハードウェアベースの暗号キーストレージ（AWS CloudHSM）

アクセスコントロールとアクセス管理

- IAM(Identity and Access Management)
  - AWSリソースにアクセスできる個々のユーザアカウントを定義できる
- MFA(Multi-Factor Authentication)
  - ハードウェアベース認証を使用できる
- 社内ディレクトリとの統合とフェデレーション
  - フェデレーション：一度認証した情報を使い回すこと、認証連携
  - IAMと独自のアプリケーション・サービスとのAPI統合ができる
- Amazon Cognito
- AWS SSO

モニタリングとログ記録

- APIコールの高い可視性
  - 誰がいつ何を行ったか
- ログの集計
- アラート通知
  - しきい値を超えたときにアラート

AWS Marketplace

- AWSで実行できるセキュリティソフトのストア
  - アプリケーションファイアウォールなど
  

