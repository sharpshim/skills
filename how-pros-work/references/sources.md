# 출처 목록

진단 중에 명령어, 설정값, 기능의 현재 상태를 확인할 때 조회하는 문서 목록입니다. 웹 검색으로 아무 글이나 찾는 대신, 이 목록에서 해당 도구의 문서를 골라 직접 조회하십시오.

마지막 확인일: 2026-09-13

## 목차

1. [등급별 사용 규칙](#등급별-사용-규칙)
2. [1등급: 공식 문서](#1등급-공식-문서)
3. [2등급: 공식 엔지니어링 글](#2등급-공식-엔지니어링-글)
4. [3등급과 4등급](#3등급과-4등급)
5. [조회 요령](#조회-요령)

---

## 등급별 사용 규칙

| 등급 | 종류 | 사용할 수 있는 용도 |
|---|---|---|
| 1등급 | 도구 제작사의 공식 문서 | 명령어, 설정값, 기능 유무를 판단하는 **유일한** 근거 |
| 2등급 | 도구 제작사의 엔지니어링 글, 연구 보고서 | 기법이 효과가 있는 원리를 설명하는 근거 |
| 3등급 | 실무자가 쓴 글, 공개 저장소의 지침 문서 | 「외부 사례」로 표시해서 보여 주는 참고 자료. 단독 근거로 쓰지 않음 |
| 4등급 | 커뮤니티 게시물 (HN, Reddit, X 등) | 진단에 쓰지 않음. 카탈로그를 관리할 때 기법 후보를 발굴하는 신호로만 사용 |

- 명령어나 설정값을 3등급 이하 자료에서 가져오지 마십시오. 오래된 글에는 이미 사라진 옵션이 그대로 남아 있습니다.
- 1등급 문서와 다른 자료가 서로 어긋나면 1등급 문서를 따릅니다.

---

## 1등급: 공식 문서

### Claude Code

- 색인: https://code.claude.com/docs/llms.txt
- 페이지 URL 끝에 `.md`를 붙이면 HTML보다 훨씬 짧은 원문을 받을 수 있습니다.

| 확인할 내용 | 문서 |
|---|---|
| 슬래시 명령 (`/compact`, `/btw`, `/rewind`, `/goal` 등) | https://code.claude.com/docs/en/commands.md |
| CLI 플래그 | https://code.claude.com/docs/en/cli-reference.md |
| settings.json 키 (`bashOutputMaxChars` 등) | https://code.claude.com/docs/en/settings-reference.md |
| 비용과 토큰 절감 | https://code.claude.com/docs/en/costs.md |
| 권장 작업 방식 | https://code.claude.com/docs/en/best-practices.md |
| 변경 기록 | https://code.claude.com/docs/en/changelog.md |

### Codex CLI

- 색인: https://developers.openai.com/codex/llms.txt (현재 https://learn.chatgpt.com/docs/llms.txt 로 리디렉션됨)

| 확인할 내용 | 문서 |
|---|---|
| 슬래시 명령 | https://learn.chatgpt.com/docs/developer-commands.md?surface=cli |
| 설정 파일 키 | https://learn.chatgpt.com/docs/config-file/config-reference.md |
| AGENTS.md 작성 | https://learn.chatgpt.com/docs/agent-configuration/agents-md.md |

변경 기록은 색인에서 찾으십시오.

### Gemini CLI

- 문서: https://geminicli.com/docs/
- 무료 등급과 Google One 사용자의 Gemini CLI는 2026-06-18에 Antigravity CLI로 대체되었다고 공지되어 있습니다. 사용자가 어느 쪽을 쓰는지 먼저 확인하십시오.

| 확인할 내용 | 문서 |
|---|---|
| 명령 | https://geminicli.com/docs/reference/commands/ |
| 설정 | https://geminicli.com/docs/reference/configuration/ |
| GEMINI.md 작성 | https://geminicli.com/docs/cli/gemini-md/ |
| 변경 기록 | https://geminicli.com/docs/changelogs/latest/ |

---

## 2등급: 공식 엔지니어링 글

- Anthropic, "Effective context engineering for AI agents"
  https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents
- Anthropic, "Writing effective tools for AI agents"
  https://www.anthropic.com/engineering/writing-tools-for-agents

---

## 3등급과 4등급

고정 목록을 두지 않습니다. 사용자의 작업 영역에 맞는 사례가 필요할 때만 다음 검색어 틀로 찾으십시오.

- `"<프레임워크 이름>" CLAUDE.md site:github.com`
- `"<프레임워크 이름>" AGENTS.md site:github.com`
- `"<도구 이름>" hooks "<검증 명령>"`

공개 저장소에 실제로 커밋된 지침 문서는 블로그 요약보다 신뢰할 만한 자료입니다. 그래도 제안에 넣을 때는 「외부 사례」로 표시해서 카탈로그 기법과 구분하십시오.

---

## 조회 요령

- 색인 파일(llms.txt)을 먼저 읽고 필요한 페이지 하나만 여십시오. 문서 사이트 전체를 훑지 마십시오.
- 조회에 실패하면 URL을 추측해서 다시 시도하지 말고, 이 목록의 색인으로 돌아가십시오.
- 이 목록의 URL이 더 이상 열리지 않으면, 진단을 마친 뒤 사용자에게 알리고 `FEEDBACK.md`에 기록할 항목으로 제안하십시오.
