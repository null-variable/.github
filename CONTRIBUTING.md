# Contributing to null-variable

**English** · [한국어](CONTRIBUTING.ko.md) · [简体中文](CONTRIBUTING.zh-CN.md) · [日本語](CONTRIBUTING.ja.md)

Thank you for contributing to null-variable. This guide applies to every repository in the organization that does not have its own `CONTRIBUTING.md`. When a repository has its own guide or a Development section in its README, those rules come first. Issues and pull requests are welcome in English, 한국어, 中文 or 日本語.

## Before you start

- Report a bug as an Issue in the affected repository, with steps to reproduce and the version or commit hash.
- Discuss large changes in an Issue before opening a pull request: new features, format or protocol changes, or public API changes.
- Report security problems through [SECURITY.md](SECURITY.md), not Issues.

## Pull requests

1. Branch from the default branch.
2. Keep one change per pull request.
3. Add or update tests when behavior changes, and update documentation that describes it.
4. Run the repository's CI checks (format, lint, test) locally before pushing. Do not disable or skip checks to make them pass.
5. When a change spans repositories that share a contract (an API, protocol or schema), release the repository that owns the contract first, then update its consumers.
6. Review starts once CI passes.

## Project-specific checks

| Project | Repository | Checks that must pass |
|---|---|---|
| Proxelo | [`proxelo`](https://github.com/null-variable/proxelo) (Go) | `gofmt -l .` prints nothing, `go vet ./...`, `go test -race ./...` |
| Proxelo | [`proxelo-proxy`](https://github.com/null-variable/proxelo-proxy) (Rust) | `cargo fmt --check`, `cargo clippy -- -D warnings`, `cargo test` |
| Proxelo | [`proxelo-api`](https://github.com/null-variable/proxelo-api) (Protobuf) | `buf lint`, `buf breaking`, commit `gen/go` after `buf generate` |

New projects add their rows here when they are published.

## License

Contributions are released under the license of the repository they are made to.
