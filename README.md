# AWS-SAP

AWS Certified Solutions Architect – Professional（**SAP-C03**）の勉強メモ。

勉強法は [この記事](https://qiita.com/kohYoung_I/items/cce40cb5b9cdfc1f8787) の「過集中スイッチ」を取り入れている。

> 知らない単語をなくして手を止めない → 問題を反射で解けるまで回す → 「なぜ？」が気になったところを深掘りする

学習計画は [00_plan.md](00_plan.md) を参照。

## 試験の概要（SAP-C03）

2026年11月17日から実施。SAP-C02 は 11月16日で終了。

- 75問（採点対象 65問 ＋ 採点対象外 10問）
- 合格スコア：720 / 1000
- 択一問題と複数選択問題

| 分野 | 内容 | 配点 |
| --- | --- | --- |
| 1 | クラウド向けに構築されたアーキテクチャの設計と実装 | 25% |
| 2 | セキュリティ、コンプライアンス、ガバナンス | 25% |
| 3 | コストを最適化したアーキテクチャの設計 | 15% |
| 4 | 回復力、移行、事業の継続性 | 15% |
| 5 | 運用上の優秀性とオートメーション | 20% |

SAP-C02 との主な違い：

- 生成 AI・AI エージェント（Amazon Bedrock など）が出題範囲に入った
- データ分析基盤、コンテナ運用、CI/CD、オブザーバビリティの比重が増えた
- IoT、WorkSpaces、メディア系サービスは対象から外れた

出典：[SAP-C03 試験ガイド](https://docs.aws.amazon.com/ja_jp/aws-certification/latest/solutions-architect-professional-03/solutions-architect-professional-03.html)、[C02 と C03 の比較](https://docs.aws.amazon.com/ja_jp/aws-certification/latest/solutions-architect-professional-03/sap-03-comparison.html)

## 4つのステップとファイル

| Step | やること | ファイル |
| --- | --- | --- |
| 1 | サービスを **一文だけ** で覚える。細かい仕様は無視 | [01_glossary.md](01_glossary.md) |
| 2 | 講義は飛ばして問題集を周回する。分からなければすぐ答えを見る | [02_practice-log.md](02_practice-log.md) |
| 3 | 「なぜ正解？」「なぜ他はダメ？」が気になった問題を深掘りする | [03_why/](03_why/) |
| 4 | 間違えた問題を記録し、AI に傾向を分析してもらう | [04_mistakes.md](04_mistakes.md) |

## 進め方のコツ

- Step 1 は「見た瞬間に役割が浮かぶ」くらいで十分。完璧に覚えなくていい
- Step 2 で問題と答えを覚えるのはゴールではなく、深く理解するための助走
- Step 3 は義務でやらない。気になった問題だけでいい
- 毎回の勉強は、まず Step 2 の周回から始めると手が止まりにくい

## Claude への頼み方の例

- 「この問題を `03_why/` にまとめて」と、問題文・選択肢・正解を貼る
- 「`01_glossary.md` に ○○ を一文で追加して」
- 「`04_mistakes.md` を見て、間違えやすい傾向を分析して」
- 「○○ と △△ の使い分けを、試験で見分けるキーワードで教えて」
