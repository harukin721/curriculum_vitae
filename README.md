# 業務経歴書

## 基本情報

https://github.com/harukin721/harukin721

## 登壇・執筆など

### 登壇

- [Road to SRE NEXT@京都 に登壇しました - Pepabo Tech Portal](https://tech.pepabo.com/2024/07/26/sre-next-kyoto/)
- [「Pepabo Tech Conference 20 春のSREまつり」開催レポート - Pepabo Tech Portal](https://tech.pepabo.com/2023/04/28/pepabotech/)

### 執筆

- [Amazon RDSの監査ログを保全する信頼性の高いソフトウェアの設計と実装について - Pepabo Tech Portal](https://tech.pepabo.com/2025/04/16/colorme-rds-audit-logs-s3/)
- [技術部合同で合宿をしました！ in 沼津 - Pepabo Tech Portal](https://tech.pepabo.com/2024/07/24/development-camp-in-numazu/)
- [Amazon RDS ブルー/グリーンデプロイを利用してMySQLのアップグレードをした話 - Pepabo Tech Portal](https://tech.pepabo.com/2024/05/10/rds-blue-green-deployment/)
- [日本CTO協会による合同ISUCON研修の紹介 - Pepabo Tech Portal](https://tech.pepabo.com/2024/02/16/isucon-2023/)
- [CloudNative Days Tokyo 2023に参加しました - Pepabo Tech Portal](https://tech.pepabo.com/2023/12/22/cloudnative-days-tokyo-2023/)
- [データに基づく統計手法を用いてNGINXのレートリミットを設定する - Pepabo Tech Portal](https://tech.pepabo.com/2023/12/15/nginx-rate-limit/)
- [『入門 考える技術・書く技術 日本人のロジカルシンキング実践法』の読書会を開催しました - Pepabo Tech Portal](https://tech.pepabo.com/2022/12/14/reading-logical-thinking/)

## 概要

- SRE, Platform, DevOps
- パブリッククラウド(AWS)とプライベートクラウド(OpenStack)のマルチクラウド環境でのシステム保守・運用
- Web サービスの SLI / SLO の監視運用の経験があります。
- 小規模〜大規模サービスの新規開発や、サービスのリプレイス経験があります。
- AWS のコスト削減
- ※ フロントエンドの開発経験はほとんどありません。

## スキル

<details>

<summary>実務で使用した技術のみを記載しています。</summary>

### 言語

Go | Ruby | Python | JavaScript | Java | 

### フレームワーク等

Ruby on Rails | 

### RDB/NoSQL

MySQL | Redis | Memcached | 

<!-- https://findy-tools.io/articles/2024-tech-stack/1 -->

### AWS

VPC | S3 | CloudFront | Lambda | ELB | EC2 | ECS | Fargate | EKS(Kubernetes) | Route53 | IAM | RDS(MySQL) | Aurora | ElastiCache(Redis|Memcached) | Kinesis | Kinesis Firehose | SQS | SNS | SES | CloudFormation | CodePipeline(Blue/Green Deployment) | CloudWatch | CloudTrail | Direct Connect | Secret Manager | Parameter Store | External Secrets | VPC Peering | VPC Endpoint | AWS Organizations | Step Functions | EventBridge Scheduler | 

### インフラ

Openstack | Kubernetes | Docker | NGINX  | Consul |

### 監視・モニタリング

Datadog | Prometheus | Grafana | Mackerel | Sentry | Fluentd | Redash |

### 環境構築

Terraform | Docker | Ansible | Puppet | Helm |

### CI/CD

GitHub Actions | Argo CD |

### その他

GitHub | GitHub Copilot | BitBucket | Slack | Notion | Backlog | esa | Capistrano |

</details>

## 主な業務経歴

現職の実績を主に見ていただきたいです。

### アソビュー株式会社 (2025年04月 〜 )

入社時からアソビューの SRE をしています。

#### WIP 【 WIP 】

##### 担当業務

- WIP

##### 取り組み

- WIP

#### その他 (2025年04月 〜 )

##### 担当業務

- Argo Workflows を最新バージョン（v3.6.5）にアップグレード
- Datadog Agent を最新バージョン（v7.64.3）にアップグレード
- EKS Cluster v1.30.0 のバージョンアップグレード
- Argo CD のサイドカープラグインに helmfile-plugin を追加
- Argo CD のサイドカープラグインを helmfile-plugin, kustomize-plugin の並行運用
- Serverless Framework EOL により、Terraform, Lambroll 移行
- プログレッシブ対応（AnalysisTemplate により、Datadog Monitor をチェック）

### GMOペパボ株式会社 (2022年09月 〜 2025年03月)

<details>

<summary>複数のプロジェクト</summary>

<br>

入社時から国内最大級の ECサイト構築サービスである**カラーミーショップ**の SRE をしています。
- 店舗総数：約5万店舗
- 流通総額：約2000億円

#### CentOS7 撤退のプロジェクトによる Ubunntu 移行 【 OpenStack / Terraform / Puppet 】

##### 担当業務

- Go のリバースプロキシサーバーが動作する CentOS VM を Ubuntu VM に移行

##### 取り組み

- サービスの入口となる重要な VM であり、障害が発生するとサービス全体に影響を及ぼすため、リスクを最小限に抑えた移行計画を策定・実施。
- Terraform 管理の柔軟性向上を図るため、CentOS VM の count 管理を Ubuntu VM では for_each に変更。既存の Puppet コードが CentOS の yum パッケージに依存していたため、Ubuntu の deb パッケージにも対応可能な OS 分岐を追加。
- OpenStack Octavia の Load Balancer にて、Ubuntu VM 用のメンバーを新規作成し、CentOS VM に影響を与えず段階的なカナリアリリースを実施。
- Ubuntu VM では柔軟に weight を調整できるようにしたため、1台ずつ小さな weight からサービスインし、並行運用期間中はエラー監視と調整を行いながら、最終的にサービスに影響を与えることなく、Ubuntu VM の 100% リリースを無事に完了。

#### AWS インフラコスト削減 【 AWS / Go / GitHub Actions 】

##### 担当業務

- サービスの売上・利益の目標達成のために AWS のインフラコスト削減を実施

##### 取り組み

AWS 提唱のクラウド利用費用最適化を進めるためのフレームワーク Cloud Financial Management (CFM) を学ぶ。

- [「AWSコスト最適化ガイドブック」を読んだのでメモ1 - harukin721](https://harukin721.hatenablog.com/entry/2024/03/24/232157)
- [「AWSコスト最適化ガイドブック」を読んだのでメモ2 - harukin721](https://harukin721.hatenablog.com/entry/2024/03/27/200638)

クイックウィン最適化

- AWS のインフラコスト削減に向けて、上位リソースおよびそのコスト割合を算出し、優先的にコスト削減を実施すべき AWS リソースを選定。
- 社内のログガイドラインに基づき、S3 のライフサイクルルールを追加や CloudWatch Logs の低頻度アクセスストレージクラスへの変更を実施。
- Terraform 管理がされていなかった AWS リソースについては、社内の関係者と相談し、不要と判断されたリソースを削除。必要と判断されたリソースは Terraform Import を実施。
- 主に S3 と CloudWatch Logs のコスト削減により、月額 20% のコスト削減を実現。

アーキテクチャ最適化

- [Amazon RDSの監査ログをCloudWatch Logsを介さずにS3へ保存したい](https://tech.pepabo.com/2024/07/24/development-camp-in-numazu/#amazon-rds%E3%81%AE%E7%9B%A3%E6%9F%BB%E3%83%AD%E3%82%B0%E3%82%92cloudwatch-logs%E3%82%92%E4%BB%8B%E3%81%95%E3%81%9A%E3%81%ABs3%E3%81%B8%E4%BF%9D%E5%AD%98%E3%81%97%E3%81%9F%E3%81%84--harukin) を実施。
- Lambda で PoC を実施し、その後 EventBridge Scheduler、Step Functions、ECS on Fargate、CloudWatch Alarms などを組み合わせて、日額 80% のコスト削減を実現。
- RDS の監査ログを取得して S3 に保存する Go プログラムを実装。GitHub で管理し、GitHub Actions で tagpr を活用して、Pull Request がマージされるとリリースタグを自動で付与。さらに、GitHub のリリースバージョンと同じタグを ECR イメージに Push する仕組みを構築し、CI/CD を整備。
- 5分おきに EventBridge Scheduler が Step Functions を呼び出し、Step Functions で ECS on Fargate が ECR からイメージを Pull して実行。実行成功時には専用の Slack チャンネルに通知、実行失敗時には CloudWatch Alarm と PagerDuty を連携させて Slack チャンネルにオンコール通知を実施。
- Step Functions では、Primary DB と Replica DB の監査ログ取得において、Replica DB 数の変動に柔軟に対応できる仕組みを Terraform で構築・管理。
- CloudWatch Alarm の Description にはオンコールドキュメントを追加し、オンコール担当者が迷わず対応できるように整備。
- この取り組みを [Amazon RDSの監査ログを保全する信頼性の高いソフトウェアの設計と実装について - Pepabo Tech Portal](https://tech.pepabo.com/2025/04/16/colorme-rds-audit-logs-s3/) としてテックブログに公開。公開後は 30 件以上のはてなブックマークを獲得。

#### Amazon RDS for MySQL 8.0 のブルー/グリーンデプロイによるアップグレード 【 AWS / MySQL 】

##### 担当業務

- RDS for MySQL のサポートバージョン終了に伴う MySQL バージョンアップグレード
- 担当サービスでは初めての試みとなるブルー/グリーンデプロイを採用し、サービスへの影響を最小限に抑えた安全な移行を実現

##### 取り組み

- Amazon RDS のアップグレード手法として、インプレースアップグレードとブルー/グリーンデプロイの2つの選択肢を比較検討。それぞれのメリット・デメリットを整理し、事業部と協議の上、リスクを最小限に抑えられるブルー/グリーンデプロイを選定。
- Amazon RDS 特有のファーストタッチレイテンシーへの対策を検討し、サービスへの影響を排除するために事前に徹底した検証を実施。また、AWS 公式ドキュメントに記載されたブルー/グリーンデプロイの「通常、ダウンタイムは1分未満」という情報の妥当性を確認。ルー/グリーンデプロイのアップグレードのプロセスを社内外に共有。
- この取り組みを [Amazon RDS ブルー/グリーンデプロイを利用してMySQLのアップグレードをした話 - Pepabo Tech Portal](https://tech.pepabo.com/2024/05/10/rds-blue-green-deployment/) としてテックブログに公開。公開後は 60 件以上のはてなブックマークを獲得。

#### Gmail ガイドライン対応(OpenDKIM,OpenARC 導入) 【 Terraform / Puppet 】

##### 担当業務

- Gmail ガイドライン準拠のため、複数サービスに OpenDKIM および OpenARC を導入
- Puppet を用いた構成管理と Serverspec を活用したインフラテストにより、複数サービス間で効率的かつ迅速に対応

##### 取り組み

- Envelope-From と Header-From の違いや、SPF、DKIM、DMARC といった主要な認証プロトコルについて短期間でキャッチアップ。
- メールサーバーの運用基盤として使用している VM 環境に対し、Puppet を用いて OpenDKIM、OpenARC の設定をコード化。さらに、Serverspec を用いたインフラテストを導入し、設定の正確性を担保。
- メールヘッダーを解析し、意図した認証を正確に通すことで、Gmail ガイドラインの要件に準拠。他のサービスに対しても、同様の対応を展開。

#### NGINX のホスト、IPアドレス、User-Agent などレートリミットを実装 【 Puppet / NGINX 】

##### 担当業務

- NGINX を用いたレートリミットを導入し、負荷分散を実現
- Puppet を活用した構成管理で、将来的な設定の追加や変更が容易な管理方法を確立

##### 取り組み

- LPIC-2 の資格勉強で得た NGINX の知識を基に、公式ドキュメントも読みつつ、レートリミットの仕組みを理解。ホスト単位、IPアドレス単位、User-Agent 単位などでのレートリミットを実装。レートリミット設定を Puppet による構成管理を実施し、設定変更や追加が必要な場合でも効率的に対応を可能にした。
- アクセスログデータを基に統計手法を活用し、適切なレートリミット値を設計。先輩エンジニアの助言を受けつつ、標準偏差を参考に異常アクセスを効率的に制限するアプローチを採用し、具体的な数値を算出。これらの知見を [Nginx のレートリミットの値に標準偏差を活用 - harukin721](https://harukin721.hatenablog.com/entry/2023/11/20/232840) にまとめ、社内外に共有。
- レートリミット導入後、エンドポイントのレイテンシ悪化が大幅に改善され、サービス全体の安定性向上に貢献。この取り組みを [データに基づく統計手法を用いてNGINXのレートリミットを設定する - Pepabo Tech Portal](https://tech.pepabo.com/2023/12/15/nginx-rate-limit/) としてテックブログに公開。公開後は約 40 件のはてなブックマークを獲得。

#### Kubernetes の Datadog 導入 【 Kubernetes / Datadog 】

##### 担当業務

- 特定の Kubernetes Node に Datadog を導入し、効率的なモニタリング環境を構築
- 並行して、Kubernetes の理解を深めるための「ひとり勉強会」を自主的に実施

##### 取り組み

- Kubernetes クラスタ内の Node 構成や役割を把握し、リソース使用状況や重要度を基にモニタリング対象 Node を選定。特定 Node のみを対象とすることで、インフラコストを抑えつつ重要な監視を実現。
- Kubernetes のラベル機能を活用し、Datadog Agent を特定の Node にのみデプロイ。DaemonSet を用いて、Node Selector や Node Affinity を組み合わせた柔軟なデプロイを実現。これらの理解を深める過程でブログ記事「[Node Affinity と Node Selector - harukin721](https://harukin721.hatenablog.com/entry/2023/07/18/224439) を作成し、知識を整理して社内へ共有。
- Datadog を通じて得たモニタリングデータを分析し、サービスのパフォーマンスボトルネックの可視化を実現。

#### Kubernetes のクラスタアップデート 【 Kubernetes / OpenStack / AWS 】

##### 担当業務

- OpenStack on Kubernetes と AWS EKS クラスタのマルチクラウド環境での Kubernetes クラスタのアップデートを実施

##### 取り組み

- 業務開始に際し、Kubernetes の基礎から応用までを効率的に学習するため、自主的な読書会を開催。
  - [Kubernetes完全ガイド 【第2版】 読書会2 Part1 - harukin721](https://harukin721.hatenablog.com/entry/2023/09/03/021341)
  - [Kubernetes完全ガイド 【第2版】 読書会2 Part2 - harukin721](https://harukin721.hatenablog.com/entry/2023/09/18/212850)
  - [Kubernetes完全ガイド 【第2版】 読書会2 Part3 - harukin721](https://harukin721.hatenablog.com/entry/2023/11/04/121614)
  - [Kubernetes完全ガイド 【第2版】 読書会2 Part4 - harukin721](https://harukin721.hatenablog.com/entry/2023/11/05/110541)
- OpenStack on Kubernetes と AWS EKS のマルチクラウド構成を活用し、クラスタアップデート中でもサービスを中断させることなく運用を継続。片方のクラスタをアップデートする際には、ユーザーリクエストをもう一方のクラスタに切り替えることで、ダウンタイムゼロのアップデートを実現。切り替え手順やアップデート計画はチームレビューも通して社内ドキュメントとして整備。
- AWS EKS のノードグループのバージョン互換性やアプリケーション稼働状況を詳細に確認し、段階的なローリングアップデートを実施。

##### その他

- Kubernetes クラスタ運用の中でスキル不足を感じたため、擬似的なトラブルシューティングを通じた学習を実施。
  - [ひとり「トラブルシューティングから学ぶk8s勉強会」Part1 - harukin721](https://harukin721.hatenablog.com/entry/2023/04/17/005725)
  - [ひとり「トラブルシューティングから学ぶk8s勉強会」Part2 - harukin721](https://harukin721.hatenablog.com/entry/2023/04/24/144057)
  - [ひとり「トラブルシューティングから学ぶk8s勉強会」Part3 - harukin721](https://harukin721.hatenablog.com/entry/2023/04/25/001146)

#### メールサーバの移設対応 【 Terraform / Puppet / Serverspec 】

##### 担当業務

- 複数台のメールサーバーでディスク容量が逼迫していたたため、移設・改修を担当
- それに伴い、Puppet で管理している VM の構成変更や Serverspec インフラテストの修正を実施

##### 取り組み

- メールサーバーは VM で運用しており、構成管理は Puppet、インフラテストは Serverspec で行った。入社 3 ヶ月後での対応であり、Terraform、Puppet、Serverspec といった技術スタックのキャッチアップを行いながら進めたが、無事完了。
- 過去のメールログを分析し、メールの利用率が低い時間帯を特定し、CS チームと協議し、メールサービスの影響を最小限に抑えてメンテナンスを実施。
- メールサーバーログのローテーション設定が不完全であることを発見し、設定を改善。Puppet の hieradata におけるパラメーター定義をクラスパラメーターに置き換えることで、データ結合を改善し、メンテナンス性を向上。

#### その他 (2022年09月 〜 )

##### 担当業務

- サービス運用・保守で発生する障害対応
- 24/365 のオンコールシフト体制の障害対応
- 障害対応時のオンコールドキュメント作成
- Mackerel の監視設定の追加・変更
- Redash のアラートを整備、Slack 通知を追加
- メールサーバーの DNSBL、IP レピュテーションの対応
- VM の CPU Steal を調査し、対応としてライブマイグレーションを実施
- APM などを活用し、SLI/SLO の違反原因を調査（Mackerel、Datadog、Sentry、Grafana）
- SSL/TLS 証明書の更新
- PowerDNS のレコード修正
- ProxySQL の割合変更
- VM に導入していた WAF のバージョンアップ作業
- メールサーバーのデータバックアップ用のシェルスクリプト修正
- DNS on EC2 の CentOS の EOL 対応に伴う移設先の検討
- J-SOX 対応でのドキュメント改善と確認対象の見直し
- NIGNX Ingress Controller のバージョンアップデート
- RDS for MySQL のパラメーターチューニング
- RDS のファーストタッチレイテンシ解除用スクリプト作成
- Puppet 未対応部分の VM 構成管理を IaC 化
- 特定のサービスプロバイダ宛てのメール送信失敗を検知する仕組みを導入
- メール送信失敗時の対応としてメールリレーサーバーを経由する仕組みを導入
- Terraform Import を利用して VM と Terraform の差分を埋める対応
- メールサーバーに rspamd の rb_modules 導入
- rspamd log を、fluentd を介して、BigQuery に転送対応

</details>

### 株式会社OKAN (2021年09月 〜 2022年08月)

<details>

<summary>2つのプロジェクト</summary>

#### 複数の既存システムの改修、ITGC 関連業務 【 Ruby on Rails / TypeScript / AWS / Docker 】 (2022年02月 〜 2022年08月)

##### 担当業務

- Ruby on Rails および React, TypeScript で開発された既存システムの改修
- AWS インフラの整備(CloudWatch によるモニタリング、バックアップ証跡の整備など)
- ビジネスサイドからの機能追加・変更要望対応
- ITGC 関連業務および IPO 準備(ドキュメント整備、ワークフロー構築)

##### 課題

- 新規開発の経験はあるが、既存システムの改修経験はない
- Ruby on Rails、React、Web API の実務経験がない

##### 取り組み

- 技術キャッチアップ: Ruby on Rails と React, TypeScript に関する動画教材や公式ドキュメントを活用し、社内の先輩エンジニアのサポートも受けながら開発業務を進めた。また、外部の勉強会(compass)や、オンラインコミュニティに参加して、社外の方からも AWS などの知識などを吸収していた。
- コミュニケーション: ビジネスサイドの方からの既存システムへの改修依頼に対応し、影響範囲を把握した上で改修を実施した。既存システムの仕様や改修による影響を具体的に説明して連携を取ることもあった、さらに社内のドキュメントを整備することで知識共有を行った。
- 効率的な問題解決: 「15分ルール」を設定し、自力で調査を進める一方、必要に応じて適切に質問することで、先輩エンジニアの時間を無駄にしないよう配慮し、業務効率と学習効率の向上を図った。
- ITGC関連業務: IPO に向けたタスクをファイナンスグループなどの関係者と連携し、EC2 や RDS のバックアップ整備などを担当した。ITGC 関連のドキュメント作成やワークフロー整備も行った。
- プロジェクト管理: Backlog を用いたタスク管理や進捗管理を実施し、スクラム開発で行った。

#### AWS を使用したインフラ設計・構築 【 AWS 】 (2021年09月 〜 2022年01月)

##### 担当業務

- システム全体の AWS インフラの設計、CloudFormation による構築とコード化
- CloudFront + S3 の静的リソース配信基盤、Auora MySQL、ECS on Fargate の導入
- CI/CD(CodePipeline)整備およびインフラ構成のドキュメント作成

##### 課題

- 入社後すぐにインフラ担当になったが、インフラに精通しているエンジニアがいなかったため、自力で進める必要があった
- 実務で AWS を使用した経験も、インフラ業務の経験も全くない状態だった
- 独学で AWS 認定を取得し、AWS コンソールを使用した経験はあったが、CloudFormation などの IaC の経験はなかった

##### 取り組み

- 自発的な IaC 化: AWS のインフラ構築するにあたり、上司からコンソール操作での設定が許可がされていたが、将来的な運用効率を考慮し、自ら IaC 化を提案。っ社内ルールで AWS のみを使用する方針だったため、CloudFormation を採用し、基礎から学びつつ、可能な箇所はすべて IaC 化を実施。AWS 公式ドキュメント、動画教材、書籍、そして AWS サポートさんなど、利用可能だったリソースをフルに活用して取り組んだ。
- CI/CD の設計: CI/CD の基礎知識を学びながら、AWS の CodePipeline を活用して、効率的なデプロイフローを構築。これにより、リリース作業の自動化と精度向上が実現。
- リソース最適化: ECS（Fargate）の使用に伴い、NAT Gateway 経由によるコスト増加の課題に直面。この課題を解決するため、VPC Endpoint を活用するなど、運用の見直しを繰り返すことでリソース最適化を図った。
- 継続的な学習: AWS 認定資格取得時の知識を基盤にしながら、必要な技術を随時補強した。また、外部の勉強会(compass)や、オンラインコミュニティに積極的に参加し、社外のエンジニアからの知見も吸収。
- ドキュメント作成: AWS の構成図や運用ルールを整備し、チームでの共有可能なドキュメントを作成。また、命名規則を統一することで構成の視認性を向上させて、チーム全体で効率的な運用が行える環境を整備。
- チーム連携: フロントエンドやバックエンドの開発チームがスムーズに作業を進められるよう、インフラがボトルネックがならないように努めた。必要に応じて、残業を行ってしまうこともあったが、プロジェクトのインフラ構築期限を守った。
- プロジェクト管理: Backlog を活用したタスク管理や進捗管理を行い、スクラム開発を円滑に進行。チーム内で課題の共有も行った。
- 参考リソース: この業務に関する内容は、かつて Wantedly の記事として公開していたが、現在はアーカイブとなっている。記事のバックアップを  [curriculum_vitae/wantedly at main · harukin721/curriculum_vitae](https://github.com/harukin721/curriculum_vitae/tree/main/wantedly) に保存している。なお、業務全般で [AWSコンテナ設計・構築[本格]入門 | SBクリエイティブ](https://www.sbcr.jp/product/4815607654/) にとても助けられました。

</details>

### 株式会社アップロード (2020年04月 〜 2021年08月)

<details>

<summary>1つのプロジェクト</summary>

#### 大手電力会社 一般家庭の電力需供量の実証実験 【 Java / MySQL 】 (2020年07月 〜 2021年08月)

##### 担当業務

- 新規機能のバッチ処理の開発(客先常駐)
- 初めての実務でJavaを使用して、電力量の需給データ、消費量データ処理バッチを開発

##### 取り組み

- 3ヶ月間の新人研修で Java、MySQL を中心に学んだ。
- 在籍中に https://github.com/harukin721/harukin721 にある AWS 認定資格や LPIC-1 を取得。
- Linux、AWS、Docker、Github を学んでいた。
- Ruby on Rails を活用して Web アプリケーションを作成し、AWS コンソールから EC2 を構築してデプロイ。

</details>
