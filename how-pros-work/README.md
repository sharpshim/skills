# how-pros-work

AI 도구를 쓰는 방식 자체를 진단하고 개선 방법을 제안하는 Agent Skill입니다.

세션에서 관찰된 현상(반복된 교정, 맥락 소실, 검증 없이 넘어가기 등)을 기법 카탈로그와 연결해서, 이름이 붙은 구체적인 개선안과 그대로 복사해 쓸 수 있는 문구를 제시합니다. 일반 채팅과 코딩 에이전트 세션 양쪽에서 동작합니다.

## 구성

```
how-pros-work/
├── SKILL.md                   진단 절차, 호출 조건, 출력 형식
└── references/
    └── techniques.md          기법 카탈로그 (필요할 때만 읽힘)
```

## 설치

이 저장소를 내려받은 위치를 `~/skills/how-pros-work`라고 가정합니다.

### Codex, Gemini CLI

두 도구가 공통으로 쓰는 상호운용 경로에 링크하면 한 번에 해결됩니다.

```bash
mkdir -p ~/.agents/skills
ln -s ~/skills/how-pros-work ~/.agents/skills/how-pros-work
```

### Claude Code

```bash
mkdir -p ~/.claude/skills
ln -s ~/skills/how-pros-work ~/.claude/skills/how-pros-work
```

### claude.ai

폴더를 zip으로 묶어서 설정 화면에서 업로드합니다. 이 환경만 자동 동기화가 되지 않으므로, 내용을 고칠 때마다 다시 올려야 합니다.

```bash
cd ~/skills && zip -r how-pros-work.zip how-pros-work
```

## 사용

"이 세션 평가해줘", "내가 더 잘 쓰는 방법 알려줘"처럼 활용 방식 자체를 물으면 호출됩니다. 작업이 일단락된 시점에 반복된 마찰이 관찰되면 스스로 짧은 제안을 덧붙이기도 합니다.

Codex에서는 `$how-pros-work`로, Claude Code에서는 `/how-pros-work`로 직접 부를 수도 있습니다.

## 개선하기

진단 결과에 동의하지 않거나 고칠 점을 발견하면, 그 자리에서 다음 형식으로 메모를 남긴 뒤 `FEEDBACK.md`에 모아 두십시오.

```
- 버전 / 환경 / 날짜
- 관찰된 문제
- 내 의견
- 제안하는 수정
```

모인 항목은 한꺼번에 반영하십시오. 하나씩 즉시 고치면 나중 의견이 앞의 수정을 뒤집어서 지침이 서로 모순된 채로 쌓입니다.
