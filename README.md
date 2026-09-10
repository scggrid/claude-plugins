# claude-plugins

팀에서 함께 쓰는 Claude Code Skill 모음입니다. Plugin 하나(`scg`)에 Skill을 모읍니다. 저장소: https://github.com/scggrid/claude-plugins

## 설치

Claude Code에서 두 줄을 차례로 입력합니다.

```
/plugin marketplace add scggrid/claude-plugins
/plugin install scg@scg-plugins
```

새 세션을 열면 Skill이 `/scg:이름`으로 보입니다.

## Skill

| 이름 | 사용 법 | 하는 일 |
|---|---|---|
| explain-diff | `/scg:explain-diff` | 지금 바뀐 코드를 쉬운 말로 설명합니다. 무엇이 달라지는지, 어디가 바뀌었는지, 확인할 것 하나. |
| explain-result | `/scg:explain-result` | 방금 받은 답변·명령을 실행하면 어떻게 되는지 설명합니다. 지금 상태 → 실행하면 하는 일 → 달라지는 것 → 결과값. |
| ui-copy-confirm | 자동 (또는 `/scg:ui-copy-confirm`) | 화면에 보이는 한글 문구(placeholder, 라벨, 에러 메시지 등)를 코드에 쓰기 전에, 기존 컨벤션을 확인하고 문구 후보를 제시해 확정받습니다. |

## 업데이트

```
/plugin marketplace update scg-plugins
/plugin update scg@scg-plugins
```

## Skill 추가하기

`skill-creator` Skill이 없으면 먼저 설치합니다. 공식 마켓플레이스는 보통 이미 등록되어 있습니다.

```
/plugin marketplace add anthropics/claude-plugins-official
/plugin install skill-creator@claude-plugins-official
```

이 저장소를 열고 Claude Code에 아래를 붙여 넣습니다.

```
/skill-creator 로 skill을 만들어 줘.
Skill 이름: <영문-소문자-하이픈>
어디에 만들지: <Global 사용자용> 혹은 <프로젝트 내부>
언제 쓰는가: <한 문장>
입력: <무엇을 보고 시작하는가>
출력: <어떤 순서로 무엇을 내놓는가>
하지 말 것: <한두 개>
필요한 이유: <한 문장>

빠진 항목은 기존 Skill을 참고해서 합리적으로 가정해서 적어 줘.
하지만 답에 따라 결과가 크게 달라지는 것은 AskUserQuestion으로 한 번에 모아 물어봐.
```

만든 뒤 `.claude-plugin/plugin.json`과 `marketplace.json`의 version을 올리고 push합니다. 다른 사람은 위 업데이트 명령으로 받습니다.
