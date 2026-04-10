# UI Action Designer

**Figma에서 HTML로: 디자인 시스템 추출, PRD 작성, 액션과 테스크 생성, 4방향 설계안 산출.**

> 🇺🇸 [English README](./README.md)

## 사전 요구사항

- **Claude Cowork 또는 Claude Code** 환경
- **Figma** 접근 — 디자인 시스템 추출 권장

## 목적

ui-action-designer는 디자인과 개발 간의 단절을 8단계 파이프라인으로 연결합니다: 디자인 시스템 추출, PRD 작성 활성화, 액션과 테스크 추출, SHE 필터 적용, 플랫폼 패턴 주입, 4방향 설계안 생성, PRD 일관성 검증.

## 사용 시점 및 방법

실행 가능한 사양과 코드가 되어야 하는 Figma 설계나 컨셉이 있을 때 배포하세요. 파이프라인: 설계 → DS 추출 → PRD 연동 → 액션-테스크 추출 → SHE 필터 → 지식 주입 → 4방향 설계안 → HTML 산출.

## 사용 예시

| 상황 | 프롬프트 | 결과 |
|---|---|---|
| 설계 인수 | `"Figma 설계를 PRD와 4가지 구현 방향으로"` | DS 추출→PRD→액션/테스크→SHE→4가지 설계안 (HTML + 일관성 확인) |
| PRD 업데이트 | `"새 설계 방향 기반 PRD 업데이트"` | 설계 델타→PRD 업데이트→테스크 재추출→4방향 설계안→검증 |
| 처음부터 PRD | `"이 컴포넌트용 간단한 PRD 작성"` | 팩터 선택→PRD→DS 추출→4가지 설계안→HTML 프로토타입 |

## 핵심 기능

- 8단계 파이프라인: 입력 → DS 추출 → 분석 → 액션-테스크 → SHE → 지식 → 4가지 설계안 → HTML
- 팩터 선택을 통한 PRD 작성 (필수/선택/있으면 좋음)
- 액션-테스크 계층: 액션 (기능) > 테스크 (단계)
- SHE 필터: 심플→숨김→구현
- iOS/Material Design 3 패턴 주입
- 4방향 설계안: 실용적, 우아함, 최소형, 풍부한 기능
- PRD 일관성 검증

## 연관 스킬

- **[human-skill](https://github.com/jasonnamii/human-skill)** — PRD 설계를 위한 사용자 행동 패턴 정보
- **[hit-skill](https://github.com/jasonnamii/hit-skill)** — 소비자 기능의 전파 및 영향 패턴
## 설치

```bash
git clone https://github.com/jasonnamii/ui-action-designer.git ~/.claude/skills/ui-action-designer
```

## 업데이트

```bash
cd ~/.claude/skills/ui-action-designer && git pull
```

`~/.claude/skills/`에 배치된 스킬은 Claude Code 및 Cowork 세션에서 자동으로 사용할 수 있습니다.

## Cowork 스킬 생태계

25개 이상의 커스텀 스킬 중 하나입니다. 전체 카탈로그: [github.com/jasonnamii/cowork-skills](https://github.com/jasonnamii/cowork-skills)

## 라이선스

MIT 라이선스 — 자유롭게 사용, 수정, 공유하세요.
