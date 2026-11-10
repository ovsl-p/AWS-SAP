# Step 1：一文要約リスト（SAP-C03）

サービス名を見た瞬間に「何をするものか」が浮かべば OK。細かい仕様は覚えない。
「混同しやすい相手」は、試験でよく並べて出てくるサービス。
★ は SAP-C03 で新しく対象になった、または出題内容に追加されたもの。

## 組織・アカウント管理

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| AWS Organizations | 複数アカウントをまとめて管理！ | Control Tower |
| SCP（サービスコントロールポリシー） | アカウント内の人ができる操作の上限を決める！ | IAM ポリシー、RCP |
| RCP（リソースコントロールポリシー） | リソースへのアクセスの上限を決める（外部からのアクセス制限）！ | SCP |
| AWS Control Tower | マルチアカウント環境をルール付きで自動構築！ | Organizations |
| IAM Identity Center | 複数アカウントへのシングルサインオン！ | IAM、Cognito |
| AWS RAM | リソースを他のアカウントと共有！ | VPC ピアリング |
| CloudFormation StackSets | 複数アカウント・リージョンへ一括デプロイ！ | CloudFormation |
| Service Quotas | サービスの上限値の確認と引き上げ申請！ | Trusted Advisor |

## ID・アクセス管理

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| IAM | AWS を操作する権限の管理！ | IAM Identity Center |
| Amazon Cognito | アプリ利用者のサインイン機能（ユーザープール / ID プール）！ | IAM Identity Center |
| AWS Directory Service | AWS 上の Active Directory！ | IAM Identity Center |
| ★ IAM Roles Anywhere | AWS の外のサーバーに証明書で一時的な権限を渡す！ | IAM ユーザーのアクセスキー |
| ★ Amazon Verified Permissions | アプリ内の細かい認可ルールを管理！ | Cognito |
| ★ AWS Verified Access | VPN なしで社内アプリへ安全にアクセス（ゼロトラスト）！ | Client VPN |

## 監査・セキュリティ

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| AWS CloudTrail | 誰がいつ何の操作をしたかの記録！ | AWS Config |
| AWS Config | 設定の変更履歴とルール違反チェック！ | CloudTrail |
| Amazon GuardDuty | 怪しい動きを自動で検知！ | Inspector |
| Amazon Inspector | EC2・コンテナイメージ・Lambda の脆弱性スキャン！ | GuardDuty |
| AWS Security Hub | セキュリティの指摘を一か所に集約！ | GuardDuty |
| ★ Amazon Security Lake | セキュリティのログを1つのデータレイクに集める！ | Security Hub |
| AWS KMS | 暗号化キーの管理！ | CloudHSM |
| AWS CloudHSM | 専用のハードウェアでキーを管理（厳しい規制向け）！ | KMS |
| AWS Secrets Manager | パスワード等の保管と自動ローテーション！ | Parameter Store |
| AWS Certificate Manager（ACM） | SSL/TLS 証明書の発行と自動更新！ | KMS |
| AWS WAF | Web アプリへの攻撃をブロック（L7）！ | Shield |
| AWS Shield | DDoS 攻撃から守る！ | WAF |
| AWS Network Firewall | VPC の通信を検査してフィルタリング！ | セキュリティグループ、WAF |
| AWS Artifact | AWS のコンプライアンスレポートを入手！ | Config |

## ネットワーク

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| VPC ピアリング | VPC 同士を1対1でつなぐ（中継できない）！ | Transit Gateway |
| AWS Transit Gateway | 多数の VPC とオンプレをつなぐハブ！ | VPC ピアリング |
| ★ AWS Cloud WAN | 世界規模のネットワークをポリシーで一元管理！ | Transit Gateway |
| AWS PrivateLink（VPC エンドポイント） | インターネットを通らずサービスへ接続！ | VPC ピアリング |
| ★ Amazon VPC Lattice | VPC やアカウントをまたいでサービス同士をつなぐ！ | PrivateLink、Transit Gateway |
| AWS Direct Connect | オンプレと AWS の専用線！ | Site-to-Site VPN |
| AWS Site-to-Site VPN | インターネット越しの暗号化接続（すぐ使える）！ | Direct Connect |
| Amazon Route 53 | DNS と、どこへ振り分けるかのルール！ | Global Accelerator |
| Route 53 Resolver | オンプレと VPC の名前解決をつなぐ！ | Route 53 |
| Amazon CloudFront | コンテンツをキャッシュして近くから配信（CDN）！ | Global Accelerator |
| AWS Global Accelerator | 固定 IP と AWS 網で通信を高速化（HTTP 以外も）！ | CloudFront |
| ALB | HTTP の中身（パス等）で振り分け（L7）！ | NLB |
| NLB | 超高速・固定 IP で振り分け（L4）！ | ALB |
| Amazon API Gateway | API の入り口（REST / HTTP / WebSocket）！ | ALB |

