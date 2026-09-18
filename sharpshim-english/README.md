# sharpshim-english

평소 작업을 하면서 영어에 노출되게 하는 Agent Skill입니다.

한국어 답변은 그대로 두고, 문장 뒤 괄호에 영어 번역을 붙입니다. 영어를 건너뛰어도 내용을 읽는 데 지장이 없으므로, 따로 공부 시간을 내지 않고 하던 일을 하면서 씁니다.

## 어떻게 보이는가

아래는 같은 답변을 레벨별로 출력한 것입니다. 원본은 이렇습니다.

> 테스트가 실패한 원인을 찾았습니다. `targetServer.test.ts`가 `dist/server/app.js`의 존재를 검사하는데, 저장소를 새로 받은 직후에는 그 파일이 없습니다.
>
> 환경 문제가 아닙니다. 빌드 선행 조건입니다. `pnpm build`를 먼저 돌렸더니 27개 테스트가 모두 통과했습니다.
>
> 다만 빌드 산출물의 존재에 의존하는 테스트는 실패했을 때 원인이 환경 탓인지 코드 탓인지 흐리기 때문에, 장기적으로는 검사 방식을 바꾸는 편이 낫다고 봅니다.

**A1** — 아주 짧은 문장을 골라 기초 어휘로 옮깁니다.

> 테스트가 실패한 원인을 찾았습니다. `targetServer.test.ts`가 `dist/server/app.js`의 존재를 검사하는데, 저장소를 새로 받은 직후에는 그 파일이 없습니다.
>
> 환경 문제가 아닙니다. (This is not an environment problem.) 빌드 선행 조건입니다. `pnpm build`를 먼저 돌렸더니 27개 테스트가 모두 통과했습니다.
>
> 다만 빌드 산출물의 존재에 의존하는 테스트는 실패했을 때 원인이 환경 탓인지 코드 탓인지 흐리기 때문에, 장기적으로는 검사 방식을 바꾸는 편이 낫다고 봅니다.

**B1** — 중간 길이의 설명 문장을 골라 관계절이 들어간 영어로 옮깁니다.

> 테스트가 실패한 원인을 찾았습니다. (I found what was causing the test to fail.) `targetServer.test.ts`가 `dist/server/app.js`의 존재를 검사하는데, 저장소를 새로 받은 직후에는 그 파일이 없습니다.
>
> 환경 문제가 아닙니다. 빌드 선행 조건입니다. `pnpm build`를 먼저 돌렸더니 27개 테스트가 모두 통과했습니다.
>
> 다만 빌드 산출물의 존재에 의존하는 테스트는 실패했을 때 원인이 환경 탓인지 코드 탓인지 흐리기 때문에, 장기적으로는 검사 방식을 바꾸는 편이 낫다고 봅니다.

**C2** — 가장 길고 뉘앙스가 실린 문장을 골라 구어 관용 표현으로 옮깁니다.

> 테스트가 실패한 원인을 찾았습니다. `targetServer.test.ts`가 `dist/server/app.js`의 존재를 검사하는데, 저장소를 새로 받은 직후에는 그 파일이 없습니다.
>
> 환경 문제가 아닙니다. 빌드 선행 조건입니다. `pnpm build`를 먼저 돌렸더니 27개 테스트가 모두 통과했습니다.
>
> 다만 빌드 산출물의 존재에 의존하는 테스트는 실패했을 때 원인이 환경 탓인지 코드 탓인지 흐리기 때문에, 장기적으로는 검사 방식을 바꾸는 편이 낫다고 봅니다. (That said, hanging a test on whether a build artifact happens to be sitting there muddies the one signal it's supposed to give you — is this broken, or is my machine just cold? — so I'd rather we reworked that check before it bites someone on a fresh clone.)

레벨은 두 가지를 정합니다. **어떤 문장을 고르는가**와 **그 문장을 어떤 영어로 옮기는가**입니다. 자세한 기준은 `SKILL.md`의 표에 있습니다.

## 구성

```
sharpshim-english/
├── SKILL.md    레벨별 기준, 발동 조건, 지켜야 할 것
└── README.md
```

## 설치

스킬은 `SKILL.md` 하나로 동작합니다. 이 README는 읽는 사람을 위한 것이라 설치하지 않아도 됩니다.

### 파일 하나만 받기

가장 간단한 방법입니다. 저장소를 클론하지 않아도 되고 git도 필요 없습니다.

