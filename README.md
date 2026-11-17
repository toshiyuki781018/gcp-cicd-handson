# gcp-cicd-handson

# Google Cloud CI/CD ハンズオン

## 1. 概要

このリポジトリは、「Google Cloud基礎・操作体験研修」の演習⑧で使用するサンプルアプリケーションです。

GitHubとGoogle Cloudのサービスを連携させ、ソースコードの変更からアプリケーションのデプロイまでを自動化するCI/CDの仕組みを学習します。

## 2. 演習の目的

この演習では、次の内容を体験します。

- GitHubとCloud Buildの連携
- Cloud Buildによるコンテナイメージのビルド
- Artifact Registryへのコンテナイメージの保存
- Cloud Runへの自動デプロイ
- GitHubのソースコード変更による自動更新
- 各サービスでの実行結果の確認

## 3. システム構成

以下の流れでアプリケーションを自動デプロイします。

```text
GitHub
  │
  │ ソースコードの変更・push
  ▼
Cloud Build
  │
  │ Dockerイメージのビルド
  ▼
Artifact Registry
  │
  │ コンテナイメージの保存
  ▼
Cloud Run
  │
  ▼
アプリケーションの実行
```

Cloud Buildは、`cloudbuild.yaml` に定義された処理に従い、コンテナイメージの作成、保存、Cloud Runへのデプロイを実行します。

## 4. ファイル構成

```text
gcp-cicd-handson/
├── README.md
├── main.py
├── requirements.txt
├── Dockerfile
└── cloudbuild.yaml
```

| ファイル | 役割 |
|---|---|
| README.md | 演習の概要とファイル構成の説明 |
| main.py | サンプルアプリケーションのソースコード |
| requirements.txt | Pythonライブラリの依存関係 |
| Dockerfile | コンテナイメージの作成手順 |
| cloudbuild.yaml | Cloud Buildによるビルド・デプロイ処理の定義 |

## 5. 事前準備

研修開始前に、以下の準備を完了してください。

1. GitHubアカウントを作成する。
2. 自分のGitHubアカウントで新しいリポジトリ `gcp-cicd-handson` を作成する。
3. 講師から配布された演習用ファイルをリポジトリへアップロードする。
4. 5つのファイルが登録されていることを確認する。

Google Cloudのプロジェクト、必要なAPI、IAM権限などは講師側で準備します。

## 6. 研修当日の演習

研修当日は、GitHubとGoogle Cloudを連携し、Cloud Buildのトリガーを設定します。

その後、サンプルアプリケーションのコードを変更し、GitHubへのpushをきっかけに自動デプロイが実行されることを確認します。

具体的な操作方法は、研修で配布する演習手順書に従ってください。

## 7. 演習時の注意事項

- 講師から指定されたGoogle Cloudプロジェクトを使用してください。
- `cloudbuild.yaml` などの設定ファイルは、講師の指示なく変更しないでください。
- パスワード、APIキー、認証情報などをGitHubに登録しないでください。
- 演習終了後は、講師の指示に従って不要なGoogle Cloudリソースを削除してください。

## 8. 到達目標

演習終了時に、以下を説明できることを目標とします。

- GitHub、Cloud Build、Artifact Registry、Cloud Runの役割
- GitHubへのpushからCloud Runへのデプロイまでの処理の流れ
- 自動デプロイの実行結果を確認する方法
- CI/CDを利用するメリット

---

Google Cloud基礎・操作体験研修  
第5部 第13章／演習⑧ CI/CDによるデプロイ
