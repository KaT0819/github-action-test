# github-action-test
![example workflow](https://github.com/KaT0819/github-action-test/actions/workflows/github-actions-demo.yml/badge.svg)
![example event parameter](https://github.com/KaT0819/github-action-test/actions/workflows/github-actions-demo.yml/badge.svg?event=pull_request)

## クイックスタート
[GitHub Actions のクイックスタート](https://docs.github.com/ja/actions/quickstart)

## ワークフローテンプレート

クイックスタートより抜粋
```
GitHubは、カスタマイズして独自の継続的インテグレーションワークフローを作成できる、
事前設定されたワークフローテンプレートを提供します。
GitHubはコードを分析し、そのリポジトリで役に立つであろうCIテンプレートを提示します。
たとえばリポジトリにNode.jsのコードが含まれているなら、Node.jsプロジェクトのためのサジェッションが提示されます。
ワークフローテンプレートは、カスタムワークフローの構築の出発点として利用することも、そのまま利用することもできます。
```
[ワークフローテンプレート](https://github.com/actions/starter-workflows)

## 次のステップ
```
追加したワークフロー例では、コードがブランチにプッシュされるたびに実行され、
GitHub Actions がリポジトリのコンテンツを処理できる方法が示されます。
ただし、これは GitHub Actions で可能なことの一部にすぎません。

・リポジトリには、さまざまなイベントに基づいてさまざまなジョブをトリガーする複数のワークフローを含めることができます。
・ワークフローを使用してソフトウェアテストアプリをインストールし、GitHub のランナーでコードを自動的にテストすることができます。

GitHub Actions は、アプリケーション開発プロセスのほぼすべての要素を自動化するのに役立ちます。
始める準備はできましたか？
GitHub Actions で次のステップに進む際に役立つ、以下のようなリソースを参照してください。
```

[詳細なチュートリアル](https://docs.github.com/ja/actions/learn-github-actions)

[ガイド](https://docs.github.com/ja/actions/guides)


[リファレンス](https://docs.github.com/ja/actions/reference)

[GitHub Actions のコンテキストおよび式の構文](https://docs.github.com/ja/actions/reference/context-and-expression-syntax-for-github-actions)

## メモ
アクションからのシェル実行でPermission denied  
⇒GitHub側に権限を追加する。
```
git update-index --chmod=+x ./.github/actions/hello-world-action/goodbye.sh
```

## デバッグロギングの有効化
詳細は以下  
https://docs.github.com/ja/actions/managing-workflow-runs/enabling-debug-logging  

* オーナー権限 or 管理アクセス権が必要

```
ランナーの診断ロギングの有効化
ACTIONS_RUNNER_DEBUGをtrue
ステップのデバッグロギングの有効化
ACTIONS_STEP_DEBUGをtrue
```


## おまけ
GitHub CLIのインストール
https://github.com/cli/cli#installation

コマンドリスト
```
# 最近のワークフロー実行一覧
gh run list
# 最大数を指定
gh run list --limit 5
# 指定されたワークフローの実行のみを返す
gh run list --workflow "GitHub Actions Demo"
gh run list -w "GitHub Actions Demo"

# 特定のワークフロー実行の詳細
gh run view 998035642
# 出力にジョブステップを含める
gh run view 998035642 --verbose
gh run view 998035642 -v

# 実行中の特定のジョブの詳細
gh run view --job 2982711726
gh run view -j 2982711726
# ジョブの完全なログ
gh run view --job 2982711726 --log

# ワークフローを実行(ワークフロー名だけでなくIDやファイル名でも可能)
gh workflow run "GitHub Actions Demo"
# ワークフローを無効可
gh workflow disable "GitHub Actions Demo"
# ワークフローを有効可
gh workflow enaable "GitHub Actions Demo"


# 
```