```bash
mkdir -p ~/.claude/skills/sharpshim-english
curl -o ~/.claude/skills/sharpshim-english/SKILL.md \
  https://raw.githubusercontent.com/sharpshim/skills/main/sharpshim-english/SKILL.md
```

디렉터리 경로만 도구에 맞게 바꾸면 됩니다.

| 도구 | 경로 |
|---|---|
| Claude Code | `~/.claude/skills/sharpshim-english/` |
| Codex, Gemini CLI | `~/.agents/skills/sharpshim-english/` |

`curl`을 쓰기 어려우면 [SKILL.md](SKILL.md)를 열어 내용을 복사한 뒤, 편집기로 같은 경로에 파일을 만들어 붙여 넣어도 결과는 같습니다.

**이 방식은 갱신이 자동으로 되지 않습니다.** 고쳐진 내용을 받으려면 같은 명령을 다시 실행하십시오.

### 저장소를 클론해 링크하기

고친 내용을 `git pull`로 받고 싶을 때 씁니다. 내려받은 위치를 `~/skills/sharpshim-english`라고 가정합니다.

```bash
# Claude Code
mkdir -p ~/.claude/skills
ln -s ~/skills/sharpshim-english ~/.claude/skills/sharpshim-english

# Codex, Gemini CLI (두 도구가 함께 쓰는 상호운용 경로)
mkdir -p ~/.agents/skills
ln -s ~/skills/sharpshim-english ~/.agents/skills/sharpshim-english
```

### claude.ai

폴더를 zip으로 묶어서 설정 화면에서 업로드합니다. 이 환경만 자동 동기화가 되지 않으므로, 내용을 고칠 때마다 다시 올려야 합니다.

```bash
cd ~/skills && zip -r sharpshim-english.zip sharpshim-english
```

### ChatGPT, Gemini 웹처럼 스킬 기능이 없는 도구

`SKILL.md`의 본문은 그냥 마크다운 지침입니다. 스킬을 인식하는 기능이 없어도, 그 내용을 **지침이 유지되는 자리**에 붙여 넣으면 같은 방식으로 동작합니다.

- **ChatGPT:** 프로젝트를 하나 만들고 그 프로젝트의 지침란에 붙여 넣습니다. 모든 대화에 적용하려면 사용자 지정 지침란에 넣어도 됩니다.
- **Gemini 웹:** Gem을 하나 만들고 지침란에 붙여 넣습니다.

두 도구 모두 메뉴 이름이 바뀔 수 있으니, "대화마다 반복되는 지침을 저장하는 자리"를 찾으면 됩니다. 한 번 쓰고 마는 것이라면 대화 첫 메시지로 붙여 넣어도 그 대화 안에서는 동작합니다.

## 사용

말에 **"샤프심 영어"**가 들어 있으면 레벨을 묻습니다. "샤프심 영어 교실 시작", "샤프심 영어 교실", "샤프심 영어"가 모두 해당하며 띄어쓰기는 가리지 않습니다. "샤프심"이 없으면 발동하지 않습니다. 영어 학습을 화제로 꺼낸 것과 실제로 시작하려는 것을 가르기 위해서입니다. 레벨을 답하면 그때부터 모든 답변에 번역이 붙습니다.

레벨을 바꿀 때는 **「영어」, 「레벨」, `level` 가운데 하나를 넣거나 레벨 표기를 직접 말합니다.** "B1으로 바꿔"처럼 쓰면 됩니다. "너무 어렵네요" 같은 말로는 바뀌지 않습니다. 작업이 어렵다는 뜻일 때가 훨씬 많기 때문입니다.

"샤프심 영어 교실 그만", "영어 그만 섞어"처럼 멈추라는 뜻이면 표현을 가리지 않고 멈춥니다. 시작과 달리 잘못 멈춰도 손해가 작기 때문입니다.

메모리 기능이 있는 환경이라면 레벨이 저장되어 다음 세션부터는 묻지 않습니다. 없어도 정상 동작하며, 세션마다 레벨을 답하면 됩니다.

## 주의

**정확성이 영어보다 우선입니다.** 설계 결정, 오류의 원인, 위험 경고처럼 잘못 읽히면 손해가 나는 자리에는 번역을 붙이지 않습니다. 코드와 파일 경로, 명령어도 건드리지 않습니다.

**쉽게 옮기다가 뜻이 달라지면 그 문장은 건너뜁니다.** 그래서 레벨에 맞는 문장이 없는 답변에는 번역이 하나도 붙지 않을 수 있습니다. 정상입니다.