## コンピュート・コンテナ

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| Amazon EC2 | 仮想サーバー！ | Fargate |
| EC2 Auto Scaling | 負荷に合わせて EC2 の台数を自動増減！ | Application Auto Scaling |
| ★ AWS Application Auto Scaling | EC2 以外（ECS、DynamoDB など）を自動増減！ | EC2 Auto Scaling |
| AWS Lambda | 短い処理をサーバーなしで実行（最大15分）！ | Fargate |
| Amazon ECS | AWS 独自のコンテナ管理！ | EKS |
| Amazon EKS | Kubernetes のコンテナ管理！ | ECS |
| AWS Fargate | サーバー管理なしでコンテナ実行！ | Lambda |
| Amazon ECR | コンテナイメージの保管場所（スキャン機能つき）！ | CodeArtifact |
| AWS Elastic Beanstalk | コードを置くだけで Web アプリ環境ができる！ | CloudFormation |

## ハイブリッド

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| AWS Outposts | 自社データセンターに AWS の機器を置く！ | Local Zones |
| ★ AWS Local Zones | 大都市の近くに置かれた AWS の小さな拠点（低遅延）！ | Outposts |
| ★ ECS Anywhere / EKS Anywhere | オンプレのサーバーで ECS / EKS を動かす！ | Outposts |
| AWS Storage Gateway | オンプレからクラウドのストレージを使う橋渡し！ | DataSync |

## ストレージ

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| Amazon S3 | 何でも置けるオブジェクトストレージ！ | EFS |
| S3 Glacier | 安い長期保管（取り出しに時間がかかる）！ | S3 標準 |
| Amazon EBS | EC2 1台用のディスク！ | EFS |
| Amazon EFS | 複数の Linux サーバーで共有するファイル置き場！ | FSx |
| FSx for Windows File Server | Windows 用の共有ファイル置き場！ | EFS |
| FSx for Lustre | HPC・機械学習向けの超高速ファイル置き場！ | EFS |
| AWS Backup | いろんなサービスのバックアップを一元管理！ | Data Lifecycle Manager |
| ★ Amazon Data Lifecycle Manager | EBS スナップショットと AMI の作成・削除を自動化！ | AWS Backup |

## データベース

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| Amazon RDS | 管理付きのリレーショナル DB！ | Aurora |
| Amazon Aurora | 高性能な RDB（Global Database で世界展開）！ | RDS |
| Amazon DynamoDB | サーバーレスのキーバリュー DB（Global Tables）！ | Aurora |
| Amazon ElastiCache | インメモリキャッシュで高速化（消えてもよいデータ）！ | MemoryDB |
| ★ Amazon MemoryDB | データが消えないインメモリ DB（Redis 互換）！ | ElastiCache |
| Amazon DocumentDB | MongoDB 互換のドキュメント DB！ | DynamoDB |
| Amazon Neptune | 関係をたどるグラフ DB！ | DynamoDB |
| Amazon Keyspaces | Cassandra 互換の DB！ | DynamoDB |
| Amazon Timestream | 時系列データ用の DB！ | DynamoDB |

## データ分析（C03 で比重増）

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| Kinesis Data Streams | リアルタイムにデータを流す！ | SQS、MSK |
| Amazon MSK | 管理付きの Apache Kafka！ | Kinesis Data Streams |
| AWS Glue | ETL（データ変換）とデータカタログ！ | EMR |
| Amazon EMR | Spark / Hadoop で大規模データ処理！ | Glue |
| Amazon Athena | S3 のデータに直接 SQL！ | Redshift |
| Amazon Redshift | 巨大データ分析用の DWH！ | Athena |
| AWS Lake Formation | データレイクの権限をまとめて管理！ | Glue |
| Amazon OpenSearch Service | 全文検索とログ分析！ | Athena |
| Amazon QuickSight | グラフやダッシュボードで可視化（BI）！ | CloudWatch ダッシュボード |
| Amazon AppFlow | SaaS（Salesforce 等）と AWS の間でデータ連携！ | Glue |
| ★ AWS Clean Rooms | 生データを見せ合わずに他社と共同分析！ | Lake Formation |

