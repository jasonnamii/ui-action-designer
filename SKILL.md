---
name: ui-action-designer
description: |
  UI Action Designer v1.1. 피그마→DS→PRD(파싱/작성/역추론)→Action→Task→SHE→UX_GATE→지식유입→4방향→HTML. 일반/TURBO 2모드.
  P1: UI Action, UI설계, UI제안, 피그마, figma, SHE, 화면설계, Action, Task, UI패턴, PRD, PRD작성, 터보UI, UI 터보, TURBO.
  P2: 설계해줘, 제안해줘, 분석해줘, PRD 만들어줘, 터보로 제안해줘, design, propose, turbo UI.
  P3: UI design, design system, user flow, action-task, PRD frame, product requirements, turbo UI, parallel proposal.
  P5: HTML로, 제안서로, 비교표로, PRD로.
  NOT: 디자인시스템구축·애플디자인스타일(→apple-design-style)·프로토타입코딩.
"@uses":
  - references/tokens.md
  - references/snippets.md
  - references/forbidden.md
  - references/qc.md
  - references/prd-frames.md
  - references/she-protocol.md
  - references/ux-principles.md
  - references/knowledge-injection.md
  - references/proposal-rules.md
  - references/ios26-patterns.md
  - references/md3-patterns.md
---

# UI Action Designer

UI설계·UI제안·화면설계·UI패턴·터보UI 전용 엔진 — 피그마 디자인시스템에서 Action>Task 구조로 UI 제안을 생성.

①입력→②DS추출→[토큰게이트]→③분석(PRD 3경로)→④추출→⑤SHE→[SHE게이트]→⑤-b UX_GATE→⑥지식유입→⑦제안→⑧산출

**UX 원리 허브:** `@ref: references/ux-principles.md` — Nielsen 10 + Norman 5 단일 출처. 이 스킬은 허브 §A+§B 전체 적용.

---

## 4블록 참조 구조

html-skill-refactor spine 공통. 허브형 스킬이라 **4블록=인덱스**, 풀스펙은 기존 7개 스포크에 유지.

| 블록 | 역할 | 로드 시점 |
|------|------|-----------|
| `references/tokens.md` | DS 토큰·SHE 등급·UX_GATE 15·4방향축·재현도 인덱스 | §② 진입시 1회 |
| `references/snippets.md` | 단계별·경로별·공통 프리미티브 인덱스 | 단계 전환시 |
| `references/forbidden.md` | 8단계 게이트 금지 + 용어·SHE·제안·TURBO·HTML·리서치 금지 | §⑤·§⑦·§⑧ + TURBO 발동시 |
| `references/qc.md` | 8단계 게이트 + UX_GATE 15 + 산출·PRD 정합성·설치·TURBO QC | 각 단계 종료 + §⑧ |

**로딩 규칙:** 4블록은 **인덱스**. 실제 상세는 기존 7 스포크(prd-frames·she-protocol·ux-principles·knowledge-injection·proposal-rules·ios26-patterns·md3-patterns)로 위임.

---

## ⛔ 절대 규칙

| # | 규칙 |
|---|------|
| 1 | 발동 조건 외 임의 실행 금지 |
| 2 | 출력 형식 준수 — 내부 라벨 사용자 노출 금지 |
| 3 | UP 존댓말·호칭 규칙 우선 적용 |

---

## 용어

| 용어 | 정의 | 역할 |
|------|------|------|
| **Action** | 시스템 기능 단위 (상위). 예: 구매하기, 업로드 | KPI 단위 |
| **Task** | Action 내 유저 수행 단계 (하위). 예: 옵션선택, 결제입력 | 퍼널 단위 |

Action > Task (1:N). Action=전환율 단위, Task=퍼널 단계 단위. 전 단계에서 이 정의 준수.

---

## ①입력

| 항목 | 설명 |
|------|------|
| 피그마 | PDF·이미지·URL(MCP). 재현도: MCP 95%+ > DevMode 90%+ > PDF 70~80% > 스크린샷 60~75% |
| PRD | PDF·md·텍스트. 미제공 → ③에서 B·C분기 |
| 정규화 | 형식 무관 → "화면 단위" 파싱. 1 PDF 페이지 = 1 화면 |

**Figma MCP 우선:** `get_design_context`+`get_screenshot`→화면·토큰·컴포넌트 일괄. `get_variable_defs`→변수·스타일 직참조. 미연결→폴백+"MCP 연결 시 정확도 향상" 1회 안내.

---

## ②DS 추출

토큰 추출(색상·타이포·간격·radius·shadow·elevation)→컴포넌트 인벤토리→토큰 고정(이후 전 단계 제약).

**🚪 게이트:** 토큰 테이블 → 형 승인. 토큰 오류 = 이후 전부 오류.

---

## ③분석

**경로별 로드 규칙:** A경로(PRD 있음) → prd-frames.md §파싱 섹션만. B경로(PRD 없음, 경량) → prd-frames.md §심플PRD 섹션만. C경로(역추론) → prd-frames.md §역추론 섹션만. 전체 파일 로드 금지 — 경로 판별 후 해당 섹션만 Read.

| 경로 | 조건 | 실행 |
|------|------|------|
| **A. 파싱** | PRD 있음 | `prd-frames.md` §1→§2 유형식별→매핑룰 추출→형 확인 |
| **B. PRD작성** | PRD 없음+"PRD부터" | C경량→`prd-frames.md` §3 팩터선택→심플PRD→형 확인→A복귀 |
| **C. 역추론** | PRD 없음+피그마만 | 화면 시퀀스 역추론→형 확인. ⑧§4 정합성 검증 스킵 |

**공통:** Action 식별→Task 분해→사용자 흐름 추출→Task 우선순위(핵심 vs 보조 경로)

