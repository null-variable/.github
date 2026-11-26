# null-variable 기여 가이드

[English](CONTRIBUTING.md) · **한국어** · [简体中文](CONTRIBUTING.zh-CN.md) · [日本語](CONTRIBUTING.ja.md)

null-variable에 기여해 주셔서 고맙습니다. 이 문서는 조직 안에서 별도 `CONTRIBUTING.md`가 없는 모든 저장소에 적용됩니다. 저장소에 자체 가이드나 README의 Development 절이 있으면 그 규칙이 먼저입니다. Issue와 PR은 English, 한국어, 中文, 日本語 모두 환영합니다.

## 시작하기 전에

- 버그는 해당 저장소에 재현 방법과 버전 또는 커밋 해시를 적어 Issue로 올려 주세요.
- 큰 변경(새 기능, 형식·프로토콜 변경, 공개 API 변경)은 PR 전에 Issue로 먼저 논의해 주세요.
- 보안 문제는 Issue가 아니라 [SECURITY](SECURITY.ko.md) 절차를 따릅니다.

## Pull request

1. 기본 브랜치에서 브랜치를 만듭니다.
2. 한 PR에는 한 가지 변경만 담습니다.
3. 동작이 바뀌면 테스트를 추가하거나 고치고, 그 동작을 설명하는 문서도 갱신합니다.
4. 푸시하기 전에 저장소의 CI 검사(포맷, 린트, 테스트)를 로컬에서 실행합니다. 통과시키려고 검사를 끄거나 건너뛰지 않습니다.
5. 계약(API, 프로토콜, 스키마)을 공유하는 여러 저장소에 걸친 변경은 계약을 소유한 저장소를 먼저 릴리스하고, 그다음 사용하는 저장소를 갱신합니다.
6. CI가 통과해야 리뷰를 시작합니다.

## 프로젝트별 검사

| 프로젝트 | 저장소 | 통과해야 하는 검사 |
|---|---|---|
| Proxelo | [`proxelo`](https://github.com/null-variable/proxelo) (Go) | `gofmt -l .` 결과 없음, `go vet ./...`, `go test -race ./...` |
| Proxelo | [`proxelo-proxy`](https://github.com/null-variable/proxelo-proxy) (Rust) | `cargo fmt --check`, `cargo clippy -- -D warnings`, `cargo test` |
| Proxelo | [`proxelo-api`](https://github.com/null-variable/proxelo-api) (Protobuf) | `buf lint`, `buf breaking`, `buf generate` 후 `gen/go` 커밋 |

새 프로젝트를 공개하면 이 표에 행을 추가합니다.

## 라이선스

기여한 코드는 기여한 저장소의 라이선스로 배포됩니다.
