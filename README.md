---
type: guide
status: active
tags:
  - second-brain
  - git
  - markdown
---

# Second Brain

Git으로 관리하는 Markdown 기반 세컨드 브레인입니다.

이 저장소의 원본은 앱이나 데이터베이스가 아니라 `.md`, `.base`, `.canvas` 파일입니다. Obsidian은 편집기이자 시각화 도구로 사용하고, Git은 변경 이력과 백업을 담당합니다.

## 핵심 원칙

- Markdown 파일이 진짜 원본입니다.
- Git으로 모든 중요한 변경을 추적합니다.
- Obsidian은 데스크톱/모바일 인터페이스로 사용합니다.
- 그래프는 `[[wikilink]]`, 태그, YAML properties로 만듭니다.
- 구조화된 목록은 Obsidian Bases를 우선 사용합니다.
- 이 vault는 사람이 직접 쓰기보다 에이전트가 자주 정리하고 연결하는 용도로 설계합니다.

## 시작점

- 메인 대시보드: [[HOME]]
- 세컨드 브레인 지도: [[MOC-second-brain]]
- 첫 프로젝트: [[second-brain]]
- Git 운영 메모: [[git-vault-workflow]]

## 폴더 구조

```text
00-inbox/       빠른 캡처, 아직 정리 전인 생각
01-daily/       일간 목표, TODO, 로그, 회고
02-dev-notes/   개발 지식, 디버깅, 아키텍처 메모
03-projects/    진행 중인 프로젝트
04-areas/       장기적으로 관리할 영역
05-resources/   참고자료, 설정, 외부 지식 요약
06-snippets/    명령어, 코드 조각, 반복 패턴
07-decisions/   ADR 형식의 결정 기록
08-maps/        MOC, Bases, Canvas 시각화
90-templates/   재사용 템플릿
99-archive/     종료되었거나 비활성화된 자료
assets/         이미지와 첨부 파일
skills/         이 vault 전용 에이전트 스킬
```

## 운영 흐름

1. Obsidian에서 이 저장소를 vault로 엽니다.
2. [[HOME]]을 시작 화면처럼 사용합니다.
3. 하루 기록은 `01-daily/YYYY-MM-DD.md`에 남깁니다.
4. 개발 지식은 `02-dev-notes/`, 프로젝트는 `03-projects/`, 결정 기록은 `07-decisions/`로 옮깁니다.
5. 중요한 노트는 관련 노트와 `[[wikilink]]`로 연결합니다.
6. 의미 있는 변경이 쌓이면 Git commit/push 합니다.

## Obsidian 사용 기준

권장 테마:

- AnuPpuccin

주요 Core Plugin:

- Bases
- Graph view
- Canvas
- Daily notes
- Templates
- Properties
- Backlinks
- Outgoing links
- Bookmarks
- File recovery

주요 Community Plugin:

- Style Settings
- Tasks
- Templater
- Base Board
- Excalidraw
- Omnisearch
- QuickAdd

## 에이전트용 문서

에이전트는 작업 전에 아래 문서를 확인합니다.

- `AGENTS.md`: 모든 에이전트 공통 규칙
- `CLAUDE.md`: Claude 전용 간단 지침
- `skills/second-brain-vault/SKILL.md`: 이 vault를 관리하는 내부 스킬

기본 방침은 단순합니다. 새 시스템을 만들지 말고, Markdown 원본을 잘 정리하고, 링크와 properties로 다시 찾기 쉬운 지식 그래프를 만듭니다.

## Git

기본 작업:

```bash
git status --short --branch
git add .
git commit -m "Update second brain"
git push
```

주의:

- `.obsidian/plugins/`, `.obsidian/themes/`, workspace 상태 파일은 추적하지 않습니다.
- Obsidian 설정 중 재현에 필요한 가벼운 JSON만 추적합니다.
- 모바일에서는 보기와 가벼운 작성 위주로 사용하고, Git 충돌 해결은 데스크톱에서 처리하는 편이 안전합니다.

