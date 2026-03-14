# Commit, Issue, and PR Writing Standards

## Usage Boundary

- 이슈 레이블, PR 레이블, 커밋 메시지, 이슈 본문, PR 본문을 작성할 때만 적용한다
- Commit Message / Issue 제목 / PR 제목은 영어로 작성한다
- Issue 본문 / PR 본문은 한글로 작성한다
- 이슈 하나에 PR 하나를 대응시킨다

## Type and Scope

- 아래 표에서 `type`을 정확히 하나 선택한다
- `scope`는 주요 변경 영역을 식별하는 데 사용한다
- `scope`는 `[a-z0-9]+` 형식의 소문자 단일 토큰으로 작성한다
- 단일 영역이 지배적이지 않을 때는 `scope`를 생략한다

| Type       | 사용 기준                       |
| ---------- | ------------------------------- |
| `feat`     | 새로운 기능                     |
| `fix`      | 버그 수정                       |
| `refactor` | 동작 변경 없는 코드 리팩토링    |
| `perf`     | 성능 개선                       |
| `docs`     | 문서 변경                       |
| `test`     | 테스트 추가 또는 수정           |
| `ci`       | CI 설정 또는 스크립트 변경      |
| `build`    | 빌드 도구 또는 의존성 변경      |
| `style`    | 로직 변경 없는 코드 스타일 수정 |
| `chore`    | 유지보수 작업                   |

## Commit Message

- `scope`가 있으면 `<type>(<scope>): <subject>`, 없으면 `<type>: <subject>` 형식을 사용한다
- `subject`는 영어 명령형, 소문자, 마침표 없이 작성한다
- `body`는 추가 맥락이 필요한 경우에만 작성하며 변경 내용과 이유를 설명한다
- 커밋 푸터는 `Refs #<issue-number>` 형식으로 작성한다
- `Closes #<issue-number>`는 PR 전용으로 예약한다

```text
<type>(<scope>): <subject>

<body>

Refs #<issue-number>
```

## Issue

- 이슈는 구현 전 작업 계획을 정의하기 위해 작성한다
- 요청 작업을 요약하는 간결한 제목을 작성한다
- 목적과 배경을 설명하는 `Goal` 섹션을 작성한다
- 실행 가능한 체크리스트 형태의 `Tasks` 섹션을 작성한다
- 관련 문서, API 명세, 디자인 링크를 포함하는 `References` 섹션을 작성한다

```text
<type>(<scope>): <subject>

## Goal
<purpose and background>

## Tasks
- [ ] ...

## References
- ...
```

## Pull Request

- PR은 구현 결과를 설명하기 위해 작성한다
- `scope`가 있으면 `<type>(<scope>): <subject> (#<issue-number>)`, 없으면 `<type>: <subject> (#<issue-number>)` 형식을 사용한다
- `type`, 선택적 `scope`, `subject` 규칙은 커밋 메시지와 동일하게 따른다
- 본문은 `Changes`, `Implementation`, `Notes` 섹션으로 구성한다
- 연결된 이슈를 닫기 위해 PR 본문에 `Closes #<issue-number>`를 작성한다

```text
<type>(<scope>): <subject> (#<issue-number>)

## Changes
- ...

## Implementation
- ...

## Notes
- ...

Closes #<issue-number>
```