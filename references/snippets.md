# snippets.md — UI Action Designer 스니펫 인덱스

html-skill-refactor spine 4블록 중 **snippets**. 경로별·단계별·톤별 스니펫 라우팅.

## §1. 단계별 스포크 매핑

| 단계 | 로드 파일 | 스니펫 종류 |
|------|----------|------------|
| ②DS 추출 | `ios26-patterns.md`·`md3-patterns.md` | 컴포넌트 HTML·토큰 템플릿 |
| ③A 파싱 | `prd-frames.md` §1·§2 | PRD 매핑표 |
| ③B 심플PRD | `prd-frames.md` §3 | 팩터 선택 템플릿 |
| ③C 역추론 | `prd-frames.md` §역추론 | 시퀀스 표 |
| ⑤ SHE | `she-protocol.md` | Before/After·타이밍 설계표 |
| ⑤-b UX_GATE | `ux-principles.md#F` | 30초 체크리스트 |
| ⑥ 지식 유입 | `knowledge-injection.md` | Action·Task 사례 표 |
| ⑦ 제안 | `proposal-rules.md`·`ios26-patterns.md`·`md3-patterns.md` | 4방향 템플릿 |
| ⑧ 산출 | `prd-frames.md` §4 | 정합성 검증 매트릭스 |

## §2. 경로별 로딩 규칙 (§③ 분기)

**A경로 (PRD 있음):** `prd-frames.md` §파싱만.
**B경로 (PRD 없음+"PRD부터"):** `prd-frames.md` §심플PRD만.
**C경로 (피그마만):** `prd-frames.md` §역추론만.

전체 파일 로드 ✗ — 경로 판별 후 해당 섹션만 Read.

## §3. 공통 프리미티브

### Action/Task 분해 템플릿
```
Action: [동사] [목적어]
├─ Task 1: [유저 입력·선택]
├─ Task 2: [확인·검증]
└─ Task 3: [실행·피드백]
```

### SHE 이중 게이트
```
객관 판정: 4축 테이블 (없으면 Action 불가? Y/N)
         ↓ 통과
주관 판정: 형 확인 1줄
```

### 4방향 제안 차별화 룰
```
4가지 중 최소 2가지는 다음 중 1개 이상 달라야 함:
 - 정보 계층 (층위 수·그룹핑)
 - 인터랙션 흐름 (Task 순서·트리거 시점)
```

## §4. HTML 산출 규칙 (§⑧)

- **비교 매트릭스:** 구현난이도·사용성·신규성·플랫폼적합도 4축
- **HTML 스타일:** `html-div-style` 6번 Blueprint 디폴트
- **CASCADE:** HTML·PRD .md 생성 시 `design-skill` 발동 필수
- **코드 산출:** 형 명시 시만 (MCP→프레임워크 / 미연결→HTML·CSS)

## §5. 로딩 원칙

- **최대 3스포크/단계** — 경로 판별 후 해당 섹션만
- **ux-principles.md** = ⑤-b 진입시 1회 (#A + #B)
- **knowledge-injection.md** = ⑥ 진입시 1회
- **proposal-rules.md** = ⑦ 진입시 1회
- **prd-frames.md** = 경로 따라 1섹션만
