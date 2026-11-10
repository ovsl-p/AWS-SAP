# 学習計画（SAP-C03・8週間・週10時間の目安）

前提：SAA 取得済み、業務で EC2 / Aurora / Route 53 / ECS を経験。
合計 約80時間。試験日や使える時間が決まったら、週数を伸び縮みさせる。

## 力を入れる分野

業務で触れていない可能性が高く、配点も大きいところを優先する。
「タスク」は公式試験ガイドの番号。

| 優先 | テーマ | 分野（配点） | 主なサービス・キーワード |
| --- | --- | --- | --- |
| 高 | マルチアカウントのガバナンスと ID | 2（25%） | Organizations、SCP / RCP、Control Tower、IAM Identity Center、クロスアカウントのロール、KMS |
| 高 | ネットワークとハイブリッド | 1（25%） | Transit Gateway、Cloud WAN、Direct Connect、VPN、PrivateLink、VPC Lattice、Outposts |
| 高 | 生成 AI・AI エージェント（C03 で追加） | 1・2 | Bedrock、ナレッジベース（RAG）、ガードレール、AgentCore、SageMaker AI |
| 高 | 運用の自動化 | 5（20%） | CloudFormation / CDK、CodePipeline、CloudWatch、X-Ray、Systems Manager |
| 中 | 移行と災害対策 | 4（15%） | 移行戦略（7R）、MGN、DMS、DataSync、RPO / RTO、DR の4パターン、Elastic Disaster Recovery |
| 中 | コスト最適化 | 3（15%） | Savings Plans、リザーブド、スポット、S3 ストレージクラス、データ転送料金 |
| 中 | データ分析基盤（C03 で比重増） | 1 | Glue、Athena、Lake Formation、Redshift、EMR、MSK |
| 低 | 経験済みの分野 | — | EC2、Aurora、Route 53、ECS は問題を解いて穴だけ埋める |

## 問題集についての注意

SAP-C03 は始まったばかりで、問題集の多くは SAP-C02 向けに作られている。
C02 の内容は大部分が C03 でも出るので使えるが、次の追加分は問題集に載っていない可能性がある。

- 生成 AI・AI エージェント
- データレイク・分析パイプライン
- コンテナの運用と監視、CI/CD のセキュリティ
- IPv6、ポスト量子暗号、マルチテナント設計

追加分は、公式試験ガイドの [C02 と C03 の比較](https://docs.aws.amazon.com/ja_jp/aws-certification/latest/solutions-architect-professional-03/sap-03-comparison.html) を見ながら、Claude に解説や練習問題を頼んで補う。

## 週ごとの目安

- [ ] **1週目：用語と1周目の開始**
  - `01_glossary.md` をひと通り眺める（1〜2時間で切り上げる）
  - 問題集を決めて1周目を始める。分からなければすぐ解説を見る
- [ ] **2〜3週目：1周目を終える**
  - 1日20問くらいのペース。正答率は気にしない（最初は4〜5割で普通）
  - 間違えた問題は `04_mistakes.md` に1行ずつ
- [ ] **4〜5週目：2周目と深掘り**
  - 2周目。間違えた・迷った問題を `03_why/` にまとめる
  - 混同しやすいサービスの使い分けを整理する
- [ ] **6週目：C03 の追加分と弱点つぶし**
  - 生成 AI など C03 の追加分を、Claude に解説と練習問題を頼んで補う
  - 間違えた問題だけ3周目
  - `04_mistakes.md` を Claude に分析してもらい、弱い分野を集中補強
- [ ] **7週目：本番形式の練習**
  - 75問を通しで2回。時間配分を体で覚える
  - 目標：正答率8割以上
- [ ] **8週目：仕上げ**
  - AWS Skill Builder の公式練習問題（SAP-C03 版があればそれ）を解く
  - `03_why/` の「一言で言うと」と使い分けの表を見直す
  - 受験

## 受験の目安

- 問題集の2周目以降で正答率9割
- 初見の模擬試験で8割前後
- 間違えた問題について、全選択肢のダメな理由を言える
- C03 の追加分（特に Bedrock まわり）を一言で説明できる