## 生成 AI・機械学習（C03 で追加）

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| ★ Amazon Bedrock | いろんな基盤モデルを API で使う生成 AI サービス！ | SageMaker AI |
| ★ Bedrock ナレッジベース | 社内文書を検索して回答させる（RAG）！ | ファインチューニング |
| ★ Bedrock ガードレール | 生成 AI の入出力から有害な内容や個人情報を除く！ | WAF |
| ★ Bedrock AgentCore | AI エージェントを動かして運用する基盤！ | Step Functions |
| ★ Amazon SageMaker AI | 自前の ML モデルを作って推論エンドポイントで動かす！ | Bedrock |

## 移行

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| AWS Transform MGN（旧 Application Migration Service） | サーバーを丸ごと AWS へ移す（リホスト）！ | DMS |
| ★ AWS Transform | AI エージェントでレガシー（メインフレーム、VMware、.NET）を刷新！ | MGN |
| AWS DMS | DB を止めずに移行！ | SCT |
| AWS SCT | 違う種類の DB へスキーマを変換！ | DMS |
| AWS DataSync | 大量ファイルをネット経由で高速転送！ | Storage Gateway |
| AWS Transfer Family | SFTP などで S3 にファイル受け渡し！ | DataSync |
| ★ AWS Data Transfer Terminal | 専用の施設にストレージ機器を持ち込んで高速アップロード！ | DataSync |

## 回復力・災害対策

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| AWS Elastic Disaster Recovery | サーバーを常時複製しておき、災害時にすぐ起動！ | AWS Backup、MGN |
| ★ AWS Resilience Hub | アプリが RTO / RPO の目標を満たせるか評価！ | Trusted Advisor |
| ★ AWS Fault Injection Service | わざと障害を起こして耐えられるか試す（カオスエンジニアリング）！ | Resilience Hub |

## アプリ連携

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| Amazon SQS | キューで処理を疎結合に！ | SNS |
| Amazon SNS | 1つの通知を複数へ一斉送信！ | SQS |
| Amazon EventBridge | イベントを条件で振り分け！ | SNS |
| AWS Step Functions | 複数の処理をワークフローでつなぐ！ | SQS |
| Amazon MQ | 既存のメッセージブローカー（ActiveMQ / RabbitMQ）をそのまま移行！ | SQS |

## 開発・デプロイ（分野5）

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| AWS CloudFormation | インフラをテンプレート（YAML / JSON）で作る！ | CDK |
| ★ AWS CDK | インフラをプログラミング言語で書く！ | CloudFormation |
| AWS CodePipeline | ビルドからデプロイまでの流れを自動化！ | CodeBuild |
| AWS CodeBuild | ビルドとテストを実行！ | CodePipeline |
| AWS CodeDeploy | アプリをデプロイ（ブルー/グリーン、カナリア）！ | CodePipeline |
| ★ AWS CodeCommit | AWS 上の Git リポジトリ！ | ECR |

## 監視・運用（分野5）

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| Amazon CloudWatch | メトリクス・ログ・アラーム！ | CloudTrail |
| CloudWatch Container Insights | コンテナ（ECS / EKS）の監視！ | X-Ray |
| ★ CloudWatch Synthetics | 擬似的なアクセスを定期的に流して外形監視！ | CloudWatch RUM |
| ★ CloudWatch RUM | 実際の利用者の体感を計測！ | CloudWatch Synthetics |
| AWS X-Ray | リクエストがサービス間をどう流れたか追跡！ | CloudWatch Logs |
| ★ AWS Distro for OpenTelemetry | OpenTelemetry 形式でメトリクスとトレースを集める！ | X-Ray |
| AWS Systems Manager | サーバー運用の道具箱（パッチ・コマンド実行・自動化）！ | Config |
| AWS Compute Optimizer | サイズの合っていないリソースを指摘！ | Trusted Advisor |

## コスト

| サービス | 一言で | 混同しやすい相手 |
| --- | --- | --- |
| AWS Cost Explorer | コストの見える化と分析！ | Budgets |
| AWS Budgets | 予算を超えそうなら通知！ | Cost Explorer |
| AWS コストと使用状況レポート（CUR） | 最も細かい利用明細を S3 に出力！ | Cost Explorer |
| ★ AWS Cost Categories | コストを自分たちの区分（部署・プロジェクト）でまとめる！ | コスト配分タグ |
| Savings Plans | 使用量の約束で割引（柔軟）！ | リザーブドインスタンス |
| ★ リザーブドインスタンス | インスタンスの種類を決めて予約割引！ | Savings Plans |
