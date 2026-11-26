# null-variable コントリビューションガイド

[English](CONTRIBUTING.md) · [한국어](CONTRIBUTING.ko.md) · [简体中文](CONTRIBUTING.zh-CN.md) · **日本語**

null-variable へのコントリビュートありがとうございます。このガイドは、Organization 内で独自の `CONTRIBUTING.md` を持たないすべてのリポジトリに適用されます。リポジトリ独自のガイドや README の Development セクションがある場合は、そちらのルールが優先されます。Issue と PR は English、한국어、中文、日本語 のいずれでも歓迎します。

## 始める前に

- バグは該当リポジトリの Issue で、再現手順とバージョンまたはコミットハッシュを書いて報告してください。
- 大きな変更（新機能、形式やプロトコルの変更、公開 API の変更）は、PR の前に Issue で相談してください。
- セキュリティ上の問題は Issue ではなく [SECURITY](SECURITY.ja.md) の手順に従ってください。

## Pull request

1. デフォルトブランチからブランチを作成します。
2. 1 つの PR には 1 つの変更だけを含めます。
3. 動作が変わる場合はテストを追加または修正し、その動作を説明するドキュメントも更新します。
4. プッシュする前に、リポジトリの CI チェック（フォーマット、lint、テスト）をローカルで実行します。通すためにチェックを無効化したりスキップしたりしないでください。
5. 契約（API、プロトコル、スキーマ）を共有する複数のリポジトリにまたがる変更では、契約を所有するリポジトリを先にリリースし、その後で利用側を更新します。
6. CI が通ってからレビューを始めます。

## プロジェクトごとのチェック

| プロジェクト | リポジトリ | 通過が必要なチェック |
|---|---|---|
| Proxelo | [`proxelo`](https://github.com/null-variable/proxelo) (Go) | `gofmt -l .` の出力なし、`go vet ./...`、`go test -race ./...` |
| Proxelo | [`proxelo-proxy`](https://github.com/null-variable/proxelo-proxy) (Rust) | `cargo fmt --check`、`cargo clippy -- -D warnings`、`cargo test` |
| Proxelo | [`proxelo-api`](https://github.com/null-variable/proxelo-api) (Protobuf) | `buf lint`、`buf breaking`、`buf generate` 後に `gen/go` をコミット |

新しいプロジェクトを公開したら、この表に行を追加します。

## ライセンス

コントリビュートされたコードは、コントリビュート先リポジトリのライセンスで配布されます。
