# Hermes Contribution Flow

**비개발자의 Slack 요청을 검토 가능한 draft PR로 만드는 Hermes 스킬입니다.**

요청자는 원하는 동작과 실제 결과를 확인하고, Alex(Hermes)는 구현·검증·독립 리뷰를 준비합니다. 개발자는 기술 검토와 병합을 맡습니다. Alex라는 이름은 바꿔도 됩니다.

```text
요청 확인 → 구현·검사 → 독립 리뷰 → 요청자 결과 확인 → draft PR → 개발자 검토
```

- 문구·국소 스타일: 가벼운 검사와 리뷰 1개
- 기능 변경: 설계·흐름 / 구현·검증 리뷰어 2개
- 결제·권한·중요 데이터: 구현 전에 담당자 확인
- 요청자에게는 미리보기와 해볼 행동만, 개발자에게는 핵심 코드와 검증 근거
- **병합·자동 병합·배포는 하지 않습니다.**

## 설치 — Hermes에게 이 문장을 보내세요

```text
https://github.com/joonseong11/hermes-contribution-flow 의 README를 읽고
alex-contribution-flow 스킬을 이 Slack 에이전트가 사용하는 Hermes 프로필에 설치해줘.
설치 후 스킬 내용을 다시 읽고 인식되는지 확인해줘.
지금은 설치만 하고 코드 변경이나 PR 생성은 하지 마.
```

직접 설치하려면 **Alex가 실행되는 환경·프로필에서**:

```bash
hermes skills install https://raw.githubusercontent.com/joonseong11/hermes-contribution-flow/main/SKILL.md
```

Hermes의 설치 검사나 확인 요청이 나오면 내용을 확인해 진행하세요. 검사를 우회하는 옵션은 필요하지 않습니다. 명령을 지원하지 않는 버전이면 `hermes skills install --help`와 아래 공식 문서를 확인하세요.

스킬은 **이 저장소의 `SKILL.md` 한 파일**로 동작합니다. 별도 플러그인 서버나 스크립트 실행이 필요하지 않습니다.

## 사용

설치 후 Alex에게:

```text
alex-contribution-flow 스킬을 사용해서
[대상 저장소]의 예약 목록에 탑승일 필터를 추가해줘.
처음에는 전체가 보이고, 날짜를 지우면 전체로 돌아오면 좋겠어.
```

Hermes 명령 입력을 지원하는 환경에서는 `/alex-contribution-flow 요청 내용`으로도 호출할 수 있습니다. 일반 요청에도 항상 적용하려면 운영자가 Alex의 기존 지침에 다음 한 줄을 추가하세요.

> 비개발자의 코드 변경 요청에는 alex-contribution-flow 스킬을 먼저 읽고 따른다. 병합·배포는 개발 담당자가 수행한다.

설치만으로 기존 에이전트 지침이나 권한이 바뀌지는 않습니다.

## 운영자가 처음 확인할 것

1. Alex가 접근할 저장소와 작업 브랜치·PR 생성 권한
2. 리뷰용 서브에이전트 실행 가능 여부
3. 테스트·미리보기 환경과 기술 검토 담당자

설치 후 먼저 작은 문구 수정으로 시험하세요. 요청 확인, 리뷰 결과, 미리보기, 요청자의 확인, draft PR까지 확인하면 됩니다. 기능 변경에서는 두 리뷰어의 결과가 모두 있어야 합니다. 리뷰 실패나 접근 불가는 통과로 처리하지 않습니다.

실제 Alex 환경에서의 설치·Slack 동작·서브에이전트 실행은 운영 환경에서 확인해야 합니다. 이 저장소는 절차를 제공하며 GitHub 권한 제한을 대신하지 않습니다.

## 파일과 공식 문서

- [SKILL.md](SKILL.md): 설치되는 전체 작업 절차
- [Hermes 스킬 설치·사용](https://hermes-agent.nousresearch.com/docs/user-guide/features/skills/)
- [Hermes 서브에이전트](https://hermes-agent.nousresearch.com/docs/user-guide/features/delegation/)

이 스킬은 `feature-flow`에서 논의한 원칙을 비개발자용으로 구성한 독립 배포본입니다. 다른 로컬 스킬 설치는 필요 없습니다.
