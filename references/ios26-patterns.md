# iOS 26 UI Patterns

태스크별 인덱싱. 해당 태스크 관련 섹션만 참조. iOS 26 = WWDC 2025 기준, WebSearch로 최신 보충.

---

## 내비게이션

| 패턴 | 설명 | SHE |
|------|------|-----|
| NavigationStack | push/pop 계층 | S: 현재 depth만 |
| NavigationSplitView | 2-3col (iPad) | S: 좁은 화면→1col 축소 |
| TabView | 최상위 섹션 전환 | H: 5+→More탭 숨김 |
| Sheet (.sheet) | 반투명 시트 | H: 부가 정보 숨김 |
| Full screen cover | 전체화면 모달 | S: 단일 목적 집중 |
| Popover | iPad 팝오버 | H: 컨텍스트 액션 숨김 |

## 입력

| 패턴 | 설명 | SHE |
|------|------|-----|
| TextField | 단일 라인 | S: 레이블+필드만 |
| TextEditor | 멀티라인 | H: 포맷팅→선택 시 노출 |
| SecureField | 비밀번호 | E: 마스킹 피드백 |
| Picker | 옵션 선택 | H: 리스트→탭 시 노출 |
| DatePicker | 날짜/시간 | H: 인라인/컴팩트/휠 모드 |
| Toggle | on/off | S: 즉각 상태 |
| Slider | 범위 값 | E: 드래그로 이해 |

## 목록·콘텐츠

| 패턴 | 설명 | SHE |
|------|------|-----|
| List | 기본 리스트 | H: swipeActions 숨김 |
| Section | 그룹화 | S: 계층 명시 |
| DisclosureGroup | 접기/펼치기 | H: 상세 숨김 |
| ScrollView | 스크롤 | H: 점진적 노출 |
| LazyVGrid/HGrid | 그리드 | S: 균일 리듬 |
| GroupBox | 관련 콘텐츠 묶음 | S: 논리적 묶음 |

## 피드백·상태

| 패턴 | 설명 | SHE |
|------|------|-----|
| Alert | 중요 알림 | E: 행동 결과 등장 |
| ConfirmationDialog | 파괴적 액션 확인 | E: 위험 행동 시만 |
| ProgressView | 진행 상태 | E: 작업 중만 |
| ContentUnavailableView | 빈 상태 | E: 콘텐츠 없을 때만 |
| .searchable | 검색 바 | H: 풀다운 시 노출 |
| .searchScopes | 검색 범위 필터 | H: 검색 활성화 시만 |

## iOS 26 특이사항

| 변경 | SHE 영향 |
|------|---------|
| Liquid Glass | S: 배경 블러 기반 시각적 단순화 |
| 새 탭 바 (플로팅·적응형) | H: 컨텍스트별 가시성 조절 |
| 강화 위젯 인터랙션 | E: 탭 시 기능 드러남 |
| Control Center 커스텀 | H: 기본 최소→커스텀 확장 |