---

## ④추출

UI 구조(레이아웃·컴포넌트·계층) + 인터랙션 패턴(탭·스와이프·롱프레스 등) 식별.

---

## ⑤SHE 필터

**SHE = Simple → Hide → Embody(Explain).** 복잡한 시스템을 "겉은 단순하게, 내부는 숨기고, 사용 시점에 드러나게" 설계하는 애플식 인터랙션 원칙. SHE는 범용 원칙(trigger-dictionary 참조)이며, 이 스킬에서는 **UI 화면에 특화된 운용**(노출 등급·숨김 트리거·이중 게이트)을 다룸. 상세 → `references/she-protocol.md`

| 단계 | 정의 | 핵심 질문 |
|------|------|----------|
| **S** (Simple) | 표면을 극도로 단순화 — 처음 보는 UI는 최소 정보만 | "없으면 Action 자체 불가?" → YES=노출 / NO=숨김. 4축 테이블 필수 |
| **H** (Hide) | 복잡한 기능·구조를 숨김 — 학습비용 제거, 인지부하 차단 | "어떤 행동·상태 뒤에 등장?" → 트리거 매핑. 삭제 ❌, 접근경로 보존 |
| **E** (Embody) | 필요 시 자연스럽게 드러남 — 설명이 아니라 경험으로 이해 | "행동만으로 이해?" → 이중 게이트(객관+형 확인) |

**핵심:** 단순함 = 기능이 적음 ❌ / 복잡함을 숨긴 상태 ✔ — UX의 본질은 타이밍 제어(언제·누구에게·어떤 행동 뒤에 보여줄지).

**🚪 게이트:** Before/After + 타이밍 설계표 + 등급 근거 → 형 승인.

---

## ⑤-b UX_GATE — Nielsen 10 + Norman 5 검증

**역할:** SHE 게이트 통과 후, 제안 직전 UX 원리 전수 점검. 허브 로드: `@ref: references/ux-principles.md#A` + `#B`.

**SHE 관계:** SHE = 타이밍·노출 제어 / UX_GATE = 상호작용 품질. SHE 결과 위에 얹음.

**🚪 게이트:** 15원리 중 **12개+ PASS** → ⑥ 진행. 11↓ → SHE L3 재설계 or ④ 롤백. 체크리스트 → `qc.md §2`.

**SHE 충돌시:** SHE 결정 우선 + 원리 조정안 제시.


## ⑥지식 유입

해당 Action·Task 사례만. 개념적 지식 ✗. 상세 → `references/knowledge-injection.md`

라이트(references/ 번들) vs 풀(+WebSearch). 범용 원칙 차단: "모든 Task에 성립" → 인용 불가.

---

## ⑦제안

4방향(표준/iOS26/AOS/창의적). 토큰 범위 내 + SHE 적용 결과 위에서. 상세 → `references/proposal-rules.md`

최소 2가지는 정보 계층 또는 인터랙션 흐름이 달라야 함.

---

## ⑧산출

HTML 파일. 화면별 4가지 제안 비교. **HTML 스타일은 html-div-style 참조.** UI 비교표 디폴트: 6번 Blueprint.

**CASCADE:** 아웃풋(PRD .md, HTML 와이어프레임 등 파일) 생성 시 design-skill을 Skill tool로 발동 필수. 대화문 분석만으로 끝나면 skip.

| 산출 항목 | 내용 |
|-----------|------|
| 비교 매트릭스 | 구현난이도·사용성·신규성·플랫폼적합도 |
| SHE 적용표 | 노출 등급·숨김 요소·드러남 트리거 |
| 참조 사례 출처 | 지식 유입 사례·가이드라인 |
| 화면별 제안서 | 화면 × 4제안 (HTML 렌더링) |

**PRD 정합성 검증 (PRD 존재 시):** `prd-frames.md` §4. 핵심경로 Task ✗→수정재제안 / △2+→의도적 생략 확인 / ✓80%미만→스코프 괴리 분석.

**코드 산출 (형 명시 시만):** MCP→프레임워크 코드 / 미연결→HTML·CSS. 산출 후 스크린샷 비교 검증 필수.

---

## TURBO 모드

**트리거:** "터보로 제안" · "TURBO" · "UI 터보" 명시.

**불변 (시퀀셜):** ①입력·②DS게이트·③경로판정·④추출·⑤SHE게이트·⑤-b UX_GATE(15 중 12+)·⑧PRD정합성·design-skill CASCADE.

**병렬 타겟:** ⑥ 지식유입(Action당 Agent)·⑦ 4방향 제안(방향별 Agent)·⑧ 화면별 HTML 블록(화면별 Agent).

**품질 방어:** 범용지식 혼입·4방향 중복구조·토큰 이탈·SHE 위반·N9/D3 누락 → 재발행·시퀀셜 복귀. 상세 → `references/forbidden.md §6`·`qc.md §6`.

**예상 단축:** 45~60%.


## Gotchas

| 함정 | 대응 |
|------|------|
| PDF 토큰 과신 | ② 게이트 검증 |
| SHE L1 과잉 | 4축 판정 엄수 |
| 범용 지식 혼입 | Task-특정만 |
| Action/Task 혼용 | 용어표 참조 |
| PRD 없이 과신 | 형 확인 |

**세부 금지:** → `references/forbidden.md`

## Version

- v1.1 (2026-04-23) — html-skill-refactor spine 적용. 4블록 인덱스(tokens·snippets·forbidden·qc) 추가, 기존 7 스포크 유지(허브 특성상 풀스펙 분산). `## 4블록 참조 구조` 섹션 신설. 중복 구분선 정리
- v1.0 — 초기
