# Step 1：一文要約リスト

サービス名を見た瞬間に「何をするものか」が浮かべば OK。細かい仕様は覚えない。
「混同しやすい相手」は、試験でよく並べて出てくるサービス。

## 組織・アカウント管理

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| AWS Organizations | 複数アカウントをまとめて管理！ | Control Tower |
| SCP（サービスコントロールポリシー） | アカウントでできる操作の上限を決める！ | IAM ポリシー |
| AWS Control Tower | マルチアカウント環境をルール付きで自動構築！ | Organizations |
| IAM Identity Center | 複数アカウントへのシングルサインオン！ | IAM、Cognito |
| AWS RAM | リソースを他のアカウントと共有！ | VPC ピアリング |
| AWS Service Catalog | 承認済みの構成をセルフサービスで配る！ | CloudFormation |
| CloudFormation StackSets | 複数アカウント・リージョンへ一括デプロイ！ | CloudFormation |

## 監査・セキュリティ

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| AWS CloudTrail | 誰がいつ何の操作をしたかの記録！ | AWS Config |
| AWS Config | 設定の変更履歴とルール違反チェック！ | CloudTrail |
| Amazon GuardDuty | 怪しい動きを自動で検知！ | Inspector |
| Amazon Inspector | EC2・コンテナの脆弱性スキャン！ | GuardDuty |
| AWS Security Hub | セキュリティの指摘を一か所に集約！ | GuardDuty |
| AWS KMS | 暗号化キーの管理！ | CloudHSM |
| AWS Secrets Manager | パスワード等の保管と自動ローテーション！ | Parameter Store |
| AWS WAF | Web アプリへの攻撃をブロック（L7）！ | Shield |
| AWS Shield | DDoS 攻撃から守る！ | WAF |
| Amazon Cognito | アプリ利用者のサインイン機能！ | IAM Identity Center |

## ネットワーク

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| VPC ピアリング | VPC 同士を1対1でつなぐ（中継できない）！ | Transit Gateway |
| AWS Transit Gateway | 多数の VPC とオンプレをつなぐハブ！ | VPC ピアリング |
| AWS PrivateLink（VPC エンドポイント） | インターネットを通らずサービスへ接続！ | VPC ピアリング |
| AWS Direct Connect | オンプレと AWS の専用線！ | Site-to-Site VPN |
| AWS Site-to-Site VPN | インターネット越しの暗号化接続（すぐ使える）！ | Direct Connect |
| Amazon Route 53 | DNS と、どこへ振り分けるかのルール！ | Global Accelerator |
| Route 53 Resolver | オンプレと VPC の名前解決をつなぐ！ | Route 53 |
| Amazon CloudFront | コンテンツをキャッシュして近くから配信（CDN）！ | Global Accelerator |
| AWS Global Accelerator | 固定 IP と AWS 網で通信を高速化（HTTP 以外も）！ | CloudFront |
| ALB | HTTP の中身（パス等）で振り分け（L7）！ | NLB |
| NLB | 超高速・固定 IP で振り分け（L4）！ | ALB |

## コンピュート

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| Amazon EC2 | 仮想サーバー！ | Lightsail |
| EC2 Auto Scaling | 負荷に合わせて台数を自動増減！ | ELB |
| AWS Lambda | 短い処理をサーバーなしで実行（最大15分）！ | Fargate |
| Amazon ECS | AWS 独自のコンテナ管理！ | EKS |
| Amazon EKS | Kubernetes のコンテナ管理！ | ECS |
| AWS Fargate | サーバー管理なしでコンテナ実行！ | Lambda |
| AWS Elastic Beanstalk | コードを置くだけで Web アプリ環境ができる！ | CloudFormation |
| AWS Batch | 大量のバッチ処理を自動で割り振り！ | Step Functions |

## ストレージ

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| Amazon S3 | 何でも置けるオブジェクトストレージ！ | EFS |
| S3 Glacier | 安い長期保管（取り出しに時間がかかる）！ | S3 標準 |
| Amazon EBS | EC2 1台用のディスク！ | EFS |
| Amazon EFS | 複数の Linux サーバーで共有するファイル置き場！ | FSx |
| FSx for Windows File Server | Windows 用の共有ファイル置き場！ | EFS |
| FSx for Lustre | HPC・機械学習向けの超高速ファイル置き場！ | EFS |
| AWS Storage Gateway | オンプレからクラウドのストレージを使う橋渡し！ | DataSync |
| AWS Backup | いろんなサービスのバックアップを一元管理！ | スナップショット |

## データベース

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| Amazon RDS | 管理付きのリレーショナル DB！ | Aurora |
| Amazon Aurora | 高性能な RDB（Global Database で世界展開）！ | RDS |
| Amazon DynamoDB | サーバーレスのキーバリュー DB（Global Tables）！ | Aurora |
| Amazon ElastiCache | インメモリキャッシュで高速化！ | DAX |
| DynamoDB Accelerator（DAX） | DynamoDB 専用のキャッシュ！ | ElastiCache |
| Amazon Redshift | 巨大データ分析用の DWH！ | Athena |
| Amazon Athena | S3 のデータに直接 SQL！ | Redshift |

## 移行（SAP で特に重要）

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| AWS Migration Hub | 移行の進み具合を一か所で管理！ | Application Discovery Service |
| AWS Application Discovery Service | オンプレのサーバー構成と依存関係を調査！ | Migration Hub |
| AWS Application Migration Service（MGN） | サーバーを丸ごと AWS へ移す（リフト＆シフト）！ | DMS |
| AWS DMS | DB を止めずに移行！ | SCT |
| AWS SCT | 違う種類の DB へスキーマを変換！ | DMS |
| AWS DataSync | 大量ファイルをネット経由で高速転送！ | Storage Gateway |
| AWS Snowball | 物理デバイスで大量データを運ぶ！ | DataSync |
| AWS Transfer Family | SFTP などで S3 にファイル受け渡し！ | DataSync |

## アプリ連携

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| Amazon SQS | キューで処理を疎結合に！ | SNS |
| Amazon SNS | 1つの通知を複数へ一斉送信！ | SQS |
| Amazon EventBridge | イベントを条件で振り分け！ | SNS |
| AWS Step Functions | 複数の処理をワークフローでつなぐ！ | SQS |
| Amazon API Gateway | API の入り口！ | ALB |
| Kinesis Data Streams | リアルタイム処理！ | SQS |
| Amazon Data Firehose | ストリームを S3 などへそのまま配送！ | Kinesis Data Streams |

## 運用・コスト

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| Amazon CloudWatch | メトリクス・ログ・アラーム！ | CloudTrail |
| AWS Systems Manager | サーバー運用の道具箱（パッチ・コマンド実行・接続）！ | OpsWorks |
| AWS Trusted Advisor | ベストプラクティスに沿っているか診断！ | Compute Optimizer |
| AWS Compute Optimizer | サイズの合っていないリソースを指摘！ | Trusted Advisor |
| AWS Cost Explorer | コストの見える化と分析！ | Budgets |
| AWS Budgets | 予算を超えそうなら通知！ | Cost Explorer |
| Savings Plans | 使用量の約束で割引（柔軟）！ | リザーブドインスタンス |
