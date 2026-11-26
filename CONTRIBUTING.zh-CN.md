# null-variable 贡献指南

[English](CONTRIBUTING.md) · [한국어](CONTRIBUTING.ko.md) · **简体中文** · [日本語](CONTRIBUTING.ja.md)

感谢你为 null-variable 做出贡献。本指南适用于本组织中所有没有单独 `CONTRIBUTING.md` 的仓库。如果仓库有自己的指南或 README 中的 Development 部分，则以其规则为准。Issue 和 PR 可以使用 English、한국어、中文 或 日本語。

## 开始之前

- 提交 bug 时，请在受影响的仓库中创建 Issue，写明复现步骤以及版本或 commit hash。
- 较大的变更（新功能、格式或协议变更、公开 API 变更）请先在 Issue 中讨论，再提交 PR。
- 安全问题请按照 [SECURITY](SECURITY.zh-CN.md) 的流程报告，不要提交 Issue。

## Pull request

1. 从默认分支创建分支。
2. 每个 PR 只包含一项变更。
3. 行为发生变化时，请添加或更新测试，并更新描述该行为的文档。
4. 推送前在本地运行仓库的 CI 检查（格式、lint、测试）。不要为了通过而关闭或跳过检查。
5. 当变更涉及共享同一契约（API、协议或 schema）的多个仓库时，请先发布拥有该契约的仓库，再更新使用它的仓库。
6. CI 通过后才会开始评审。

## 各项目的检查

| 项目 | 仓库 | 必须通过的检查 |
|---|---|---|
| Proxelo | [`proxelo`](https://github.com/null-variable/proxelo) (Go) | `gofmt -l .` 无输出、`go vet ./...`、`go test -race ./...` |
| Proxelo | [`proxelo-proxy`](https://github.com/null-variable/proxelo-proxy) (Rust) | `cargo fmt --check`、`cargo clippy -- -D warnings`、`cargo test` |
| Proxelo | [`proxelo-api`](https://github.com/null-variable/proxelo-api) (Protobuf) | `buf lint`、`buf breaking`，执行 `buf generate` 后提交 `gen/go` |

新项目公开后会在此表中添加对应的行。

## 许可证

贡献的代码将以所贡献仓库的许可证发布。
