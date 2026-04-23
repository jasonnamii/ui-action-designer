# tokens.md — UI Action Designer 공통 토큰 인덱스

html-skill-refactor spine 4블록 중 **tokens**. 토큰·프로토콜 상수 인덱스.

## §1. DS 토큰 카탈로그 (§② DS 추출)

| 토큰군 | 추출 대상 | 상세 스포크 |
|--------|-----------|------------|
| 색상 | primary·surface·text·border·state 계열 | `ios26-patterns.md`·`md3-patterns.md` |
| 타이포 | scale·weight·line-height·letter-spacing | `ios26-patterns.md`·`md3-patterns.md` |
| 간격 | 4/8pt grid·gutter·section padding | `ios26-patterns.md` |
| Radius | card·button·input·modal | `ios26-patterns.md` |
| Shadow/Elevation | level 1~5·MD3 tonal elevation | `md3-patterns.md` |
| 컴포넌트 | Button·Input·Card·Tab·Sheet·Toast | `ios26-patterns.md`·`md3-patterns.md` |

## §2. PRD 토큰 (§③ 분석)

| 토큰 | 역할 | 상세 |
|------|------|------|
| Action | 시스템 기능 단위 (KPI) | SKILL.md §용어 |
| Task | 유저 수행 단계 (퍼널) | SKILL.md §용어 |
| A/B/C 경로 | PRD 있음/없음/역추론 | `prd-frames.md` |

## §3. SHE 노출 등급 (§⑤)

| 등급 | 정의 | 트리거 |
|------|------|--------|
| L1 Surface | 항상 노출 | "없으면 Action 자체 불가" YES |
| L2 Triggered | 행동·상태 뒤 등장 | 탭·스와이프·롱프레스·컨텍스트 |
| L3 Hidden | 심층 메뉴·설정 | 명시 경로만 |

→ 상세: `she-protocol.md`

## §4. UX_GATE 15원리 (§⑤-b)

Nielsen 10 (N1~N10) + Norman 5 (D1~D5). 15개 중 **12개+ PASS** 필수. 상세: `ux-principles.md#A` + `#B`.

## §5. 4방향 제안 축 (§⑦)

| 방향 | 축 |
|------|-----|
| 표준 | 플랫폼 가이드라인 기본형 |
| iOS26 | Apple HIG + liquid glass·symbol animation |
| AOS | MD3 Expressive + dynamic color |
| 창의적 | 토큰 범위 내 재조합·계층·흐름 혁신 |

→ 상세: `proposal-rules.md`·`ios26-patterns.md`·`md3-patterns.md`

## §6. Figma MCP 재현도

| 소스 | 재현도 |
|------|--------|
| Figma MCP (`get_design_context`+`get_screenshot`) | 95%+ |
| DevMode | 90%+ |
| PDF | 70~80% |
| 스크린샷 | 60~75% |

→ 상세: SKILL.md §①
